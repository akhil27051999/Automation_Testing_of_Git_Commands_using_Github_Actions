# 🚀 Automation Testing of Git Commands Using GitHub Actions

This project demonstrates how **Git command execution can be automated and tested** in a CI/CD environment using **GitHub Actions** — a real-world scenario reflecting DevOps and Automation principles.

All commonly used Git commands are stored in a `.txt` file, and an automated GitHub Actions workflow executes these commands whenever a change is pushed to the file or the workflow is manually triggered from the GitHub UI.

---

## 🏗️ Project Structure
```
Automation-testing-of-git-commands/
|
├── .github/ 
│   └── workflows/ 
│      └── git_commands_workflow.yml
└── git_commands/ 
    └── git_commands.txt 

- `git_commands.txt`: A text file that holds all your Git commands (one per line).
- `git_commands_workflow.yml`: GitHub Actions workflow that automates command execution.

```
⚙️ How It Works

When git_commands.txt is updated (via push) or the workflow is manually triggered:
  1. GitHub Actions reads each line in the .txt file.
  2. Skips blank lines and comments (lines starting with #).
  3. Executes each Git command inside a CI shell environment.
  4. Prints the output and error (if any) for each command.
  5. Displays the success or failure status for each command executed.


## 🚦 Workflow Triggers
```
------------------------------------------------------------------------
| Trigger Type        | Description                                    |
|---------------------|------------------------------------------------|
| `push`              | When `.txt` command files are pushed or changed|
| `workflow_dispatch` | Manual trigger from GitHub UI                  |
------------------------------------------------------------------------

```

## 📌 Use Cases

1. 🔍 Practice Git commands in a CI/CD environment.
2. 🧪 Test Git operations in isolation before using them in real workflows.
3. 📚 Learn Git while observing real-time output and behavior.
4. ⚙️ Demonstrate automation skills using GitHub Actions.
5. 📊 Showcase in DevOps/Automation/CI-CD project portfolios.

## 🏁 Getting Started

1. ✅ Fork or Clone the repository.
2. 📝 Add or modify Git commands in `git_commands.txt`.
3. 🔀 Push changes to trigger the workflow automatically.
4. ⚙️ Or go to GitHub Actions > Run Workflow to trigger manually.
5. 📊 View execution output and logs in the Actions tab.

```
## ✍️ Author
```
Akhil Thyadi
GitHub: [@akhil27051999](https://github.com/akhil27051999)

```
## 📜 License
```
This project is open source and available under the MIT License.
