# Quick Start 🚀

## 1. Try It Now!

In Claude Code, type:

```
/project:claudecode-rule2hook "Format Python files after editing"
```

Claude will:
1. Analyze your rule
2. Generate a hook configuration
3. Save it to `~/.claude/hooks.json`
4. Show you what was configured

## 2. Use Your CLAUDE.md

If you have rules in CLAUDE.md, just type:

```
/project:claudecode-rule2hook
```

## 3. Common Rules

```
/project:claudecode-rule2hook "Run black on Python files after editing"
/project:claudecode-rule2hook "Execute git status when finishing tasks"
/project:claudecode-rule2hook "Run tests after modifying test files"
/project:claudecode-rule2hook "Check for TODO comments before committing"
```

## 4. Check Results

See your configured hooks:
```
cat ~/.claude/hooks.json
```

That's it! Your rules are now active hooks in Claude Code. 🎉