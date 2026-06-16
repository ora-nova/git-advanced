<!-- START: Git Advanced Part 1 -->

# Question 1: Setup Repository
git clone <your-repo-url>
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
git cherry-pick <commit-hash>

# Question 10: Visualize history and Check reflog 
git log --graph --oneline --all
git log --graph --oneline --decorate --all
git reflog
git push --force-with-lease origin main

<!-- END: Git Advanced Part 1 -->
