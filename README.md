# AI4Blockchain Arxiv Daily

<p align="center">
  <h1 align="center"><br><ins>AI4Blockchain-Arxiv-Daily</ins><br>Automatically Update AI & Blockchain Papers Daily using GitHub Actions</h1>
</p>

## Overview

This repository automatically crawls and updates papers from arXiv related to the intersection of **Artificial Intelligence** and **Blockchain** technologies. The system runs daily via GitHub Actions to fetch the latest research papers and update the repository.

## Features

- 🤖 **Automated Daily Updates**: Fetches new papers from arXiv every day
- 🔍 **Smart Filtering**: Focuses on AI and Blockchain intersection topics
- 📊 **Multiple Categories**: Covers AI+Blockchain, Smart Contracts & AI, Consensus & AI, DeFi & AI
- 🔗 **Code Links**: Automatically finds and links to GitHub repositories when available
- 📝 **Markdown Output**: Generates formatted README and web pages
- ⚙️ **CI/CD Integration**: Fully automated via GitHub Actions

## Categories

The repository tracks papers in the following categories:

1. **AI+Blockchain**: Core research on combining AI and blockchain technologies
2. **Smart Contracts & AI**: AI-powered smart contract analysis, detection, and optimization
3. **Blockchain Consensus & AI**: AI-enhanced consensus algorithms and federated learning on blockchain
4. **DeFi & AI**: Artificial intelligence applications in decentralized finance

## Usage

### Local Setup

1. Clone this repository:
```bash
git clone https://github.com/jhy-3/AI4Blockchain-arxiv-daily.git
cd AI4Blockchain-arxiv-daily
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Run the script:
```bash
python daily_arxiv.py --config_path config.yaml
```

### GitHub Actions Setup

The repository uses GitHub Actions for automated daily updates. To enable:

1. **Enable GitHub Actions**:
   - Go to Settings → Actions → General
   - Under "Workflow permissions", select "Read and write permissions"
   - Save the changes

2. **Enable Workflows**:
   - Go to Actions tab
   - Enable the workflows: "Daily Arxiv Update" and "Weekly Update Paper Links"
   - The daily workflow runs automatically at 00:00 UTC every day
   - The weekly workflow updates paper links every Monday

3. **Manual Trigger** (optional):
   - You can manually trigger workflows from the Actions tab

### Configuration

Edit `config.yaml` to customize:

- **Keywords**: Add or modify search keywords for different topics
- **Max Results**: Adjust the number of papers fetched per category
- **Output Paths**: Change where JSON and Markdown files are saved

Example configuration:
```yaml
keywords:
    "AI+Blockchain":
        filters: ["artificial intelligence blockchain", "machine learning blockchain"]
max_results: 10
```

## Project Structure

```
.
├── .github/
│   └── workflows/
│       ├── daily-update.yml          # Daily paper update workflow
│       └── weekly-update-links.yml   # Weekly link update workflow
├── docs/
│   ├── index.md                      # Web page (GitHub Pages)
│   ├── ai4blockchain-arxiv-daily.json # JSON data for README
│   └── _config.yml                    # Jekyll config for GitHub Pages
├── daily_arxiv.py                     # Main script
├── config.yaml                        # Configuration file
├── requirements.txt                   # Python dependencies
└── README.md                          # This file
```

## Output

The script generates:

- **README.md**: Main repository README with paper listings
- **docs/index.md**: Web page for GitHub Pages
- **JSON files**: Structured data for all papers

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Built on top of the arxiv API
- Inspired by [cv-arxiv-daily](https://github.com/Vincentqyw/cv-arxiv-daily)

