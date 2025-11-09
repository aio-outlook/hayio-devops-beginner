# Stage 2: Git & GitHub

Stage 2 is a hands-on guide that introduces beginners to Git and GitHub for version control, remote collaboration, and secure authentication workflows in DevOps projects.

## Step 1: What Git and GitHub Are

- **Git** is a distributed version control tool that runs locally, letting you snapshot changes, compare history, and work offline.
- **GitHub** is a cloud platform that hosts Git repositories, provides collaboration features (branch protection, pull requests, reviews), and enables teamwork across locations.
- Typical workflow: develop and commit locally with Git, then sync to GitHub so collaborators can review and integrate your work.

## Step 2: Configuring Git Identity

Set your global author details so every commit records the correct name and email:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Confirm the configuration when needed:

```bash
git config --global --list
```

## Step 3: Initialize and Connect Repositories

Create a project folder, initialize Git, and prepare a starter file:

```bash
mkdir my-first-git-project
cd my-first-git-project
git init
echo "# My First Git Project" > README.md
git status
```

Create a new repository on GitHub (leave it empty), then connect your local repository to the remote:

```bash
git remote add origin https://github.com/<username>/<repo>.git
git remote -v
```

`git remote -v` confirms the remote URL for fetch and push operations.

## Step 4: Authentication Options

### Option A: HTTPS + Personal Access Token (Classic)

- GitHub requires Personal Access Tokens (PATs) instead of passwords for HTTPS pushes.
- Generate a classic token with only the `repo` scope at:

  ```text
  https://github.com/settings/tokens
  → Generate new token (classic)
  → Select "repo" scope only
  ```

- Use the token in your remote URL or paste it when prompted during `git push`. Example from the live session:

  ```bash
  git remote add origin https://aio-outlook:ghp_xyz1234567i5iaDkIKxxB57AdTeinDfk4f3M0h@github.com/aio-outlook/first.git
  ```

This classic token unlocks push, pull, and clone operations for repositories covered by the `repo` scope.

_The token shown above was revoked immediately after the live session; always protect active tokens._

### Option B: SSH Authentication

SSH keys provide a more persistent, secure method for automation and long-term access.

Generate and register a new key pair:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

Display the public key and copy it:

```bash
cat ~/.ssh/id_ed25519.pub
```

Add the key on GitHub: `Settings → SSH and GPG Keys → New SSH Key`, paste the public key, and save.

Test SSH connectivity:

```bash
ssh -T git@github.com
```

You should see a greeting confirming authentication without pulling any data.

## Step 5: Commit and Push Workflow

Follow this sequence to publish your first commit:

```bash
echo "My first Git project" > readme.txt
git add .
git commit -m "first commit"
git branch -M main
git push -u origin main
```

- `git add .` stages every tracked change.
- `git commit -m` records the staged changes with a meaningful message.
- `git branch -M main` renames the current branch to `main`.
- `git push -u origin main` uploads the branch and sets `origin/main` as the upstream target.

## Step 6: Common Git Commands

| Command | Purpose |
|---------|---------|
| `git status` | Inspect current changes and staging state |
| `git add <file>` | Stage specific files for the next commit |
| `git commit -m "<message>"` | Record staged changes with a message |
| `git push` | Send local commits to the remote repository |
| `git pull` | Fetch and integrate remote commits into the current branch |
| `git log` | Review commit history |
| `git branch` | List or manage local branches |
| `git checkout <branch>` | Switch to another branch |

## Step 7: Troubleshooting

| Issue | What It Means | Fix |
|-------|----------------|-----|
| `remote: Permission to <org>/<repo>.git denied to <username>` | Account lacks access or wrong remote owner | Confirm repository ownership and access rights; if wrong remote, reset it via `git remote set-url origin https://github.com/<username>/<repo>.git`. |
| `403 Permission denied` | Invalid or expired token, or cached credentials | Generate a new PAT with `repo` scope, remove cached credentials (Keychain, credential manager), and push again. |
| `fatal: unable to access 'https://github.com/...':` | Remote URL incorrect or network blocked | Verify the remote URL (`git remote -v`), update it if needed, and ensure network connectivity. |

Update the remote if you need to correct its URL:

```bash
git remote set-url origin https://github.com/<username>/<repo>.git
```

## Step 8: Key Takeaways

- A classic PAT with only the `repo` scope is sufficient for pushes, pulls, and cloning over HTTPS.
- SSH keys provide a secure, reusable option ideal for automation and long-lived access.
- Core Git loop: `git init → git add → git commit → git push` keeps local and remote repositories synchronized.

For the full walkthrough of the live session, see:  
[Git & GitHub Session (2025-11-08)](./git-github-session-2025-11-08.md)
