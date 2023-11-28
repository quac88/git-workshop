# Commands and Common Problems in Git

## Common Problems

### `git commit`
- **Common Problem**: 
  - If you want to commit to a side branch called `test`, you need to first checkout `test` and then commit.
  - Example: 
    ```bash
    git checkout test
    git commit -m "Your commit message"
    ```

### `git merge`
- **Tips**:
  - When merging in Git, make sure to checkout the branch you want to merge into.
  - Example: If you want to merge the `Test` branch into `main`, then checkout `main` and then type `git merge Test`.
    ```bash
    git checkout main
    git merge Test
    ```

### `git pull`
- **Common Issues**:
  - Users often pull before checking the remote repository if there is any commit to pull.
  - Remember, `git pull` is essentially `git fetch` + `git merge`. 
  - Always ensure you have a commit to fetch, and then it will merge it.
  - Use this wisely and always check the status of your local branch before using `git pull`.

### `git push`
- **Best Practice**:
  - Before pushing your changes to the remote repository using `git push`, ensure your local repository is up-to-date with the changes made by others.
  - This helps in avoiding conflicts and ensures that your changes are based on the latest code.

## Common Scenarios

### Parallel Edits to the Same Lines
- **Scenario**:
  - Developer A modifies a file and pushes changes.
  - Developer B also modifies the same file without pulling the latest changes.
  - When Developer B tries to push, Git detects conflicting changes on the same lines.
