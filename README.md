## gh-workflows

Personal project for reusable [GitHub Actions workflows](https://docs.github.com/en/actions/using-workflows/reusing-workflows) shared across my repositories as a versioned dependency. At the moment, the only one is an auto-assign of issues and PRs to the repository owner (i.e. myself).

Feel free to get in touch or submit an issue if you found a bug or have any feedback.

### assign-to-owner
Automatically assigns a newly opened or reopened Issue or Pull Request to the repository owner.

To use this place a ``` .github/workflows/assign.yml``` as follows in your repository.

```yml
name: Assign to owner

on:
  issues:
    types: [opened, reopened]
  pull_request:
    types: [opened, reopened]

jobs:
  assign:
    uses: martinhammer/gh-workflows/.github/workflows/assign-to-owner.yml@v1
    permissions:
      issues: write
      pull-requests: write
```

#### Pull requests from forks
With the `pull_request` trigger, workflows run on PRs from forks only get a read-only `GITHUB_TOKEN`, so those PRs are skipped and left unassigned. For Dependabot PRs, you can also set `assignees` in `dependabot.yml`.

If you need fork PRs assigned too, use `pull_request_target` instead of `pull_request`. This workflow never checks out or runs code from the PR, so it is a [safe use](https://docs.github.com/en/actions/reference/security/securely-using-pull_request_target) of that trigger. However, GitHub's default policy blocks `pull_request_target` in public repositories, so you will also need an Actions event policy that explicitly allows it.
