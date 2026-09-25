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

## Useful Git Commands and Notes

### 31) Push after merging

After merging the feature branch into `main`, push the updated branch to GitHub so the remote repository also includes the latest changes:

```bash
git push origin main
```

This is important after a merge to make the changes available to others.

### 32) Merge vs. Rebase

#### Merge

`git merge` combines the histories of two branches and creates a merge commit. It is a safe and common option, especially when working with shared branches.

```bash
git merge <branch-name>
```

#### Rebase

`git rebase` moves the current branch's commits on top of another branch, creating a cleaner, more linear commit history. It is useful when you want the branch to appear as if it was built on the latest changes.

```bash
git rebase <branch-name>
```

Example:

```bash
git rebase main
```

In short:

- Merge keeps both branch histories together and is safer for shared work.
- Rebase keeps a cleaner linear history but rewrites commit history, so it should be used carefully.

### 33) `git commit -a -m "msg"`

The `-a` flag tells Git to automatically stage all modified tracked files before creating the commit. It is similar to running `git add .` for files that are already being tracked.

```bash
git commit -a -m "your commit message"
```

> Note: This does not include new untracked files. For those, you still need `git add`.

### 34) `git stash`

`git stash` temporarily saves your current in-progress changes so you can switch branches, pull updates, or work on something else without losing your work.

```bash
git stash
```

This is useful when you need to pause current work temporarily.

### 35) `git pull`

`git pull` downloads the latest changes from the remote repository and merges them into your current branch.

```bash
git pull origin main
```

This keeps your local branch updated with the latest team changes.

### 36) `git stash apply`

`git stash apply` restores the most recently stashed changes without removing them from the stash list.

```bash
git stash apply
```

This is useful after pulling changes or switching branches, when you want to recover your saved work again.

If you want to apply the stash and remove it from the stash list at the same time, you can use:

```bash
git stash pop
```

`git stash apply` is a safer option if you want to keep the stash available for later use.