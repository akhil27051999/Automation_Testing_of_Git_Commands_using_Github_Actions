# 🚀 Automation Testing of Git Commands Using GitHub Actions

This project demonstrates how **Git command execution can be automated and tested** in a CI/CD environment using **GitHub Actions** — a real-world scenario reflecting DevOps and Automation principles.

All commonly used Git commands are stored in a `.txt` file, and an automated GitHub Actions workflow executes these commands whenever a change is pushed to the file or the workflow is manually triggered from the GitHub UI.

---

## 📆 Project Structure

Automation-testing-of-git-commands/ ├── git_commands/ │ ├── git_commands.txt ├── .github/ │ └── workflows/ │ └── git_command_executor.yml

bash
Copy
Edit

- `git_commands.txt`: A text file that holds all your Git commands (one per line).
- `git_command_executor.yml`: GitHub Actions workflow that automates command execution.

---

## ⚙️ How It Works

- When `git_commands.txt` is updated (via push) or the workflow is manually triggered:
  1. GitHub Actions reads each line in the `.txt` file.
  2. Skips blank lines and comments (lines starting with `#`).
  3. Executes each Git command inside a CI shell environment.
  4. Prints the output and error (if any) for each command.
  5. Displays the success or failure status for each command executed.

---

## 🚦 Workflow Triggers

| Trigger Type        | Description                                       |
|---------------------|---------------------------------------------------|
| `push`              | Automatically runs when `git_commands.txt` changes|
| `workflow_dispatch` | Manually triggered from GitHub UI                 |

---

## ✨ Sample Workflow File

```yaml
name: Git Command Executor

on:
  push:
    paths:
      - 'git_commands/git_commands.txt'
  workflow_dispatch:

jobs:
  execute-git-commands:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v3

      - name: Run Git Commands from File
        run: |
          echo "🚀 Executing Git Commands..."
          FILE_PATH="git_commands/git_commands.txt"
          if [ -f "$FILE_PATH" ]; then
            while IFS= read -r cmd || [ -n "$cmd" ]; do
              [[ -z "$cmd" || "$cmd" =~ ^#.* ]] && continue
              echo "🔸 Command: $cmd"
              echo "🔽 Output:"
              eval "$cmd" 2>error.log | tee output.log
              if [ -s error.log ]; then
                echo "❌ Error:"
                cat error.log
              else
                echo "✅ Command executed successfully."
              fi
              echo "-----------------------------"
            done < "$FILE_PATH"
          else
            echo "❌ File not found: $FILE_PATH"
          fi

```
📜 Sample git_commands.txt


git status
git log --oneline
git branch -a
git remote -v
You can add more commands or comment out commands temporarily using #.
```

```
📌 Use Cases
pgsql
Copy
Edit

```

🔍 Practice Git commands in a CI/CD environment.
🧪 Test Git operations in isolation before using them in real workflows.
📚 Learn Git while observing real-time output and behavior.
⚙️ Demonstrate automation skills using GitHub Actions.
📊 Showcase in DevOps/Automation/CI-CD project portfolios.

```
🏁 Getting Started
```

pgsql
Copy
Edit
✅ Fork or Clone the repository.
📝 Add or modify Git commands in `git_commands.txt`.
🔀 Push changes to trigger the workflow automatically.
⚙️ Or go to GitHub Actions > Run Workflow to trigger manually.
📊 View execution output and logs in the Actions tab.

```
🙌 Author
```
Akhil Thyadi
GitHub: @akhil27051999

```
📜 License
```
This project is open source and available under the MIT License.

yaml
Copy
Edit

---

Would you like me to generate a ready-to-use repository template (including sample files and workflow YAML) for download or upload to your GitHub?






