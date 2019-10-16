Git Commands
============

## Translated Versions
- [Versão em português](READMEpt.md)

___

_A list of my commonly used Git commands_

*If you are interested in my Git aliases, have a look at my `.bash_profile`, found here: https://github.com/joshnh/bash_profile/blob/master/.bash_profile*

--

### Getting & Creating Projects

| Command | Description |
| ------- | ----------- |
| `git init` | Initialize a local Git repository |
| `git clone ssh://git@github.com/[username]/[repository-name].git` | Create a local copy of a remote repository |

### Basic Snapshotting

| Command | Description |
| ------- | ----------- |
| `git status` | Check status |
| `git add [file-name.txt]` | Add a file to the staging area |
| `git add -A` | Add all new and changed files to the staging area |
| `git commit -m "[commit message]"` | Commit changes |
| `git rm -r [file-name.txt]` | Remove a file (or folder) |

### Branching & Merging

| Command | Description |
| ------- | ----------- |
| `git branch` | List branches (the asterisk denotes the current branch) |
| `git branch -a` | List all branches (local and remote) |
| `git branch [branch name]` | Create a new branch |
| `git branch -d [branch name]` | Delete a branch |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git checkout -b [branch name]` | Create a new branch and switch to it |
| `git checkout -b [branch name] origin/[branch name]` | Clone a remote branch and switch to it |
| `git checkout [branch name]` | Switch to a branch |
| `git checkout -` | Switch to the branch last checked out |
| `git checkout -- [file-name.txt]` | Discard changes to a file |
| `git merge [branch name]` | Merge a branch into the active branch |
| `git merge [source branch] [target branch]` | Merge a branch into a target branch |
| `git stash` | Stash changes in a dirty working directory |
| `git stash clear` | Remove all stashed entries |

### Sharing & Updating Projects

| Command | Description |
| ------- | ----------- |
| `git push origin [branch name]` | Push a branch to your remote repository |
| `git push -u origin [branch name]` | Push changes to remote repository (and remember the branch) |
| `git push` | Push changes to remote repository (remembered branch) |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git pull` | Update local repository to the newest commit |
| `git pull origin [branch name]` | Pull changes from remote repository |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git` | Add a remote repository |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH |

### Inspection & Comparison

| Command | Description |
| ------- | ----------- |
| `git log` | View changes |
| `git log --summary` | View changes (detailed) |
| `git diff [source branch] [target branch]` | Preview changes before merging |


### Process to work with git and open source

* Fork the repo (click the fork button on the repo you want to help with)
* Clone your forked repo (on the repo https://github.com/bobbo489/<repo_name>), (click the clone/download and copy the url, it should end in .git) 
  * git clone https://github.com/bobbo489/<repo_name>.git
* Create a new branch 
  * cd repo
  * git branch "new-informative-branch-name"
  * git checkout "new-informative-branch-name"
    * If needing to go back to master = git checkout master
* Make edits and changes as needed to files in the local repo
* Add and commit those changes
  * git add <files you changed>
  * git commit -m "short message here" or git commit <-- opens up your text editor where you can add more and longer info
* Verify what will be committed
  * git status
* Push your changes to the current branch of the forked repo
  * git push --set-upstream origin <new-informative-branch-name>
* Update your local repo in case other updates have happened!
  * Check the remotes
    * git remote -v (should list your repos and actions you can do to them)
    * May need to add the original repo (probably a good thing if you want to actually do things)
      * git remote add <some shortname, like upstream> https://github.com/original-owner-username/original-repository.git
  * Check the remotes again to make sure your addition worked
    * git remote -v
* Sync the Fork to ensure everything is up to date
  * git fetch <the shortname you selected above>
* Switch to master branch and merge
  * git checkout master
  * git merge <shortname you selected above>/master
* Create the Pull Request to incorporate your code!
  * On your forked repo, select New Pull Request
    * Add/modify the title and comments as needed, then click Create Pull Request
  * If the maintainers of the original repo like your stuff, they can accept it, if not they can decline it, or have you modify your code prior to accepting the request.
* Any things that need a refresher....look at this good guide.  https://www.digitalocean.com/community/tutorials/how-to-create-a-pull-request-on-github
