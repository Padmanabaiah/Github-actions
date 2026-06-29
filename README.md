# Github-actions
This project is about Github Actions Implementations for Applications to deploy into Bare metal Kubernetes(Kind))

First we will cover the basics of Github Actions before proceeding with actual implementation of foundation level knowledge in GitHub Actions.

You should have a repository in your github account created and when you open repository and click on the actions. It will redirect you to GH Actions page.
```text
Components of GitHub Actions:
📁 .github/workflows/
└── 📋 workflow.yml  <- The Recipe Book
     ├── 🔔 Event     <- The Customer Order (Triggers the recipe)
     └── 👨‍🍳 Job       <- The Kitchen Station (Isolated environment)
          └── 📝 Step  <- The Cooking Tasks (Sequential commands)
               └── 🛠️ Action <- The Kitchen Tools (Reusable shortcuts)
```
1. <u>**Workflow**<u>:
   . Technical Definition: An automated, top-level process configured in your repository using a YAML file. It defines the overall automation        pipeline, environment variables, and execution architecture.
   . Location: Stored in the (.github/workflows/) directory.
   . Kitchen Analogy: The Recipe Book. It is the master blueprint detailing exactly how a specific dish (your software process) is constructed from start to finish.
2. <u>**Event**<u>:
   . Technical Definition: A specific activity or webhook that triggers a workflow run. Events can be repository-driven (push, pull_request), manual (workflow_dispatch), or time-based (schedule via cron syntax).
   . Kitchen Analogy: The Customer’s Order. It is the spark that alerts the kitchen to start cooking. No order means the kitchen sits idle.
3. <u>**Job<u>**:
   . Technical Definition: A set of sequential steps executed on the same fresh instance of a virtual machine or container. By default, multiple jobs run concurrently (in parallel) unless specified otherwise via dependency mapping (needs: keyword).
   . Kitchen Analogy: The Kitchen Station. A dedicated area (like the Grill Station or Pastry Station) operating independently. Multiple stations cook different parts of the meal simultaneously to save time.
4. <u>**Runner<u>**:
   . Technical Definition: The underlying execution environment or compute infrastructure hosting the Job. Runners can be GitHub-hosted (ephemeral Ubuntu, Windows, or macOS VMs) or Self-hosted (infrastructure managed by you).
   . Kitchen Analogy: The Stove and Electricity. The physical hardware and utility power required to make the kitchen station actually functional.
5. <u>**Step<u>**:
   . Technical Definition: An individual, linear task executed within a Job. Steps run sequentially on the same Runner, allowing them to share file system states and environmental outputs with subsequent steps.
   . Kitchen Analogy: The Cooking Tasks. The exact, one-by-one actions a chef must take at their station (e.g., Step 1: Fetch ingredients. Step 2: Chop them. Step 3: Sear them.).
6. <u>**Action<u>**:
   . Technical Definition: Reusable, modular sub-components or plugins designed to execute repetitive, complex logic (e.g., setting up a language runtime, authenticating with cloud providers). You can build custom actions or pull verified ones from the GitHub Marketplace.
   . Kitchen Analogy: The Kitchen Tools. Specialized gadgets like an electric blender or a garlic press. Instead of writing code to do everything manually by hand, you use a pre-made tool to get it done instantly.


