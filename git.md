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


Why is it recommended to use pull requests in Git instead of directly pushing changes to the master branch?

`git pull request`, often referred to as just a "pull request" (PR) or "merge request" in some platforms like GitLab, is a feature of distributed version control systems like Git that facilitates collaboration. Pull requests provide a way for developers to submit changes to a project for review before those changes are merged into a primary branch, such as the `master` or `main` branch. Here's why pull requests are important and why pushing directly to the master branch is often discouraged:

1. *Code Review*: PRs provide an opportunity for other team members to review code changes. This helps ensure that the code is of high quality, follows project conventions, and doesn't introduce any regressions or bugs.

2. **Continuous Integration (CI) and Continuous Deployment (CD)**: Many projects have CI/CD pipelines set up to run tests, lint code, and perform other checks when a pull request is opened. This ensures that any proposed changes don't break existing functionality.

3. *Maintain a Clean History*: Direct pushes can lead to a cluttered and hard-to-follow commit history, especially if multiple people are pushing simultaneously. PRs allow for a more organized approach, where feature branches can be merged in a single commit (especially if you're squashing commits), keeping the history cleaner.

4. *Avoid Disrupting the Stable Code*: The `master` branch is often considered the stable or production-ready branch. If everyone pushes their changes directly to `master`, it can quickly become unstable. By using feature branches and PRs, there's a buffer zone where testing and integration happen before it reaches `master`.

5. *Documentation and Discussion*: PRs provide a platform to discuss the changes being proposed. This can be in the form of code comments, general discussions about the implementation approach, or suggestions for improvement. It acts as a documented history of the decision-making process for future reference.

6. *Access Control*: It's a security risk to allow everyone to push directly to the primary branch. By restricting direct pushes and using PRs, you can ensure that only trusted contributors can modify the codebase after appropriate review.

7. *Conflict Resolution*: When multiple developers work on the same codebase, there's potential for merge conflicts. Resolving these conflicts in the context of a PR allows for a more isolated and controlled environment.

8. *Encourage Modular Work*: When developers know they'll need to submit a PR for changes, they're more likely to make changes in smaller, more modular chunks. This results in more manageable code changes and more straightforward reviews.

For all these reasons and more, most professional development teams adopt a workflow that encourages the use of pull requests and discourages direct pushes to the primary or master branch. It helps maintain the quality, stability, and security of the codebase.