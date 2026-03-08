# Changelog

## v1.0.1 (2026-03-08)
- Publish to ClawHub (version bump only; content unchanged from v1.0.0)


## v1.0.0 (2026-03-07)
- 🌍 **Add i18n support (English/Chinese)** — Default English, switch via config
- 🌍 **添加国际化支持（中英文双语）** — 默认英文，可通过配置切换
- Add low-frequency watcher (event + scan fallback)
- Add per-agent configurable displayName/username + Telegram notify routing (configs/team-dispatch.json)
- Add doctor + baseline model shortcut
- Add postmortem template + troubleshooting docs
- Raise recommended concurrency to 10 (configurable)

### i18n Configuration / 国际化配置

```json
{
  "language": "zh"  // "en" for English, "zh" for Chinese
}
```

### Output Messages / 输出消息

| English | 中文 |
|---------|------|
| ✅ Project completed! | ✅ 项目完成！ |
| 📤 Dispatched to {agent} | 📤 已派发至 {agent} |
| ❌ Task failed: {reason} | ❌ 任务失败：{reason} |
| 📦 Final deliverables: | 📦 最终交付清单： |
| 🔎 Preview: {path} | 🔎 预览方式：{path} |

## v3.0 (2026-03-06)
- DAG-based dispatching, auto decomposition, retries/fallbacks, result injection
