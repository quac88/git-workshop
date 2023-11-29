# Best Practices

Product Development is a team sport. Cordination and communitcation is the key to success.

# Main vs. Dev Branch

The main branch is exclusively reserved for production ready code. Everything on main should be treated as if it already is in the hands of the consumer.

## Redunencies - Protecting the Main Branch

Before anything is merged into main, it should be reviewed and tested by at least one other person depending on the size and complexity of the project. 

## Protect Main Branch

Protect the main branch to avoid inaproprate changes.

![protect_main_branch_1](/images/branch-protections.png)

## Pipeline

In smaller low complexity projects with 1-3 developers, it may make sense to commit directly to development then merge releases into main. As projects become larger and more complex, it is important to have a pipeline that ensures that code is tested and reviewed before it is merged into main. In large projects, development should not be committed to. Instead, developers should create a branch off of development, make their changes, then create a pull request to merge their changes into development. Each branch must be owned by a single developer so that there is a single point of communication. Use these naming conventions for branching and PRs: [contributing.md](/docs/contributing.md).

## Commits 

It is recommended to use [angular style commits](/docs/commits.md) so that the commit messages are easy to navigate and understand should you need to revert a commit. Additionally, this allows for automated versioning and changelog generation.













