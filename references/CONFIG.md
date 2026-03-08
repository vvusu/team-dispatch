# Team Dispatch Config (C option)

## Where

- Built-in default (single source): `~/skills/team-dispatch/config.json`

## Paths

- `paths.projectsRoot` (default: `~/work`)
  - Real code/projects live here.
  - Recommendation: agents create project folders like: `~/work/<project>`
- User override: `~/.openclaw/configs/team-dispatch.json`

Generate user override:
```bash
bash ~/skills/team-dispatch/scripts/setup-config.sh
```

## Goals

- Keep `agentId` portable and stable across machines.
- Allow per-agent presentation and notification routing:
  - `displayName` (human-friendly)
  - `username` (optional)
  - `notify.telegram.chatId` (optional)

## Notification policy

`notifyPolicy`:
- `failures-only` (recommended): only notify on `failed/timeout/blocked`
- `project-complete`: notify when project becomes `completed`
- `all-tasks`: notify on every task completion

## Telegram notification

Dispatcher-level behavior (not subagent):
- Based on `notifyPolicy`, when a task/project hits the matching state, the main agent reads config and sends a message to the configured Telegram chat.

Recommended payload:
- project name
- task id
- agentId + displayName
- status + short result/error
- deliverables (paths)

## Example
```json
{
  "team": {
    "agents": {
      "coder": {
        "displayName": "闪电",
        "notify": { "telegram": { "enabled": true, "chatId": "telegram:569110000" } }
      }
    }
  }
}
```
