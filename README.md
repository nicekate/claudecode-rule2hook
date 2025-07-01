# claudecode-rule2hook 🪝

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Compatible-blue.svg)](https://docs.anthropic.com/en/docs/claude-code)

Convert natural language project rules into Claude Code hooks automatically! Write rules in plain English, and let Claude transform them into powerful automation hooks.

## ✨ Features

- 🎯 **Natural Language Processing** - Write rules in plain English
- 🔄 **Automatic Hook Generation** - Converts rules to proper hook configurations
- 🧠 **Smart Detection** - Intelligently identifies events, tools, and commands
- 📝 **CLAUDE.md Integration** - Reads from existing project memory files
- 🛡️ **Safe Configuration** - Backs up existing hooks before applying changes
- 🚀 **Zero Dependencies** - Works directly with Claude Code

## 📦 Installation

```bash
# Clone the repository
git clone https://github.com/zxdxjtu/claudecode-rule2hook.git
cd claudecode-rule2hook

# That's it! The slash command is ready to use
```

## 🚀 Quick Start

In Claude Code, type:

```bash
# Convert a single rule
/project:claudecode-rule2hook "Format Python files with black after editing"

# Convert rules from CLAUDE.md
/project:claudecode-rule2hook

# Convert multiple rules
/project:claudecode-rule2hook "Run tests after editing, Format code before committing"
```

## 📚 How It Works

1. **Input** - Provide rules as text or let Claude read from CLAUDE.md
2. **Analysis** - Claude analyzes rules to determine:
   - Trigger events (before/after actions)
   - Target tools (Edit, Write, Bash, etc.)
   - Commands to execute
3. **Generation** - Creates proper hook configurations
4. **Application** - Saves hooks to `~/.claude/hooks.json`

## 🎯 Examples

### Example 1: Code Formatting

**Input:**
```
Format Python files with black after editing
```

**Generated Hook:**
```json
{
  "hooks": {
    "PostToolUse": [{
      "matcher": "Edit|MultiEdit|Write",
      "hooks": [{
        "type": "command",
        "command": "black ."
      }]
    }]
  }
}
```

### Example 2: Git Workflow

**Input:**
```
Run git status when finishing a task
```

**Generated Hook:**
```json
{
  "hooks": {
    "Stop": [{
      "hooks": [{
        "type": "command",
        "command": "git status"
      }]
    }]
  }
}
```

## 📋 Supported Rule Patterns

- **Formatting**: `"Format [language] files after editing"`
- **Testing**: `"Run tests when modifying test files"`
- **Git**: `"Execute git [command] when [event]"`
- **Validation**: `"Check/Validate [something] before [action]"`
- **Notifications**: `"Alert/Notify when [condition]"`
- **Custom Commands**: Use backticks for specific commands

## 🛠️ Advanced Usage

### Reading from CLAUDE.md

Create a `CLAUDE.md` file with your project rules:

```markdown
# Project Rules

- Format Python files with black after editing
- Run tests before committing
- Check for TODO comments before pushing
```

Then run: `/project:claudecode-rule2hook`

### Complex Rules

```bash
/project:claudecode-rule2hook "Run 'npm run lint && npm test' after editing source files"
```

### Validation Rules

```bash
/project:claudecode-rule2hook "Validate JSON schema before saving .json files"
```

## 🧪 Testing

Use the included test tools:

```bash
# Interactive testing
./quick-test.sh

# Validate generated hooks
python3 validate-hooks.py

# Test specific rules
cat test-rules.txt
```

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Ways to Contribute

- 🐛 Report bugs
- 💡 Suggest new features
- 📝 Improve documentation
- 🔧 Submit pull requests
- 📢 Share your rule patterns

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Built for the [Claude Code](https://docs.anthropic.com/en/docs/claude-code) community
- Inspired by the need for simpler automation
- Thanks to all contributors!

## 📚 Resources

- [Claude Code Documentation](https://docs.anthropic.com/en/docs/claude-code)
- [Hooks Documentation](https://docs.anthropic.com/en/docs/claude-code/hooks)
- [Slash Commands Guide](https://docs.anthropic.com/en/docs/claude-code/slash-commands)
- [Memory Management](https://docs.anthropic.com/en/docs/claude-code/memory)

## 🔗 Links

- **Issues**: [GitHub Issues](https://github.com/zxdxjtu/claudecode-rule2hook/issues)
- **Discussions**: [GitHub Discussions](https://github.com/zxdxjtu/claudecode-rule2hook/discussions)
- **Wiki**: [Project Wiki](https://github.com/zxdxjtu/claudecode-rule2hook/wiki)

---

<p align="center">
  Made with ❤️ by the Claude Code community
</p>

<p align="center">
  <a href="https://github.com/zxdxjtu/claudecode-rule2hook/stargazers">⭐ Star us on GitHub!</a>
</p>