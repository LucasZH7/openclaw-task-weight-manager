# OpenClaw Task Weight Manager

An OpenClaw skill for managing multiple interleaved threads inside a single chat while protecting the mainline task.

Core idea:

- classify one noisy conversation into several threads
- assign weights instead of treating all turns equally
- lock onto the highest-value thread
- park interruptions instead of forgetting them
- periodically re-score and steer attention back to the mainline

## Skill path

- `openclaw-task-weight-manager/`

## Highlights

- Works as a plain skill with no external service
- Integrates cleanly with OpenClaw `HEARTBEAT.md`, `cron`, `memory`, and `session`
- Includes a bootstrap script to create a thread board and default heartbeat checklist

## Quick start

```bash
cd openclaw-task-weight-manager
python3 scripts/bootstrap_workspace.py
```

Then invoke the skill in OpenClaw with prompts such as:

- `使用 $task_weight_manager 重新加权当前对话`
- `使用 $task_weight_manager 锁定主线 30 分钟`
- `使用 $task_weight_manager 列出所有线程并告诉我现在为什么会偏题`

## Publish targets

- GitHub repository
- ClawHub skill registry

## Repository structure

- `openclaw-task-weight-manager/SKILL.md`
- `openclaw-task-weight-manager/agents/openai.yaml`
- `openclaw-task-weight-manager/references/`
- `openclaw-task-weight-manager/assets/`
- `openclaw-task-weight-manager/scripts/`
