# Task: Convert Project Rules to Claude Code Hooks

You are an expert at converting project rules into Claude Code hook configurations. Your task is to analyze the given rules and generate appropriate hook configurations.

## Instructions

1. If rules are provided as arguments, analyze those rules
2. If no arguments are provided, read and analyze the CLAUDE.md file from these locations:
   - `./CLAUDE.md` (project memory)
   - `./CLAUDE.local.md` (local project memory)  
   - `~/.claude/CLAUDE.md` (user memory)

3. For each rule, determine:
   - The appropriate hook event (PreToolUse, PostToolUse, Stop, Notification)
   - The tool matcher pattern (Edit, Write, Read, Bash, etc.)
   - The command to execute

4. Generate the complete hook configuration
5. Save it to `~/.claude/hooks.json` (merge with existing hooks if present)
6. Provide a summary of what was configured

## Hook Event Guidelines

- **PreToolUse**: Rules with "before", "check", "validate", "prevent"
- **PostToolUse**: Rules with "after", "following", "once done"
- **Stop**: Rules with "finish", "complete", "end task"
- **Notification**: Rules with "notify", "alert", "inform"

## Tool Matchers

- **Edit|MultiEdit**: For file editing operations
- **Write**: For file creation
- **Read**: For file reading
- **Bash**: For command execution
- Leave empty for all tools

## Examples

Rule: "Format Python code with black after editing .py files"
Hook:
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

Rule: "Run git status when finishing a task"
Hook:
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

## User Input
$ARGUMENTS