# DEV Guestbook

Welcome to the **Intro to Software Engineering** workshop from **DEV**, OSU's Software Engineering Club! 👋

Tonight you will make your very first contribution to a real GitHub project. You will add a small file about yourself to this guestbook, then ask us to accept it with a **pull request**. This is the same process engineers use at real companies every day.

Never used Git before? Perfect. That is who this is for.

> **No time for setup?** Skip to [No setup? Use the browser](#no-setup-use-the-browser).

---

## Setup

Do this once before the steps below.

1. **Install Git:** download it from https://git-scm.com/downloads and install it with the default options. Git is the tool that tracks changes to files.
2. **Install VS Code:** download it from https://code.visualstudio.com. This is the code editor we will use.
3. **Sign into GitHub in VS Code:** open VS Code, click the person icon in the bottom left corner, and choose **Sign in with GitHub**. This lets VS Code push your work to GitHub for you.
4. **Tell Git who you are:** open a terminal (in VS Code: **Terminal > New Terminal**) and run these two commands with your own name and the email on your GitHub account:

   ```sh
   git config --global user.name "Your Name"
   git config --global user.email "you@example.com"
   ```

   Git stamps your name and email on every change you save.

---

## Steps

In the commands below, replace `<your-github-username>` with your real GitHub username (and remove the `<` and `>`).

### 1. Fork this repo

Click the **Fork** button at the top right of this page, then click **Create fork**.

A **fork** is your own copy of this repo on GitHub. You can change your copy however you want without affecting the original.

### 2. Clone your fork

On your fork's page, click the green **Code** button and copy the URL. Then run:

```sh
git clone https://github.com/<your-github-username>/dev-guestbook.git
```

This downloads your fork from GitHub onto your computer.

### 3. Go into the folder

```sh
cd dev-guestbook
```

This moves your terminal into the project folder you just downloaded.

### 4. Make a new branch

```sh
git checkout -b add-<your-github-username>
```

This creates a **branch**, a separate line of work where you can make changes safely, and switches you onto it.

### 5. Copy the template

```sh
cp attendees/_template.md attendees/<your-github-username>.md
```

This makes a copy of the template file and names it after you. (You can also right click the template in VS Code, copy it, paste it, and rename it.)

### 6. Fill it in

Open the project in VS Code with `code .`, then open your new file and write your answer after each field. Save the file.

This is the actual change you are contributing.

### 7. Save and upload your change

```sh
git add attendees/<your-github-username>.md
```

This tells Git which file you want to include in your next save.

```sh
git commit -m "Add <your name>"
```

This saves a snapshot of your change, called a **commit**, with a short message describing it.

```sh
git push origin add-<your-github-username>
```

This uploads your branch to your fork on GitHub.

### 8. Open a pull request

Go to your fork on GitHub. You should see a yellow banner with a **Compare & pull request** button. Click it, check the boxes in the checklist, and click **Create pull request**.

A **pull request** (PR) asks the owners of the original repo to pull your change into it. A robot will check your file in about a minute. If you see a green check mark, you are done! 🎉 If you see a red X, click **Details** to see what to fix.

---

## Push not working?

If `git push` asks for a password and then fails, that is normal. **GitHub does not accept your account password for pushing.** It needs a token instead, or for you to be signed in through VS Code.

The easiest fix is the GitHub CLI:

1. Install it from https://cli.github.com
2. Close and reopen your terminal, then run:

   ```sh
   gh auth login
   ```

3. Choose **GitHub.com**, then **HTTPS**, then **Yes** to authenticate Git, then **Login with a web browser**. Follow the steps in your browser.
4. Run your `git push` command again.

Or, sign into GitHub in VS Code (see [Setup](#setup) step 3) and push using the **Source Control** tab on the left side of VS Code.

---

## No setup? Use the browser

You can do the whole thing without installing anything:

1. **Fork** this repo (see step 1 above).
2. On **your fork's** page, press the **`.`** (period) key. This opens **github.dev**, a version of VS Code that runs in your browser.
3. In the file list on the left, right click the `attendees` folder, choose **New File**, and name it `<your-github-username>.md`.
4. Copy everything from `attendees/_template.md` into your new file and fill it in.
5. Click the **Source Control** icon on the left (it looks like a branching line), type a message like `Add <your name>`, and click **Commit & Push**.
6. Go back to your fork on github.com, click **Contribute**, then **Open pull request**, and click **Create pull request**.

---

## Done early?

Try these challenges:

1. **Review someone else's PR.** Go to the **Pull requests** tab of this repo, open someone's PR, click **Files changed**, and leave a friendly comment on a line. Then click **Review changes** and submit your review.
2. **Update your file after feedback.** Edit your file, then run `git add`, `git commit`, and `git push` again on the same branch. Your pull request updates by itself. No new PR needed!
3. **Cause and fix a merge conflict with a partner.** A merge conflict happens when two people change the same line in different ways, and Git needs a human to pick the right version.
   - In one person's **fork** (not this repo), go to **Settings > Collaborators** and add your partner.
   - Both of you clone that fork and make your own branch.
   - Both of you edit the **same line** of the same file differently, then commit and push.
   - Open a PR for each branch. When opening it, change **base repository** to the fork, not `devosu/dev-guestbook`.
   - Merge the first PR. The second PR will now say it has conflicts. Click **Resolve conflicts**, pick the text you want to keep, delete the `<<<<<<<`, `=======`, and `>>>>>>>` lines, and click **Mark as resolved**, then **Commit merge**.

---

## Rules

See [CONTRIBUTING.md](CONTRIBUTING.md). Short version: one file per person, only edit your own file, and name it after your GitHub username.
