# Git
__What is Git ?__<br>
Git is a distributed Version control system. <br>
This means that all the codebase including the history of the database is mirrored on the users computer.

__Why we use git?<br>__
Git is very useful for backing your data as well as to track history. It helps when many people are working on same project.
___
## Git Commands

- `git init <folder name/ project name>`<br>This will create a new git repository.

- Git has three States
  1. Working directory
  2. Staging Area
  3. Repository


- Working Directory :- This is the directory where all the file and folder exists. These files or folder may or may not be managed by Git, But git is aware of these files and folders.
- Repository(.git folder) :- In this area all the commits and history are saved.
- Staging Area :- In between the working directory and the repository is the staging area where the working directory is prepared to be moved from the working area to repository.
All these states are saved on local drive. But you can share or save the on a remote server. eg:- Github

- `git status`   -----> Used to check status of your file.
- `git add <file name>` OR use `git add -A` (To add all files to staging area)  -----> To add filename to staging area.
- `git commit -m "This is commit message"`   -----> To commit changes i.e. To add the files from staging area to the Repository.
- `rm -rf .git`    -----> To remove version control system, from the current folder. This is not a git command, for git command use git rm -rf
- `git log`    -----> This command show all the commits that are parts of the repo.
- `git show`    -----> This is similar to git log command. It shows where the HEAD is.
- `git ls-files`   -----> Ths shows files that are tracked by git.
- `git commit -a`    -----> This tells git to add modified files to staging area then commit those files.
- `git commit -am`    -----> Same as above command but with message.
- `git reset HEAD <file name>`   -----> To unstage a file from git.
- `git checkout --<file name>`  -----> To restore a file to previous committed state.
- `git log --oneline --graph --decorate --all`   ----> Use of git log with functionalities.
- `--oneline`     -----> It's for printing all the info of a commit in single line. Shows git history.
- `--graph`       -----> Represent the info by using "*".
- `--decorate`    -----> Tells us which commits are parts of which branches.
- `--all`         -----> Include all commits.
- `git config --global alias.<alias name> "log --oneline --graph --decorate --all"`     -----> This is used to create a alias, which can be used to represent the log command with extra functionality.
- `--global` is used because we want the alias to be at user level not at a repository level.
- `--alias.<alias name>`       -----> Used to create a alias name.
- After that you can use `git hist -- <file name>`     -----> Will show the history of the file.
- git config `--global --list`    -----> will give list of all the global configuration in GIT.
- git config `--global --edit`    -----> To edit the global configuration.
- `git mv README.md PLEASE_README.md`     -----> Renaming a file in git. This will rename the file in working directory and add the action to the staging area, To rename files in repo, You have to commit changes. So
  - Committing the changes `git commit -m "Renaming the file".`    -----> The advantage of using git to perform these file operation is that they are tracked by git.
- `git rm <file name>`   -----> To delete a file, after this need to commit changes.
- `git add -u`   -----> To update deleted files and add them to staging area
- `git add -A`   -----> Covers all types of updates/modificatio on git directory and add them to staging area
- To exclude a file/folder from git, make a file named .gitignore and open it with txt editor, Then add the file name that you want git to ignore in the .gitignore file. for eg: see the Git folder in P: drive.
  - To ignore an extension like .log extension use -----> `*.log`
- `git diff <address of first commit> <address of second commit>`   -----> This tells the difference between the two commits.
- `git difftool <address of first commit> <address of second commit>`  -----> Shows difference using difftool.

- Branching is just a timeline of commits. Branches are the names we give to timelines in Git
- After a timeline is complete the branches can be merged with the master branch.
Types of merges    ----->
1. Fast-Forward
- Fast-Forward is simplest case of merging
- Git will simply apply all changes to feature branch to master branch and it will appear though the branching never existed.
- We can disable this type of branch.

2. Automatic
- Non conflicting Merge in Parent branch. Git automatically detects any conflicts and resolves them
- Preserves both timelines
- Merge commit on Destination

3. Manual merge
- Automatic Merge not possible
- Conflicting Merge States
- Changes saved in Merge commit

Special Markers
Just like "Pointers"
- HEAD
  - Points to last commit of current branch
  - Can be moved manually


- `git branch`    -----> Tells us current branch that we are on.
- `git checkout -b <name of branch>`     -----> This creates a branch and switches to that branch
  - `checkout` -----> Used to change branch -----> `-b` used to create a branch
- To merge the branches we need to first switch to master branch using -----> `git checkout <branch name>`
- `git merge <name of the branch that you want to merge>`   -----> Merges the master branch with feature branch.
- `git branch -d <name of branch>`    -----> This deletes the feature branch.
- Conflicts will occur when same part of the file is changed on different branches, It will fail to merge aromatically.

**Tagging Events**<br>
- `git tag -a <name of tag> -m "Release 1.0"`    -----> `-a` is for annotated tag. These tag contain extra info compared to simple tags
- `git tag -d <Tag name>`     -----> To delete a tag.

**Stashing**<br>
- Save work in Progress with stashing<br>
- Stashing is used put the current work in stash, This will remove the files from being tracked while they are in stash. They can be removed from stash when needed.
- `git stash`  -----> Puts all current files in a stash
- `git stash list`   -----> Shows the files and commits in stash
- `git stash pop`  -----> It performs two action<br>
  - 1. It applies whatever was in the stash to files.
  - 2. It drops the stash that was applied

**Time Travel**
- `git reset <commit id> --soft`     -----> `--soft` is lead destructive rollback as it just changes the HEAD pointer to the given id.
- `git reset <commit id> --mixed`    -----> `--mixed unstates` the changes that had occurred.
- `git reset <commit id> --hard`        -----> `--hard` is the most destructive, It wipes all the commits before the given commit.
- `git reflog`    -----> This is very useful it will give us all the commit id even after hard resetting the commit, Using reflog we can jump to any commit we want.
- `git commit --amend`   ----> This is used to change the commit message, Where HEAD is pointing.

___
## Github


- `git remote add origin https://github.com/kushagra414/demo.git`    -----> `add` ----> takes two parameters:-<br> 
  - 1. name of remote reference 
  - 2. full url of repository
- `git push -u <reference name of remote repo> <name of local branch> --tags`     ----->  `-u` sets up a tracking branch relationship between master branch on local repo and master branch on remote repo. origin is reference name of remote repo.  `--tags` to send all the tags in local repo
- `git remote -v`      -----> Tells if we are connected to a remote server
  GIT REMOTE COMMANDS
 git remote [-v | --verbose]
   - `git remote add [-t <branch>] [-m <master>] [-f] [--tags | --no-tags] [--mirror=<fetch|push>] <name> <url>`
   - `git remote rename <old> <new>`
   - `git remote remove <name>`
   - `git remote set-head <name> (-a | --auto | -d | --delete | <branch>)`
   - `git remote [-v | --verbose] show [-n] <name>`
   - `git remote prune [-n | --dry-run] <name>`
   - `git remote set-branches [--add] <name> <branch>`
   - `git remote get-url [--push] [--all] <name>`
   - `git remote set-url [--push] <name> <newurl> [<oldurl>]`
   - `git remote set-url --add <name> <newurl>`
   - `git remote set-url --delete <name> <url>`

    - `-v, --verbose` be verbose; must be placed before a sub-command.


- Using SSH security instead of HTTPS.
Why ? Because it saves time, should be used only on Personal Computer.

- SSH vs HTTPS
HTTPS asks for username and password every time hence we will use SSH

- `git clone <cloning url> <name of the folder to clone to. This is optional>`

- From git 2.0 and above `git push` only sends master branch to github. We need to change default push behavior to `simple` this command to push all branches to the github `git config --global push.default simple`.
- `git pull` ---> Git Pull is using 2 commands at once i.e. `git fetch` and `git merge` But this command can be destructive if you have changes that are incompatible with github.
- `git fetch` ---> Git fetches the info from remote repo and creates a new branch and will suggest to merge them.
- `git remote set-url <reference name of repo> <new-link>` ---> This could be used if you renamed the your repo or if the url of repo changed.
- `git remote show <reference name of repo>` ---> This shows info about the remote repo.
- `git show <SHA-1 commit id>` ---> This shows info about that commit, SHA-1 commit id can be copied from remote repo(github).<br />
- `git mergetool` ---> for resolving merge conflicts.
- `git fetch -p` ---> Remove stale/dead branches references from github.
- `git config --global -e` ---> For editing the global commands.
- `git pull -all` ---> Will pull/ update all tracking branches, as by default git will pull only the branch on which you are currently are.
- `git push Test :<branch name to delete>` ---> This will push all the updates to remote repo and delete any branches after the `:`<br />
- __Checkout rebase commands from here ---> https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase and https://www.atlassian.com/git/tutorials/merging-vs-rebasing__
- `git pull --rebase` ---> This command will rebase the local branch and will make it ahead of the repo branch.
- You can change the default branch in github from master to any other branch you may like.
`git tag <tag name> <branch name>` ---> Used to associate a simple tag with a branch
`git tag -a <tag name> -m "message/extra information" <commit id>` ---> These are annotated tags.
- `git show <tag name>` ---> Shows all the info about that tag.
- `git push <remote ref> <tag name>` ---> To push particular tag to github.
- `git tag -d <name of tag>` ---> To delete a tag.
- `git push <repo ref> :<Tag name>` ---> This will delete the tag from remote repo.
- `git tag -f <tag name> <commit id>` ---> To change a Tag to new commit id.
- `git push --force <repo ref> <tag name>` ---> To force push a tag to gituhb.
-  We can compare tags, commits, branches and time ranges in github by using the `pull request` section on github.
-  Syntax for comparing time changes ---> `<branch name>@{time/date/days}`.
-  You can also compare ranges by comparing HEAD at different positions ---> `HEAD@{number}`. `HEAD^` ---> This means HEAD-1
- `git commit -m "message", close #<issue number>"` ---> This will close the issue and also show the commit id associated with the issue on github.

## To update your forked repo with the original github repo follow :-

- Add **Upstream** of original repo to your git.
  - `git remote add upstream <link of original git repository>`
- Next is to pull the upstream.
  - `git pull upstream master`
- After this you need to push the changes to forked repository.
  - `git push origin master`