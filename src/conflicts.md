# Merge Conflict

## Create a new directory
```
mkdir git-merge-conflict-demo
cd git-merge-conflict-demo
```

## Add a file
```
echo "Hello, Git!" > example.txt
git add example.txt
git commit -m "docs: test merge conflicts"
```

## Create a new branch
```
git checkout -b quac/docs/merge-conflict-test
```

## Modify the file on the new branch
```
echo "Hello from feature branch!" > example.txt
git commit -am "docs: test edit in feature branch"
```

## Switch back to main branch
```
git checkout main
```

## Make different changes to the same file on the main branch
```
echo "Hello from main branch!" > example.txt
git commit -am "docs: test edit in main branch"
```

## Attempt to merge the feature branch into main
```
git merge quac/docs/merge-conflict-test
```

## Resolve the merge conflict
To resolve the conflict, edit example.txt to keep the changes you want. For example, you can choose one branch's changes over the other, or you can combine them. Once you've edited the file, save it, then add and commit the changes:

```
git add example.txt
git commit -m "Resolved merge conflict"
```

# Rebase Conflict

## Create a new directory
```
mkdir git-rebase-conflict-demo
cd git-rebase-conflict-demo
```

## Create and commit a file
```
echo "Hello, Git!" > example.txt
git add example.txt
git commit -m "docs: test rebase conflicts"
```

## Create a new branch
```
git checkout -b quac/docs/rebase-conflict-test
```

## Modify the file on the new branch
```
echo "Hello from feature branch!" > example.txt
git commit -am "docs: edit in feature branch"
```

## Switch back to main branch
```
git checkout main
```

## Make different changes to the same file on the main branch
```
echo "Hello from main branch!" > example.txt
git commit -am "docs: edit in main branch"
``` 

## Attempt to rebase the feature branch into main
```
git checkout quac/docs/rebase-conflict-test
git rebase main
```

## Resolve the rebase conflict
To resolve the conflict, edit example.txt to keep the changes you want. For example, you can choose one branch's changes over the other, or you can combine them. Once you've edited the file, save it, then add and commit the changes:


# Push Conflict

## Make and push changes from the local repository
```
echo "push conflict example" > example.txt
git add example.txt
git commit -m "docs: push conflict example"
git push
```

## Make and push changes from the remote repository
You can do this from the web interface

## Make more changes from the local repository
```
echo "yet another push conflict example" > example.txt
```

## Attempt to push the changes from the local repository
```
git push
```

## Resolve the push conflict
First pull the changes from the remote repository:
```
git pull
```

Then resolve the conflict by editing example.txt to keep the changes you want. For example, you can choose one branch's changes over the other, or you can combine them. Once you've edited the file, save it, then add and commit the changes:
```
git add example.txt
git commit -m "docs: resolve push conflict"
git push
```

# Pull Conflict

## Make and push changes from the local repository
```
echo "pull conflict example" > example.txt
git add example.txt
git commit -m "docs: pull conflict example"
git push
```

## Make and push changes from the remote repository
You can do this in the web interface

## Makke more changes locally and push
```
echo "yet another pull conflict example" > example.txt
git add example.txt
git commit -m "docs: another pull conflict example"
git push
```

## Attempt to pull the changes from the remote repository
```
git pull origin main
```

## Resolve the pull conflict

1. Open example.txt in your text editor
2. Edit the file to rexolve conflicts
3. Add and commit the changes

```
git add example.txt
git commit -m "docs: resolve pull conflict"
git push
```



