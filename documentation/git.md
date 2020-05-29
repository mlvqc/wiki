# Git

## Quick commands

| desire                                                       | command                                                      |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| clone a git repo                                             | `git clone https://github.com/<your_username>/<repo name>`   |
| create a new remote for the upstream repo (which is the original repo you forked from) | `git remote add upstream https://github.com/<original repo you forkedfrom>` |
| get the current branch name                                  | `git branch`                                                 |
| get access to remote branches                                | `git fetch`                                                  |
| see branches available for checkout                          | `git branch -v -a`                                           |
| create a new local branch that will track a prior (remote) branch | `git checkout -b <new local branch name>  <origin/remote_branch_name>` |
| create a new branch                                          | `git checkout -b <new branch name>`                          |
| create a new remote for the upstream repo (which is the original repo you forked from) | `git remote add upstream https://github.com/<original repo you forkedfrom>` |
| check status of git (changes etc.)                           | `git status`                                                 |
| add a file to commit                                         | `git add <filename>`                                         |
| add all files in directory to commit                         | `git add .`                                                  |
| commit files `add`ed to the current branch with sign-off `-s` and message `-m` | `git commit -s -m "<add informative message about edits and committed files>"` |
| push commits and changes to new branch                       | `git push -u origin <branch currently editing name>`         |



## GitHub Fundamentals

Contributing to a project on Github

1. **Fork** the project to your **personal** git hub

2. Clone locally.

   `git clone https://github.com/<your_username>/<repo name>`

3. Create an *upstream* remote and sync your local copy before you branch

   `git remote add upstream https://github.com/<original repo you forkedfrom>`

4. Create a new branch & branch for each separate piece of work.

   `git checkout -b <new branch name>`

5. Do the work, write [good commit messages](https://blogs.gnome.org/danni/2011/10/25/a-guide-to-writing-git-commit-messages/), and read the CONTRIBUTING file if there is one.

   `git status`

   `git add <filename>`

   `git commit -s -m "<add informative message about edits and committed files>"`

6. Push to your *origin* repository.

   `git push -u origin <branch currently editing name>`

7. Create a new Pull Request in GitHub - see the ***Compare & Pull Request button*** in Github.

8. Respond to any [code review](http://www.lornajane.net/posts/2015/code-reviews-before-you-even-run-the-code) feedback.

If you want to contribute to an open source project, the best  one to pick is one that you are using yourself. The maintainers will  appreciate it!

Source: [Rob Allen](https://akrabat.com/the-beginners-guide-to-contributing-to-a-github-project/) & Brandon Severin

## Keeping a fork synced

If you have forked a repo and added an `upstream` correctly (for basic instructions see [GitHub-Fundamentals](##GitHub-Fundamentals) or [GitHub docs](https://help.github.com/en/github/getting-started-with-github/fork-a-repo#keep-your-fork-synced)) here are instructions on how to keep for fork in sync with the original remote repo using the Terminal.

1. Open the terminal and `cd` into your project

2. Fetch the branches and their respective commits from the upstream repository. Commits to `master` will be stored in a local branch, `upstream/master`
   
   `git fetch upstream`
   
3. Check out your fork's local master branch

   `git checkout master`
 
4. Merge the changes from `upstream/master` into your local master branch. This brings your fork's master branch into sync with the upstream repository, without losing your local changes. 

   `git merge upstream/master`
   
   
[Brandon]
