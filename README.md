 CI/CD Pipeline – Task 1

 Project Overview

This task implements a basic CI/CD pipeline using GitHub Actions for the repository.
The pipeline is configured to automatically build and deploy the application when changes are pushed to the designated branch.

---

Branching Strategy

| Branch Name            | Purpose                                                    |
| ---------------------- | ---------------------------------------------------------- |
| `version-1`            | Default branch (base/main code).                           |
| `task1-ci-cd-pipeline` | Feature branch used to create and test the CI/CD pipeline. |
| `staging`              | Used for deployment or staging environment testing.        |

Development and workflow testing are done in `task1-ci-cd-pipeline`. After validation, changes are pushed to `staging` for deployment.

---

Pipeline File Location

The CI/CD workflow file is located at:

```
.github/workflows/staging-deploy.yml
```

---

Workflow Details

The workflow performs the following steps:

1. Trigger

   Runs on push to the `staging` branch or manually from the Actions tab.

2. Job – Build and Deploy

    Checks out the repository code.
    Sets up the required runtime environment.
    Installs dependencies.
    Runs tests (if applicable).
    Deploys the code to the staging environment.

---

 How to Work with Branches

| Action                   | Command                                                                                 |
| ------------------------ | --------------------------------------------------------------------------------------- |
| Switch to feature branch | `git checkout task1-ci-cd-pipeline`                                                     |
| Commit changes           | `git add .`<br>`git commit -m "Message"`                                                |
| Push to remote           | `git push origin task1-ci-cd-pipeline`                                                  |
| Merge to staging         | `git checkout staging`<br>`git merge task1-ci-cd-pipeline`<br>`git push origin staging` |

---

 Requirements

 GitHub repository access
 GitHub Actions enabled
 Valid deployment credentials or tokens (stored in GitHub Secrets)

---

 Deployment Notes

 Any updates pushed to the `staging` branch will automatically trigger the pipeline.
 Ensure all environment variables and secrets are configured correctly in:

  ```
  Settings → Secrets and variables → Actions
  ```
