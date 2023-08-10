### Setup & Configuration
- **Set Username**: `git config --global user.name "Your Name"`
- **Set editor for editing like commit messages**: `git config --global core.editor notepad.exe`
- **Set Email**: `git config --global user.email "email@example.com"`

### Creating Repositories
- **Initialize a New Repository**: `git init`
- **Clone an Existing Repository**: `git clone [url]` where url can be github repo url.
- **Adding your existing code to a new repo**: 
  ```
  git remote add origin [url]
  ```
  After making sure that everything is committed.
  ```
  git push
  ```
### Local Changes
- **Check Status of Files**: `git status`
- **Add Changes to Staging**: `git add [file]` or `git add .`
- **Remove changes from Staging**: `git remove [file]` or `git remove .`
- **Commit Changes**: `git commit -m "Commit message"`
- **Show Changes**: `git diff`
- **View Commit History**: 
  To view history of current branch
  ```
  git log
  ```
  To view history of another branch locally.
  ```
  git log [branch-name]
  ```
  To view history of another branch remotelt.
  ```
  git log [remote-name]/[branch-name]
  ```

### Branching & Merging
- **Create a New Branch**: `git branch [branch-name]`
- **Switch to a Branch**: `git checkout [branch-name]`
- **Delete a Branch**: `git branch -d [branch-name]`
- **Merge a Branch**: `git merge [branch-name]`

### Rebasing
- **Rebase Current Branch onto Another**: `git rebase [base-branch]`
- **Continue a Rebase after Resolving Conflicts**: `git rebase --continue`
- **Abort a Rebase**: `git rebase --abort`
- **Interactively Rebase Commits**: `git rebase -i [base-branch or commit]`

### Difference between rebasing && merging
- **Merging**:
  - Combines branches with a new merge commit.
  - Preserves individual branch history.
  - Maintains original commit points.s
- **Rebasing**:
  - Replays changes from one branch onto another.
  - Creates a linear, clean history.
  - Can alter original commit history, losing branch context.

### Remote Repositories
- **Add a Remote**: `git remote add [name] [url]`
- **List Remotes**: `git remote -v`
- **Push to Remote**: `git push [remote-name] [branch-name]`
- **Pull from Remote**: `git pull [remote-name] [branch-name]`
- **Fetch from Remote**: `git fetch [remote-name]`

### Difference between `git fetch` & `git pull`
- **Fetch**:
  - Downloads updates from the remote repository.
  - Does not automatically merge changes into your working branch.
  - Allows you to review changes before integrating them.
- **Pull**:
  - Combines the functionalities of `git fetch` and `git merge`.
  - Downloads updates from the remote repository and immediately merges them into your working branch.
  - Useful when you want to automatically apply remote changes.

### Undoing Changes
- **Unstage Changes**: `git reset [file]`
- **Revert Commit**: `git revert [commit-hash]`
- **Reset to Previous Commit**: `git reset --hard [commit-hash]`

### Miscellaneous
- **Show Stashed Changes**: `git stash list`
- **Apply Stashed Changes**: `git stash apply`
- **Show Configuration**: `git config --list`

