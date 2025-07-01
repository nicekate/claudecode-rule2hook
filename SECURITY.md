# Security Policy

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| 1.0.x   | :white_check_mark: |
| < 1.0   | :x:                |

## Reporting a Vulnerability

We take the security of claudecode-rule2hook seriously. If you believe you have found a security vulnerability, please report it to us as described below.

### Please do NOT:
- Create a public GitHub issue for security vulnerabilities
- Post about it publicly before it's fixed

### Please DO:
- Email us at [INSERT SECURITY EMAIL]
- Include the word "SECURITY" in the subject line
- Provide detailed steps to reproduce the issue
- Allow us reasonable time to fix the issue before disclosure

### What to expect:
- Acknowledgment of your report within 48 hours
- Regular updates on our progress
- Credit in the fix announcement (if desired)

## Security Considerations

### Hook Execution
- Hooks run with full user permissions
- Always review generated hooks before applying
- Be cautious with rules that execute shell commands

### Best Practices
1. **Review Generated Hooks**: Always inspect the generated `hooks.json` before using
2. **Backup Configuration**: The tool automatically backs up existing hooks
3. **Test First**: Use the validation tools to verify hook configurations
4. **Limit Scope**: Be specific in your rules to avoid unintended matches

### Safe Usage Tips
- Don't blindly trust rules from untrusted sources
- Regularly review your active hooks
- Use specific tool matchers to limit hook scope
- Test hooks in a safe environment first

## Hook Security Guidelines

When writing rules that will become hooks:

1. **Avoid Sensitive Data**: Don't include passwords, tokens, or keys in rules
2. **Use Absolute Paths**: Be explicit about file locations
3. **Validate Input**: For complex commands, add validation
4. **Limit Permissions**: Run commands with minimal required permissions

## Audit Trail

claudecode-rule2hook maintains backups of previous configurations in:
```
~/.claude/hook-backups/
```

This allows you to:
- Review changes over time
- Restore previous configurations
- Audit hook modifications

Thank you for helping keep claudecode-rule2hook secure!