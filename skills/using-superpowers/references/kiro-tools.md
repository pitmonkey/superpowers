# Kiro CLI Tool Mapping

Skills use Claude Code tool names. When you encounter these in a skill, use your platform equivalent:

| Skill references | Kiro CLI equivalent |
|-----------------|---------------------|
| `Skill` tool (invoke a skill) | slash command: `/skill-name` (e.g., `/brainstorming`) |
| `Read` (file reading) | built-in file reading |
| `Write` (file creation) | built-in file writing |
| `Edit` (file editing) | built-in file editing |
| `Bash` (run commands) | terminal / shell commands |
| `Grep` (search file content) | built-in search |
| `Glob` (search files by name) | built-in file search |
| `TodoWrite` (task tracking) | maintain a task list in chat |
| `WebSearch` | built-in web search |
| `WebFetch` | built-in URL fetch |
| `Task` tool (dispatch subagent) | `/agent` or inline subagent prompt |

## Invoking Skills

In Kiro CLI, skills are invoked via slash commands. The skill name becomes the command:

| If a skill says... | In Kiro, do this |
|---------------------|-----------------|
| `Skill("brainstorming")` | `/brainstorming` |
| `Skill("writing-plans")` | `/writing-plans` |
| `Skill("systematic-debugging")` | `/systematic-debugging` |
| `Skill("test-driven-development")` | `/test-driven-development` |
| `Skill("verification-before-completion")` | `/verification-before-completion` |
| `Skill("requesting-code-review")` | `/requesting-code-review` |

Kiro auto-discovers skills from `~/.kiro/skills/`. Skills may also auto-trigger when Kiro matches your request against skill descriptions — you do not always need to use the slash command explicitly.

## Subagent support

When a skill asks you to dispatch a subagent (via `Task` tool or `Agent` tool in Claude Code terms), use Kiro's `/agent` command or describe the delegation task inline in your response. Pass the full prompt from the skill's prompt template to the subagent.

For parallel subagent dispatch: request multiple `/agent` tasks together where skills allow independent parallel execution.
