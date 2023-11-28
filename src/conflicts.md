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
```
To resolve the conflict, edit example.txt to keep the changes you want. For example, you can choose one branch's changes over the other, or you can combine them. Once you've edited the file, save it, then add and commit the changes:

```
git add example.txt
git commit -m "Resolved merge conflict"
```

