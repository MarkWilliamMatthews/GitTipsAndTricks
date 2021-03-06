# Git Tips And Tricks

**List local commits not on remote:** 
	
    git log --branches --not –remotes

**List commits history (remote):**
	 
    git log

**Remove a file from tracking locally (ignore) (note that this will not solve a conflict on remote):**

    git update-index --skip-worktree <path-name>

**Stash local changes (temporary or changes preventing a pull):**
	
    git stash

**Re-apply local changes (will try merge stashed and local changes. Conflicts may be present):**

    git apply stash

**Re-apply stashed changes for a specific file (force the local copy to be the same as the stashed version):** 

	git checkout stash -- <paths...>

**How to view local commits against remote:**

	git log origin/develop..HEAD

**Revert to a previous commit locally:**

	git log # view commits
	git checkout commit # checkout to commit

**Revert to a previous commit that has been pushed to remote:**
	
	git reset --hard 'xxxxx'
	git clean -f -d
	git push -f

**Checkout a file from another branch:**

In the branch you want to add the file to do:

	git checkout branch_name -- file_name

**View difference between two commits:**

	git diff commit1^..commit2

**How to test a pull request and merge:**

	git checkout -b name_of_branch develop
	git pull git@github.com:user/eonemp.git name_of_branch

**How to merge a branch once it has been tested:**

	git checkout develop
	git merge name_of_branch # merge branch to current branch
	git push # push commits to remote
	git branch -d name_of_branch # deletes branch!!! Use with care. 

**Compare local to remote version of a file:**

	git diff origin/master -- [local-path]
  where master is name of any remote branch. 


**Merge a specific commit from another branch:**

	git cherry-pick commit-hash 

	
