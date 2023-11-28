# Merge Conflict

## Create a new directory
```bash
mkdir git-merge-conflict-demo
cd git-merge-conflict-demo
```

## Add a file
```bash
echo "Hello, Git!" > example.txt
git add example.txt
git commit -m "docs: test merge conflicts"
```

## Create a new branch
```bash
git checkout -b quac/docs/merge-conflict-test
```

## Modify the file on the new branch
```bash
echo "Hello from feature branch!" > example.txt
git commit -am "docs: test edit in feature branch"
```

## Switch back to main branch
```bash
git checkout main
```

## Make different changes to the same file on the main branch
```bash
echo "Hello from main branch!" > example.txt
git commit -am "docs: test edit in main branch"
```

## Attempt to merge the feature branch into main
```bash
git merge quac/docs/merge-conflict-test
```

## Resolve the merge conflict
To resolve the conflict, edit example.txt to keep the changes you want. For example, you can choose one branch's changes over the other, or you can combine them. Once you've edited the file, save it, then add and commit the changes:

```bash
git add example.txt
git commit -m "Resolved merge conflict"
```

# Rebase Conflict

## Create a new directory
```bash
mkdir git-rebase-conflict-demo
cd git-rebase-conflict-demo
```

## Create and commit a file
```bash
echo "Hello, Git!" > example.txt
git add example.txt
git commit -m "docs: test rebase conflicts"
```

## Create a new branch
```bash
git checkout -b quac/docs/rebase-conflict-test
```

## Modify the file on the new branch
```bash
echo "Hello from feature branch!" > example.txt
git commit -am "docs: edit in feature branch"
```

## Switch back to main branch
```bash
git checkout main
```

## Make different changes to the same file on the main branch
```bash
echo "Hello from main branch!" > example.txt
git commit -am "docs: edit in main branch"
``` 

## Attempt to rebase the feature branch into main
```bash
git checkout quac/docs/rebase-conflict-test
git rebase main
```

## Resolve the rebase conflict
To resolve the conflict, edit example.txt to keep the changes you want. For example, you can choose one branch's changes over the other, or you can combine them. Once you've edited the file, save it, then add and commit the changes:


# Push Conflict

## Make and push changes from the local repository
```bash
echo "push conflict example" > example.txt
git add example.txt
git commit -m "docs: push conflict example"
git push
```

## Make and push changes from the remote repository
You can do this from the web interface

## Make more changes from the local repository
```bash
echo "yet another push conflict example" > example.txt
```

## Attempt to push the changes from the local repository
```bash
git push
```

## Resolve the push conflict
First pull the changes from the remote repository:
```bash
git pull
```

Then resolve the conflict by editing example.txt to keep the changes you want. For example, you can choose one branch's changes over the other, or you can combine them. Once you've edited the file, save it, then add and commit the changes:
```bash
git add example.txt
git commit -m "docs: resolve push conflict"
git push
```

# Pull Conflict

## Make and push changes from the local repository
```bash
echo "pull conflict example" > example.txt
git add example.txt
git commit -m "docs: pull conflict example"
git push
```

## Make and push changes from the remote repository
You can do this in the web interface

## Makke more changes locally and push
```bash
echo "yet another pull conflict example" > example.txt
git add example.txt
git commit -m "docs: another pull conflict example"
git push
```

## Attempt to pull the changes from the remote repository
```bash
git pull origin main
```

## Resolve the pull conflict

1. Open example.txt in your text editor
2. Edit the file to rexolve conflicts
3. Add and commit the changes

```bash
git add example.txt
git commit -m "docs: resolve pull conflict"
git push
```

# Using Cheery-Pick

## Create a new directory
```bash
mkdir cherry-pick-demo
cd cherry-pick-demo
```

## Create a base file and commit
```bash
echo "Initial commit" > example.txt
git add example.txt
git commit -m "docs: initial commit for cherrypick demo"
```

## Create two branches
```bash
git checkout -b quac/docs/cherry-pick-branch-1
git checkout main
git checkout -b quac/docs/cherry-pick-branch-2
```

## Add commits to both branches
```bash
git checkout quac/docs/cherry-pick-branch-1
echo "Feature 1 content" >> example.txt
git commit -am "docs: add to Feature 1"
```
```bash
git checkout quac/docs/cherry-pick-branch-2
echo "Feature 2 content" >> example.txt
git commit -am "docs: add to Feature 2"
```

## Cherry-pick scenerio
Imagine you're working on feature2 and realize that a particular commit from feature1 is needed in your branch. However, you don't want the entire feature1 branch merged into your feature2 branch.

## Cherry-picking the commit
```bash
git checkout quac/docs/cherry-pick-branch-1
git log
```

Copy the commit hash of the commit you want to cherry-pick. Then switch to the branch you want to cherry-pick into and run the following command:
```bash
git checkout quac/docs/cherry-pick-branch-2\
git cherry-pick <commit-hash>
```

## Cherry-pick conflict
If there is a conflict, resolve it as you would any other conflict. Then add and commit the changes:
```bash
git add example.txt
git commit -m "docs: resolve cherry-pick conflict"
```

Once the cherry-pick is successful and conflicts (if any) are resolved, the changes from the specific commit in feature1 are now in your feature2 branch.

# Using Reset

## Make a new directory
```bash
mkdir reset-demo
cd reset-demo
```

## Create a base file and commit
```bash
echo "Initial commit" > example.txt
git add example.txt
git commit -m "docs: initial commit for reset demo"
```

## Make a series of commits
```bash
echo "Change 1" >> example.txt
git commit -am "docs: Change 1"

echo "Change 2" >> example.txt
git commit -am "docs: Change 2"

echo "Change 3" >> example.txt
git commit -am "docs: Change 3"
```

## View the commit history
```bash
git log
```

## Reset to a previous commit

### soft
```bash
git reset --soft [commit-hash]
```
### mixed
```bash
git reset --mixed [commit-hash]
```
### hard
```bash
git reset --hard [commit-hash]
```

# Reverting a Commit

## Make a new directory
```bash
mkdir revert-demo
cd revert-demo
```

## Add a file and make intiial commits
```bash
echo "Initial content" > example.txt
git add example.txt
git commit -m "docs: initial commit"

echo "Update 1" >> example.txt
git commit -am "docs: Update 1"

echo "Update 2" >> example.txt
git commit -am "docs: Update 2"
```

## View the commit history
```bash
git log
```

## Revert a specific commit
```bash
git revert [commit-hash]
```

# Using Stash

## Make a new directory
```bash
mkdir stash-demo
cd stash-demo
```

## Add a file and commit
```bash
echo "Initial content" > example.txt
git add example.txt
git commit -m "docs: initial commit"
```

## Make a change to the file
```bash
echo "Update 1" >> example.txt
```

## Stash the changes
```bash
git stash
```

## Switch branches and apply stash to the new branch
```bash
git checkout -b quac/docs/stash-demo
git stash apply
```

## Resolve the stash conflict
If there are conflicts after applying the stash, resolve them as you would in a merge conflict. Edit the files to fix the conflicts, then add and commit:

## Result
The changes from the stash are now in the new branch. The stash can be dropped if no longer needed
```bash
git stash drop
```




