# CI/CD Web Project

This project demonstrates a complete Continuous Integration and Continuous Deployment (CI/CD) pipeline using GitHub Actions and Vercel. It is built with HTML, CSS, and JavaScript contained within a single file to focus on the DevOps implementation.

![Build Status](https://github.com/velectronicsr/cicd/actions/workflows/advanced-ci.yml/badge.svg)

## Project Overview

The goal of this repository is to implement a professional-grade DevOps workflow for a simple web application. The pipeline ensures that no broken or unformatted code can be merged into the main branch, and successfully merged code is automatically deployed to production.

## Features

* **Automated Linting:** Uses HTMLHint to check for syntax errors and best practices.
* **Style Enforcement:** Uses Prettier to ensure consistent code formatting.
* **Branch Protection:** GitHub rules prevent merging pull requests unless all automated checks pass.
* **Continuous Deployment:** Vercel automatically deploys changes to production immediately after a successful merge.

## Tech Stack

* **Frontend:** HTML5, CSS3, JavaScript (ES6)
* **CI Provider:** GitHub Actions
* **CD Provider:** Vercel
* **Tools:** HTMLHint, Prettier

## Pipeline Workflow

The CI/CD pipeline is defined in `.github/workflows/advanced-ci.yml`. It runs automatically on every Push and Pull Request to the main branch.

1.  **Checkout:** The pipeline pulls the latest code from the repository.
2.  **Setup:** Installs Node.js environment.
3.  **Linting:** Runs `htmlhint index.html` to verify code quality. If this fails, the build stops.
4.  **Formatting Check:** Runs `prettier --check .` to verify code style. If code is messy, the build stops.
5.  **Deployment:** If all checks pass and the code is merged, Vercel triggers a deployment to the live URL.

## How to Run Locally

1.  Clone the repository:
    git clone https://github.com/velectronicsr/cicd.git

2.  Navigate to the project directory:
    cd cicd

3.  Open `index.html` in your browser to view the application.

## How to Test the Pipeline

**To trigger a failure (Test CI):**
1.  Create a new branch.
2.  Edit `index.html` and remove a closing tag (e.g., `</html>`).
3.  Push the changes and open a Pull Request.
4.  Observe that the "Advanced Lint & Build" check fails and blocks the merge.

**To trigger a success (Test CD):**
1.  Fix the HTML syntax error.
2.  Push the fix to the branch.
3.  Observe that the checks pass.
4.  Merge the Pull Request and verify the changes on the Vercel deployment URL.
