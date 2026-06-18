<!-- START: Git Advanced Part 1 -->

# Question 1: Setup Repository
git clone https://github.com/ora-nova/git-advanced
cd git-advanced

# Question 2: Create initial files
touch test{1..4}.md
git add test1.md
git commit -m "chore: Create initial file"

git add test2.md
git commit -m "chore: Create another file"

git add test3.md
git commit -m "chore: Create third and fourth files"

# Question 3: Fix missing file (amend commit)
git add test4.md
git commit --amend -m "chore: Add third and fourth files"

# Question 4: Fix commit message using rebase
git rebase -i HEAD~2
# change "Create another file" → "Create second file"

# Question 5: Squash commits
git rebase -i --root
# squash "Create second file" into "Create initial file"

# Question 6: Drop unwanted commit
touch unwanted.txt
git add unwanted.txt
git commit -m "Unwanted commit"

git rebase -i --root
# drop "Unwanted commit"

# Question 7: Reorder commits (if required in editor)
git rebase -i --root

# Question 8: Create branch and add file
git checkout -b ft/branch
touch test5.md
git add test5.md
git commit -m "Implemented test 5"

# Question 9: Cherry-pick commit into main
git checkout main
git cherry-pick 96b515a

# Question 10: Visualize history and Check reflog 
git log --graph --oneline --all
git log --graph --oneline --decorate --all
git reflog
git push --force-with-lease origin main

<!-- END: Git Advanced Part 1 -->
<!-- START: Git Advanced Part 2 -->

# Question 1: Feature Branch Creation
git checkout -b ft/new-feature

# Question 2: Work on Feature Branch
echo "feature work" > feature.txt
git add .
git commit -m "Implemented core functionality for new feature"

# Question 3: Switch Back to Main & New File
git checkout main
echo "Welcome to the project" > readme.txt
git add .
git commit -m "Updated project readme"

# Question 4: Remote Branch Basics
git push origin ft/new-feature
git fetch
git pull origin main
git branch -a

# Question 5: Delete Branch
git checkout main
git branch -d ft/new-feature
git branch -D ft/new-feature

# Question 6: Create Branch from Commit
git log --oneline
git checkout -b ft/new-branch-from-commit 0db8018

# Question 7: Merge Branch
git checkout main
git merge ft/new-branch-from-commit

# Question 8: Rebase Branch
git checkout ft/new-branch-from-commit
git rebase main 

# Question 9: Rename Branch
git branch -m ft/new-branch-from-commit ft/improved-branch-name

# Question 10: Detached HEAD
git checkout b9ecb6f
git checkout -b  ft/recovery-branch

<!-- END: Git Advanced Part 2 -->
<!-- START: Git Advanced Part 3 -->

# Question 1: Stash Changes
git stash

# Question 2: Restore Stash
git stash pop

# Question 3: Merge Conflict Resolution
git merge ft/conflict-branch
# fix conflicts manually
git add .
git commit

# Question 4: Merge Tool (optional)
git mergetool

# Question 5: Detached HEAD Recovery
git checkout main
git checkout -b recovery-branch

# Question 6: Ignore Files (.gitignore)
echo "/tmp" > .gitignore
git add .
git commit -m "Add gitignore"

# Question 7: Tags
git tag v1.0
git tag
git tag -d v1.0

# Question 8: Push to Remote
git push origin main
git push --all origin
git push origin v1.0

# Question 9: Pull from Remote
git pull origin main

# Question 10: Sync GitHub Changes
# make changes on GitHub
git pull origin main

<!-- END: Git Advanced Part 3 -->

