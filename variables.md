## 📊 Variables vs. 🤫 Secrets

GitHub Actions gives you two ways to store information: **Variables** (for public configuration data) and **Secrets** (for private, sensitive data).

| Feature | 📊 Variables | 🤫 Secrets |
| :--- | :--- | :--- |
| **What it is** | A labeled prep-bowl on the counter. | A locked safe under the counter. |
| **Data Type** | Public info (usernames, folder paths, server names). | Private info (passwords, API keys, tokens). |
| **Visibility** | Visible in plain text in your build logs. | Masked automatically with `***` in build logs. |

---

## 🛠️ How to Use Them in YAML

Here is how you write and reference them inside your `workflow.yml` file.

```yaml
name: Kitchen Deployment Workflow

on: [push]

# 1. Defining global variables at the top
env:
  CHEF_NAME: "Chef_Gordon"
  SERVER_REGION: "us-east-1"

jobs:
  cook_dinner:
    runs-on: ubuntu-latest
    steps:
      - name: Setup the Kitchen Station
        run: |
          echo "The head chef today is \${{ env:CHEF_NAME }}"
          echo "Connecting to the server in region \${{ env:SERVER_REGION }}"

      - name: Log into the Secret Pantry
        run: |
          # Secrets are pulled from your GitHub Repository Settings
          echo "Logging in with token: \${{ secrets.PANTRY_PASSWORD }}"
```

### 💡 Why the Code Looks This Way:
* `env:` This is where you declare your environment variables.
* `${{ env.VARIABLE_NAME }}` This tells GitHub to open the labeled variable box and grab the text inside.
* `${{ secrets.SECRET_NAME }}` This safely fetches encrypted data from your repository settings without exposing it to anyone viewing the code.
