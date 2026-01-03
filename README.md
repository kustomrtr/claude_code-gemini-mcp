# Claude Code + Gemini MCP Server

Connect Claude Code with Google's Gemini AI for powerful AI collaboration. Ask Gemini questions, get code reviews, and brainstorm ideas - all within Claude Code!

## 🚀 Quick Start (2 minutes)

### Prerequisites
- Python 3.8+ installed
- Claude Code CLI installed
- Google Gemini API key ([Get one free](https://aistudio.google.com/apikey))

### One-Line Install

```bash
curl -sSL https://raw.githubusercontent.com/RaiAnsar/claude_code-gemini-mcp/main/install.sh | bash
```

### Manual Install

1. **Clone this repo:**
```bash
git clone https://github.com/RaiAnsar/claude_code-gemini-mcp.git
cd claude_code-gemini-mcp
```

2. **Run setup with your API key:**
```bash
./setup.sh YOUR_GEMINI_API_KEY
```

That's it! 🎉

## 📖 Usage

Start Claude Code anywhere and use these commands:

```bash
claude

# Ask Gemini anything

mcp__gemini-collab__ask_gemini
  prompt: "Explain quantum computing in simple terms"

# Get code reviews
mcp__gemini-collab__gemini_code_review
  code: "def auth(u): return u.pwd == 'admin'"
  focus: "security"

# Brainstorm ideas
mcp__gemini-collab__gemini_brainstorm
  topic: "How to scale a web app to 1M users"

Or simply ask claude code to correlate with Gemini, it is not a rocket sciene... (Author's note) 
```

## 🛠️ What This Does

1. Installs the Google Gemini Python SDK
2. Sets up an MCP server that bridges Claude Code and Gemini
3. Configures it globally (works in any directory)
4. Provides tools for collaboration between Claude and Gemini

## 🔧 Available Tools

- **ask_gemini** - Ask Gemini any question
- **gemini_code_review** - Get security/performance code reviews
- **gemini_brainstorm** - Brainstorm ideas and solutions

## 📁 Installation Location

The server is installed at: `~/.claude-mcp-servers/gemini-collab/`

## 🐛 Troubleshooting

**MCP not showing up?**
```bash
# Check if it's installed
claude mcp list

# Reinstall with global scope
claude mcp remove gemini-collab
claude mcp add --scope user gemini-collab python3 ~/.claude-mcp-servers/gemini-collab/server.py
```

**Connection errors?**
- Check your API key is valid
- Ensure Python has `google-generativeai` installed: `pip install google-generativeai`

## Configuration

### API Key

Set your Gemini API key via environment variable:
```bash
export GEMINI_API_KEY=your_api_key_here
```

Or edit `~/.claude-mcp-servers/gemini-collab/server.py` directly.

### Model Selection

By default, the server uses `gemini-3-flash-preview`. To use a different model:

```bash
export GEMINI_MODEL=gemini-3-pro-preview
```

Available models ([full list](https://ai.google.dev/gemini-api/docs/models)):
- `gemini-3-pro-preview` - Latest, most capable
- `gemini-3-flash-preview` - Latest, fast and efficient
- `gemini-2.5-pro` - Stable production model
- `gemini-2.5-flash` - Stable, balanced performance
- `gemini-2.5-flash-lite` - Stable, lightweight
- `gemini-2.0-flash` - Previous generation

## 🤝 Contributing

Pull requests welcome! Please keep it simple and beginner-friendly.

## 📜 License

MIT - Use freely!

---

Made with ❤️ for the Claude Code community
