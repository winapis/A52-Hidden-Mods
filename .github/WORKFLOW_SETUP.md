# Workflow Configuration

This repository includes a GitHub Actions workflow that automatically syncs the repository content to `https://dumps.tadiphone.dev/dumps/samsung/pa1q.git`.

## Setup Instructions

### Required Secrets

To configure the workflow, you need to add the following secrets to your GitHub repository:

1. Go to your repository on GitHub
2. Navigate to **Settings** → **Secrets and variables** → **Actions**
3. Click **New repository secret** and add:

#### Required Secrets:
- `DUMPS_USERNAME`: Username for authentication with dumps.tadiphone.dev
- `DUMPS_PASSWORD`: Password or personal access token for authentication

#### Optional Secrets:
- `DUMPS_REPO_URL`: Custom repository URL (defaults to `https://dumps.tadiphone.dev/dumps/samsung/pa1q.git`)

### Workflow Triggers

The workflow runs automatically:
- **On push to main branch**: Syncs changes immediately
- **Manual trigger**: Can be run manually from the Actions tab

### What the Workflow Does

1. **Checkout**: Downloads the complete repository history
2. **Configure Git**: Sets up Git user for the sync operation
3. **Authentication**: Uses provided credentials to authenticate with the target repository
4. **Sync**: Pushes all branches and tags to the dumps repository
5. **Cleanup**: Removes authentication details from Git configuration

### Security Notes

- Credentials are handled securely through GitHub Secrets
- Authentication details are cleaned up after each run
- The workflow uses force push to ensure complete synchronization

### Manual Execution

You can manually trigger the workflow:
1. Go to the **Actions** tab in your repository
2. Select **Sync to Dumps Repository**
3. Click **Run workflow**