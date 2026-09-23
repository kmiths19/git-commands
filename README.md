# git-commands

This repository contains important Git commands for beginner, intermediate, and advanced software developers.

## 1. Getting Started

### Check Git version
```bash
git --version
```

### Configure your identity
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

### View configuration
```bash
git config --list
```

### Initialize a repository
```bash
git init
```

### Clone a repository
```bash
git clone <repository-url>
```

## 2. Basic Daily Commands

### Check repository status
```bash
git status
```

### See tracked and untracked changes
```bash
git diff
git diff --staged
```

### Add files to staging
```bash
git add <file>
git add .
```

### Commit changes
```bash
git commit -m "Your commit message"
```

### View commit history
```bash
git log
git log --oneline
git log --oneline --graph --decorate
```

## 3. Branching Commands

### List branches
```bash
git branch
git branch -a
```

### Create a branch
```bash
git branch <branch-name>
```

### Switch branches
```bash
git checkout <branch-name>
git switch <branch-name>
```

### Create and switch in one command
```bash
git checkout -b <branch-name>
git switch -c <branch-name>
```

### Rename a branch
```bash
git branch -m <new-branch-name>
```

### Delete a branch
```bash
git branch -d <branch-name>
git branch -D <branch-name>
```

## 4. Remote Repository Commands

### Show remotes
```bash
git remote -v
```

### Add a remote
```bash
git remote add origin <repository-url>
```

### Fetch updates
```bash
git fetch
git fetch --all
```

### Pull latest changes
```bash
git pull
git pull origin <default-branch>
git pull --rebase origin <default-branch>
```

`git pull` fetches and then merges by default. Use `git pull --rebase` when you want to keep a linear history.

### Push changes
```bash
git push
git push origin <branch-name>
git push -u origin <branch-name>
```

## 5. Undo and Recovery Commands

### Unstage a file
```bash
git restore --staged <file>
```

### Discard local changes
```bash
git restore <file>
```

Warning: this permanently removes uncommitted changes in the selected file.

### Amend the last commit
```bash
git commit --amend
```

### Reset commits
```bash
git reset --soft HEAD~1
git reset --mixed HEAD~1
git reset --hard HEAD~1
```

Warning: `git reset --hard` removes committed, staged, and working tree changes that are not preserved elsewhere.

### Revert a commit safely
```bash
git revert <commit-hash>
```

### Recover lost work
```bash
git reflog
```

## 6. Stashing Commands

### Save work temporarily
```bash
git stash
git stash push -m "work in progress"
```

### List stashes
```bash
git stash list
```

### Apply or remove stashed work
```bash
git stash apply
git stash pop
git stash drop stash@{0}
```

## 7. Tagging Commands

### List tags
```bash
git tag
```

### Create tags
```bash
git tag <tag-name>
git tag -a <tag-name> -m "Release message"
```

### Push tags
```bash
git push origin <tag-name>
git push origin --tags
```

## 8. Merge and Rebase Commands

### Merge a branch
```bash
git merge <branch-name>
```

### Rebase on top of another branch
```bash
git rebase <branch-name>
```

### Finish a standard merge after resolving conflicts
```bash
git add <resolved-file>
git commit
```

### Abort a merge
```bash
git merge --abort
```

### Continue a rebase after resolving conflicts
```bash
git add <resolved-file>
git rebase --continue
```

### Abort a rebase
```bash
git rebase --abort
```

## 9. Intermediate Inspection Commands

### Show a specific commit
```bash
git show <commit-hash>
```

### See who changed each line
```bash
git blame <file>
```

### Search commit messages
```bash
git log --grep="keyword"
```

### View commit history for a file
```bash
git log -- <file>
```

## 10. Advanced Git Commands

### Cherry-pick a commit
```bash
git cherry-pick <commit-hash>
```

### Clean untracked files
```bash
git clean -n
git clean -fd
```

Warning: `git clean -fd` permanently deletes untracked files and directories.

### Compare branches
```bash
git diff <base-branch>..<feature-branch>
```

### Create a temporary worktree
```bash
git worktree add ../another-copy <branch-name>
```

### Bisect to find a bad commit
```bash
git bisect start
git bisect bad
git bisect good <commit-hash>
```

### Inspect references
```bash
git show-ref
```

### Squash commits with interactive rebase
```bash
git rebase -i HEAD~3
```

## 11. Helpful Best Practices

- Use `git status` often.
- Write clear commit messages.
- Prefer `git revert` over rewriting shared history.
- Use branches for features, fixes, and experiments.
- Review changes with `git diff` before committing.

## 12. Quick Command Summary

| Level | Common commands |
| --- | --- |
| Beginner | `git init`, `git clone`, `git status`, `git add`, `git commit`, `git log` |
| Intermediate | `git branch`, `git switch`, `git checkout -b`, `git pull`, `git push`, `git stash`, `git tag` |
| Advanced | `git rebase`, `git cherry-pick`, `git reflog`, `git worktree`, `git bisect`, `git clean` |
