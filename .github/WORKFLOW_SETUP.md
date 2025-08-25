# Workflow Configuration

This repository includes a GitHub Actions workflow that downloads the dumps repository from `https://dumps.tadiphone.dev/dumps/samsung/pa1q.git` and makes it available as a downloadable artifact.

## Setup Instructions

### No Configuration Required

This workflow works out of the box and doesn't require any secrets or configuration. It simply clones the public dumps repository and uploads it as an artifact.

### Workflow Triggers

The workflow runs automatically:
- **On push to main branch**: Downloads the latest dumps repository
- **Manual trigger**: Can be run manually from the Actions tab

### What the Workflow Does

1. **Clone**: Downloads the dumps repository from `https://dumps.tadiphone.dev/dumps/samsung/pa1q.git` into a folder called `dump`
2. **Upload**: Uploads the entire `dump` folder as a GitHub Actions artifact
3. **Retention**: Artifacts are kept for 30 days before automatic deletion

### Downloading the Artifact

After the workflow completes:
1. Go to the **Actions** tab in your repository
2. Click on the latest workflow run
3. Scroll down to the **Artifacts** section
4. Download the `dumps-repository` artifact (will be a ZIP file)
5. Extract the ZIP to access the dumps repository content

### Manual Execution

You can manually trigger the workflow:
1. Go to the **Actions** tab in your repository
2. Select **Download Dumps Repository**
3. Click **Run workflow**