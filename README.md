# Git Practice

A practical record of the Git commands used while creating and updating this repository.

## Initial Repository Setup

1. Initialize Git in the parent folder:

   ```bash
   git init
   ```

2. Create the project files, including `home.py`, `index.py`, and the files in `src/`.
3. Stage and commit the initial version:

   ```bash
   git add .
   git commit -m "initial commit"
   ```

4. Modify `home.py`, then stage and commit the changes:

   ```bash
   git add .
   git commit -m "saving home file"
   ```

## Reviewing History

View the complete commit history:

```bash
git log
```

View a compact, one-line version of the history:

```bash
git log --oneline
```

Example commit history:

```text
b40a274 (HEAD -> master) Revert index fun
8509e49 fun sub created
8f019ca fun add created
6a48233 fun index removed
5c7d498 fun calculate_area created
4faf523 fun greet created
006450d fun index created
37eb338 EOF
ea43be7 updated userid
2cbaa8f saving index file
0a63daa saving home file
981247b initial commit
```

Inspect the changes introduced by a specific commit:

```bash
git show <commit-id>
```

View who changed each line of a file, along with the timestamp and commit:

```bash
git blame <file-name>
```

## Undoing Changes

Reset the repository to a specific commit and discard later changes:

```bash
git reset --hard <commit-id>
```

> **Warning:** A hard reset removes the later commits from the current branch and erases their working-tree changes. Use it carefully.

Create a new commit that reverses the changes from an earlier commit while preserving history:

```bash
git revert <commit-id>
```

## Connecting to GitHub

Add the GitHub repository as the `origin` remote:

```bash
git remote add origin https://github.com/bodasingianil/Git_Practice.git
```

In this command, `origin` is the conventional name for the remote repository.

Check the configured remote URLs:

```bash
git remote -v
```

Example output:

```text
origin  https://github.com/bodasingianil/Git_Practice.git (fetch)
origin  https://github.com/bodasingianil/Git_Practice.git (push)
```

Rename the default branch from `master` to `main`:

```bash
git branch -M main
```

Push the local `main` branch to GitHub and set its upstream branch:

```bash
git push -u origin main
```

Here, `origin` is the remote name and `main` is the branch name.

If the local and remote repositories have unrelated histories, pull the remote branch with:

```bash
git pull origin main --allow-unrelated-histories
```

## Branches

List all local branches:

```bash
git branch
```

Create and switch to a feature branch:

```bash
git branch anil-feature
git checkout anil-feature
```

After modifying `index.py`, stage and commit the changes, then publish the feature branch:

```bash
git add .
git commit -m "update index file"
git push --set-upstream origin anil-feature
```

Switch back to `main` and merge the remote feature branch:

```bash
git checkout main
git merge origin/anil-feature
```

Check the current working-tree and branch status:

```bash
git status
```

For example, Git may report:

```text
Your branch is ahead of 'origin/main' by 3 commits.
(use "git push" to publish your local commits)
```