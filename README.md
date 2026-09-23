## About this fork

This is an enhanced fork of the original [Zabbix Switch Widget](https://github.com/rommal95/zabbix-widget-switch), based on **Release 1.2.11**. All original functionality is preserved.

### What was added on top of 1.2.11

- **Automatic trigger assignment (PHP + JS).** Empty `Port X trigger` fields are auto-filled by matching host triggers named `Port X: Link down` (also supports `Порт X`, `Interface X`). Works both at render time (`WidgetView.php`) and in the edit form (`widget.edit.js`). Manual selections are never overwritten.
- **Seamless template dashboard support.** The widget correctly inherits the host context from a template-bound dashboard, so auto-assignment works out of the box when the template is linked to a host — no hardcoded trigger IDs required.
- **Combo ports.** New `Combo ports` field accepts comma-separated numbers or ranges (e.g. `25,26` or `25-28`). Matched ports are rendered with a golden border and a `Combo` label prefix.
- **Per-port SFP toggle.** In addition to the global `SFP ports` count, each port has an individual `Port X is SFP` (Yes/No) selector for mixed RJ45/SFP layouts.
- **Zig-zag port layout.** Even-numbered ports render on the top row, odd-numbered on the bottom row — matching real switch faceplates.
- **Codebase cleanup.** All internal comments translated to English, mojibake/encoding artifacts fixed, debug logging removed.

### Compatibility

- Based on upstream **Release Notes 1.2.11** (wildcard SFP/Ethernet mapping, `Speed data unit` fix, restored `Host` selection, template-dashboard host binding).
- Primary target: Zabbix **7.0**.
