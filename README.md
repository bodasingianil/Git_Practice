# Git_Practice

1) git init on parent folder
2) Created home.py index.py and source.py files
3) git add .
4) git commit -m "initial commit"
5) modified home.py file 
6) git add .
7) git commit -m "saving home file"
8) likewise update files 
9) git log 
	006450d fun index created
	37eb338 EOF
	ea43be7 updated userid
	2cbaa8f saving index file
	0a63daa saving home file
	981247b initial commit
10) Git show <commit id> ====> tell you under the file what are the specific changes made 
11) git log --oneline    ====> shows all commits in oneline 
	b40a274 (HEAD -> master) Revert index fun
	8509e49 fun sub created
	8f019ca fun add created
	6a48233 fun index removed
	5c7d498 fun calculate_area created
	4faf523 fun greet  created
	006450d fun index created
	37eb338 EOF
	ea43be7 updated userid
	2cbaa8f saving index file
	0a63daa saving home file
	981247b initial commit
	
12) git blame <file_name> ====> shows the changes in the file with timestamp and author
13) git reset --hard <commit_id> ====> removes history of latest commits of commit_id. Code also will be erased
	- lose code and history of latest chagnes/addons
14) git revert <commit_id> ===> keeps the latest code and adds/merges the code along with latest code of specific commit_id

	b40a274 (HEAD -> master) Revert index fun
	8509e49 fun sub created
	8f019ca fun add created
	6a48233 fun index removed
	5c7d498 fun calculate_area created
	4faf523 fun greet  created
	006450d fun index created
	37eb338 EOF
	ea43be7 updated userid
	2cbaa8f saving index file
	0a63daa saving home file
	981247b initial commit

15) git remote add origin https://github.com/bodasingianil/Git_Practice.git
	Here: you are connecting local git with github. so taking remote. origin is branch name preferrably used always. link refers to github branch
16) git remote -v
	origin  https://github.com/bodasingianil/Git_Practice.git (fetch)
	origin  https://github.com/bodasingianil/Git_Practice.git (push)
	
17) git branch
* master
18) if its master then rename to main 
19) git branch -M main ====> It will be renamed from master -> main
20) git push -u origin main 
	Here: 	push --> push local code to online 
			origin --> online branch name
			main --> local branch name
21) git pull origin main --allow-unrelated-histories 
	Here: when git and github not in sync and trying to push local code to github
22) git branch ==> shows all branches in repo
23) git branch "anil-feature" ==> creates feature branch if not exists
24) git checkout anil-feature ==> Switched to branch 'anil-feature'
25) modify index.py file and commit the changes
26) git push --set-upstream origin anil-feature 
	Here: Created anil-feature on github 
27) update files in local repo and commit 
28) git checkout main  ==> Switched to branch 'main'
29) git merge origin/anil-feature  ==> merging origin branch with anil-feature branch in github

	
