# Stage 2: Git & GitHub

Stage 2 is a hands-on introduction to Git and GitHub for version control and collaboration.

## Step 1: Understand Git and GitHub

- **Git** is a distributed version control system that runs locally and records snapshots of your project history.
- **GitHub** is a cloud service that hosts Git repositories and adds collaboration tooling such as pull requests, reviews, and issue tracking.
- Best practice: make changes locally with Git, then sync to GitHub so teammates can review and contribute.

## Step 2: Configure Git

Set your identity so commits are attributed correctly:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
git config --global init.defaultBranch main
git config --list --global
```

## Step 3: Initialize a Local Repository

Create a project folder, initialize Git, and inspect status:

```bash
mkdir hayio-sample-app
cd hayio-sample-app
git init
echo "# Hayio Sample App" > README.md
git status
```

## Step 4: Create a GitHub Repository

1. Sign in to GitHub and select `New repository`.
2. Name the repository (for example, `hayio-sample-app`) and choose visibility.
3. Leave it empty (no README, .gitignore, or license) so you can push your local history.

## Step 5: Connect Local and Remote Repositories

Add the GitHub repository as a remote named `origin`:

```bash
git remote add origin https://github.com/<your-username>/hayio-sample-app.git
git remote -v
```

## Step 6: Make the First Commit and Push (HTTPS)

Stage files, commit, set the primary branch, and push to GitHub:

```bash
git add README.md
git commit -m "chore: initial commit"
git branch -M main
git push -u origin main
```

## Step 7: Authenticate with a Personal Access Token (Classic)

GitHub no longer accepts account passwords for Git operations.

1. Navigate to GitHub `Settings` → `Developer settings` → `Personal access tokens` → `Tokens (classic)`.
2. Generate a new token with the `repo` permission scope and set an expiration.
3. During the first HTTPS push, enter your GitHub username and use the token as the password. Allow your credential manager to store it when prompted.

Example prompt:

```bash
Username for 'https://github.com': your-username
Password for 'https://your-username@github.com': <paste-token-here>
```

## Step 8: Use Common Git Commands

| Command | Purpose |
|---------|---------|
| `git status` | Display tracked, staged, and unstaged changes |
| `git add <file>` | Stage file(s) for the next commit |
| `git commit -m "<message>"` | Record staged changes in the repository history |
| `git branch` | List local branches |
| `git checkout -b <name>` | Create and switch to a new branch |
| `git pull` | Fetch and merge remote changes into the current branch |
| `git push` | Upload local commits to the remote repository |

## Step 9: Troubleshoot 403 Permission Errors on Push

- Confirm the remote URL is correct and uses HTTPS: `git remote -v`.
- Ensure the Personal Access Token is active, unexpired, and includes the `repo` scope.
- If macOS Keychain or another credential helper cached an old password, remove that entry and push again to supply the new token.
- For organization repositories, verify that you have write access and that the token is authorized for the organization.

## Step 10: Key Takeaways

- Git runs locally to track history; GitHub hosts repositories and enables collaboration.
- Configure your Git identity once before committing to keep authorship accurate.
- A consistent workflow (`status → add → commit → push`) keeps local and remote repositories aligned.
- Personal Access Tokens secure HTTPS pushes—manage and rotate them responsibly.

For a detailed walkthrough of the November 8, 2025 live session, see:  
[Git & GitHub Session (2025-11-08)](./docs/git-github-session-2025-11-08.md)
