# Claude MCP Servers Collection

![GitHub stars](https://img.shields.io/github/stars/saptechengineer/mcp?style=social)
![License](https://img.shields.io/badge/license-MIT-blue)

A professional collection of Model Calling Protocol (MCP) servers for enhancing Claude Desktop with external capabilities.

> ⭐ **If you find this project useful, please consider giving it a star on GitHub to show your support!** ⭐

## Overview

This repository contains MCP servers that extend Claude Desktop with additional capabilities:

- **Weather Service**: Get real-time weather information for any location
- **LinkedIn Profile Scraper**: Extract and analyze professional profiles from LinkedIn

*More MCP servers coming soon!*

## Project Structure

```
MCP/
├── linkedin/
│   ├── .venv/
│   ├── .env
│   ├── .gitignore
│   ├── linkedin.py
│   ├── pyproject.toml
│   └── uv.lock
├── weather/
│   ├── .venv/
│   ├── pyproject.toml
│   ├── requirements.txt
│   ├── uv.lock
│   └── weather.py
├── claude desktop config.png
└── README.md
```

## Prerequisites

- Python 3.9+ installed on your system
- Claude Desktop application
- Basic knowledge of command line operations

## Installation

### 1. Install UV

UV is a modern Python package installer and resolver that ensures fast, reproducible installations.

```bash
pip install uv
```

### 2. Verify UV Installation Path

Find the exact path where UV is installed:

```bash
where uv  # On Windows
which uv  # On macOS/Linux
```

Take note of this path as you'll need it for the configuration.

### 3. Clone the Repository

```bash
git clone https://github.com/yourusername/claude-mcp-servers.git
cd claude-mcp-servers
```

### 4. Set Up Each MCP Server

Each server is contained in its own directory with the necessary dependencies.

```bash
# For the weather service
cd weather
uv venv
uv pip install -r requirements.txt

# For the LinkedIn scraper
cd ../linkedin
uv venv
uv pip install -r requirements.txt
```

## Configuration

### Configure Claude Desktop

1. Open Claude Desktop
2. Navigate to: **File → Settings → Developer → Edit config**
3. Add the following MCP server configurations:

```json
{
    "mcpServers": {
        "weather": {
            "command": "C:/Users/yourusername/AppData/Local/Programs/Python/Python311/Scripts/uv",
            "args": [
                "--directory",
                "C:/path/to/your/MCP/weather",
                "run",
                "weather.py"
            ]
        },
        "linkedin_profile_scraper": {
            "command": "C:/Users/yourusername/AppData/Local/Programs/Python/Python311/Scripts/uv",
            "args": [
                "--directory",
                "C:/path/to/your/MCP/linkedin",
                "run",
                "linkedin.py"
            ]
        }    
    }
}
```

> 📝 **Note**: Replace the paths in the configuration with your actual paths.

## Usage

After completing the setup, you can start leveraging these powerful extensions with Claude Desktop:

### Weather Service

Ask Claude about the weather anywhere in the world:

```
What's the current weather in New York City?
Will it rain in London tomorrow?
What's the temperature forecast for Tokyo this week?
```

### LinkedIn Profile Scraper

Ask Claude to create detailed professional profile summaries:

```
Create a proper profile page with the details of https://www.linkedin.com/in/parthasap/
Summarize the career trajectory of https://www.linkedin.com/in/anyprofile/
What skills does https://www.linkedin.com/in/someprofile/ have?
```

## Contributing

Contributions are welcome! Here's how you can contribute:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add some amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

## Troubleshooting

If you encounter issues:

- Verify that all paths in the configuration are correct
- Ensure the Python scripts are executable
- Check if all dependencies are installed
- Review Claude Desktop logs for error messages
- Verify your `.env` files contain the necessary API keys

## Planned MCP Servers

We're actively developing additional MCP servers:

- Document Analysis Tool
- Calendar Integration
- Email Composition Assistant
- Code Repository Analyzer
- Data Visualization Tool

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgements

- [Anthropic](https://www.anthropic.com/) for creating Claude
- All contributors who have helped shape this project

---

<p align="center">
  <b>Made with ❤️ for the Claude community</b><br>
  <a href="https://github.com/saptechengineer/mcp">Star this repo</a> if you found it useful! Thank you! 🌟
</p>