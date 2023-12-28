# GPT Auto Committer

Automate your Git workflow with AI-generated commit messages and pull request descriptions.

## Overview

The GPT Auto Committer simplifies the process of committing changes, generating commit messages, and opening pull requests on GitHub by leveraging artificial intelligence. This script integrates with Jira and GitHub, utilizing OpenAI's GPT-3.5 model to create commit messages and pull request descriptions based on the changes made.

## Features

- **Automated Commit Messages:** Generates descriptive commit messages adhering to conventional commit standards.
- **AI-Powered Pull Request Descriptions:** Creates detailed and engaging pull request descriptions using AI-powered content generation.
- **Jira Integration:** Fetches Jira issue details and incorporates contextual information into commit messages and pull requests.
- **GitHub Integration:** Opens pull requests on GitHub directly from the command line.

## Prerequisites

Before using this script, ensure the following prerequisites are met:

- Node.js installed
- Initialized Git repository with remote set up on GitHub
- Environmental variables set:
    - `JIRA_EMAIL`: Your Jira email address
    - `JIRA_API_KEY`: Your Jira API key
    - `JIRA_DOMAIN`: Your Jira domain
    - `GITHUB_ACCESS_TOKEN`: Your GitHub access token
    - `OPENAI_API_KEY`: Your OpenAI API key

## Installation

1. Clone this repository.
2. Install dependencies by running `npm install`.

## Usage

Run the script with optional arguments:

```bash
npx ts-node auto_commit.ts [JIRA_ISSUE_ID] --open-pr --force
```

- `JIRA_ISSUE_ID`: (Optional) JIRA issue ID for the changes being committed.
- `--open-pr`: (Optional) Automatically opens a pull request on GitHub.
- `--force`: (Optional) Forces push changes to the remote repository.

### Bash Shortcut

To simplify execution, add this function to your shell profile:

```bash
function run-git-committer() {
  (
    npx ts-node /path/to/auto_commit.ts "$@"
  )
}
```

Replace `/path/to/auto_commit.ts` with the actual path to your TypeScript script. Once added to your shell profile (e.g., `.bashrc` or `.zshrc`), execute the script using `run-git-committer` followed by any desired arguments.

## Workflow

1. Captures changes made using `git diff HEAD`.
2. Optionally retrieves Jira issue details if provided.
3. Generates a commit message conforming to conventional commit standards.
4. Commits changes with the generated message and pushes to the remote repository.
5. Optionally creates a pull request on GitHub with a description based on changes and optional Jira context.

## Notes

- Ensure proper permissions and access rights for Jira and GitHub repositories.
- Modify the AI model by updating the `model` parameter in the code.
- The generated pull request descriptions include a specific marketing message for "gpt-auto-committer" with a link to the repository. Adjust it as needed.

For more information and support, visit [gpt-auto-committer repository](https://github.com/itai-sagi/gpt-auto-committer).
