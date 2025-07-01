# Contributing to claudecode-rule2hook

First off, thank you for considering contributing to claudecode-rule2hook! 🎉

## 🤝 Code of Conduct

This project and everyone participating in it is governed by our [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

## 🎯 How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check existing issues as you might find out that you don't need to create one. When you are creating a bug report, please include as many details as possible:

- **Use a clear and descriptive title**
- **Describe the exact steps to reproduce the problem**
- **Provide specific examples to demonstrate the steps**
- **Describe the behavior you observed and what you expected**
- **Include your Claude Code version**

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion, please include:

- **Use a clear and descriptive title**
- **Provide a detailed description of the suggested enhancement**
- **Provide specific examples of how it would work**
- **Explain why this enhancement would be useful**

### Your First Code Contribution

Unsure where to begin? You can start by looking through these issues:

- Issues labeled `good first issue`
- Issues labeled `help wanted`

### Pull Requests

1. Fork the repo and create your branch from `main`
2. Make your changes
3. Ensure your code follows the existing style
4. Update documentation as needed
5. Issue that pull request!

## 📝 Contribution Guidelines

### Improving the Slash Command

The core of claudecode-rule2hook is the prompt in `.claude/commands/claudecode-rule2hook.md`. When improving it:

1. **Test thoroughly** - Ensure your changes work with various rule patterns
2. **Maintain clarity** - The prompt should be clear and unambiguous
3. **Add examples** - If adding new functionality, include examples
4. **Document changes** - Update README.md if behavior changes

### Adding Test Cases

New test cases are always welcome! Add them to:

- `test-cases.md` - For detailed test scenarios
- `test-rules.txt` - For quick test rules
- `examples/sample_rules.md` - For user-facing examples

### Improving Documentation

- Keep language clear and concise
- Add examples where helpful
- Ensure code blocks are properly formatted
- Update table of contents if adding sections

## 🔧 Development Process

1. **Create an issue** - Discuss your idea first
2. **Fork & branch** - Create a feature branch
3. **Make changes** - Follow the guidelines above
4. **Test** - Ensure everything works as expected
5. **Document** - Update relevant documentation
6. **Pull request** - Submit your PR with a clear description

### Branch Naming

- `feature/` - For new features
- `fix/` - For bug fixes
- `docs/` - For documentation updates
- `test/` - For test additions

Example: `feature/support-yaml-config`

## 📋 Checklist

Before submitting your PR, ensure:

- [ ] The slash command works correctly
- [ ] Documentation is updated if needed
- [ ] Test cases are added for new functionality
- [ ] Examples are provided for new features
- [ ] The PR description clearly describes changes

## 💡 Tips for Contributors

### Understanding the Architecture

claudecode-rule2hook is intentionally simple:

1. User invokes `/project:claudecode-rule2hook`
2. Claude receives the prompt from `claudecode-rule2hook.md`
3. Claude analyzes rules and generates hooks
4. Claude saves configuration to `~/.claude/hooks.json`

No external dependencies or complex logic needed!

### Testing Your Changes

1. Clone your fork locally
2. Make changes to `.claude/commands/claudecode-rule2hook.md`
3. Test with various rule inputs
4. Verify generated hooks work correctly

### Common Patterns

When adding support for new rule patterns:

1. Add detection logic to the prompt
2. Include examples in the prompt
3. Add test cases
4. Update documentation

## 🙏 Recognition

Contributors will be recognized in:

- The project README
- Release notes
- Special thanks section

## 💬 Questions?

Feel free to:

- Open an issue for discussion
- Start a GitHub Discussion
- Reach out to maintainers

Thank you for helping make claudecode-rule2hook better! 🚀