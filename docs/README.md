# AI4Blockchain Arxiv Daily - Usage Guide

This repository automatically crawls and updates papers from arXiv related to the intersection of **Artificial Intelligence** and **Blockchain** technologies.

## Overview

This codebase is composed of the following parts:

- `daily_arxiv.py`: main script to process given configurations and fetch papers from arXiv
- `config.yaml`: configuration file for paper keywords, output paths, etc.

## Usage

<details>
  <summary>Table of Contents</summary>

1. **Fork this repository**
   - Fork the [AI4Blockchain-arxiv-daily](https://github.com/jhy-3/AI4Blockchain-arxiv-daily) repository

2. **Edit configurations**
   - Change `user_name` and `repo_name` in [config.yaml](../config.yaml) to match your GitHub username and repository name
   - Customize `keywords` in [config.yaml](../config.yaml) to add or modify search terms
   - Push changes to your remote repository

3. **Configure GitHub Actions**
   - Go to **Settings** → **Actions** → **General**
   - Under "Workflow permissions", select **"Read and write permissions"** and save
   - Go to **Actions** tab
   - Click **"I understand my workflows, go ahead and enable them"**
   - Enable the workflows:
     - **"Daily Arxiv Update"**: Runs automatically every day at 00:00 UTC
     - **"Weekly Update Paper Links"**: Runs every Monday to update code links
   - You can manually trigger workflows by clicking "Run workflow" button

4. **Setting GitHub Pages (optional)**
   - Go to **Settings** → **Pages**
   - Under "Build and deployment", select:
     - Source: **"Deploy from a branch"**
     - Branch: **"main"** and folder **"/docs"**
   - Save the settings
   - Your GitHub Pages will be available at: `https://your_github_username.github.io/AI4Blockchain-arxiv-daily`

5. **Add new keywords (optional)**
   - Edit `keywords` section in [config.yaml](../config.yaml)
   - You can add more filters or keywords for different topics
   - Push changes to remote repository
   - Re-run GitHub Actions manually or wait for the next scheduled run

</details>

## Configuration

### Keywords Configuration

Edit the `keywords` section in `config.yaml` to customize search terms:

```yaml
keywords:
    "AI+Blockchain":
        filters: ["artificial intelligence blockchain", "machine learning blockchain"]
    "Smart Contracts & AI":
        filters: ["smart contract AI", "AI smart contract"]
```

### Output Configuration

The script generates three types of output:

- **README.md**: Main repository README with paper listings
- **docs/index.md**: Web page for GitHub Pages
- **JSON files**: Structured data stored in `docs/` directory

## Local Testing

To test the script locally:

```bash
# Install dependencies
pip install -r requirements.txt

# Run the script
python daily_arxiv.py --config_path config.yaml

# Update paper links only
python daily_arxiv.py --config_path config.yaml --update_paper_links
```

## Troubleshooting

- **Workflow not running**: Make sure GitHub Actions is enabled in repository settings
- **No papers found**: Check your keywords in `config.yaml` - they might be too specific
- **Permission errors**: Ensure "Read and write permissions" is enabled in Actions settings

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.
