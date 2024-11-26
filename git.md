### Git Commands Cheat Sheet

This cheat sheet covers the most common Git commands for everyday use. For more detailed information, refer to the [official Git documentation](https://git-scm.com/doc).

#### Configuration
- **Set user name**: `git config --global user.name "Your Name"`
- **Set user email**: `git config --global user.email "your.email@example.com"`

#### Repository
- **Initialize a repository**: `git init`
- **Clone a repository**: `git clone <repository-url>`

#### Basic Snapshotting
- **Check status**: `git status`
- **Add files to staging area**: `git add <file>`
- **Commit changes**: `git commit -m "commit message"`
- **Remove files**: `git rm <file>`
- **Move or rename files**: `git mv <old-file> <new-file>`

#### Branching and Merging
- **List branches**: `git branch`
- **Create a new branch**: `git branch <branch-name>`
- **Switch to a branch**: `git checkout <branch-name>`
- **Create and switch to a new branch**: `git checkout -b <branch-name>`
- **Merge a branch**: `git merge <branch-name>`
- **Delete a branch**: `git branch -d <branch-name>`

#### Remote Repositories
- **Add a remote repository**: `git remote add <name> <url>`
- **Fetch changes from remote**: `git fetch <remote>`
- **Push changes to remote**: `git push <remote> <branch>`
- **Pull changes from remote**: `git pull <remote> <branch>`

#### Undoing Changes
- **Revert a commit**: `git revert <commit>`
- **Reset to a previous commit**: `git reset --hard <commit>`
- **Unstage a file**: `git reset <file>`

#### Cherry-picking
- **Cherry-pick a commit**: `git cherry-pick <commit>`

#### Inspection and Comparison
- **Show commit history**: `git log`
- **Show changes**: `git diff`
- **Show changes for a specific file**: `git diff <file>`
- **Show commit details**: `git show <commit>`

#### Stashing
- **Stash changes**: `git stash`
- **Apply stashed changes**: `git stash apply`
- **List stashes**: `git stash list`
- **Drop a stash**: `git stash drop`
