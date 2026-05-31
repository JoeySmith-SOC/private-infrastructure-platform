# Logs

## Purpose

Store sanitized operational logs, summaries, and evidence records that support maintenance, procurement, incidents, and recovery testing.

## Folder Structure

| Path | Purpose |
|---|---|
| `logs/changes/` | Change summaries and maintenance outcomes |
| `logs/maintenance/` | Routine maintenance records |
| `logs/incidents/` | Incident reports and timelines |
| `logs/recovery-tests/` | Backup and DR validation evidence |
| `logs/procurement/` | Purchase and asset intake records |

## Standards

- Treat this folder as public-safe evidence and summaries, not as a dump of live system logs.
- Link log entries back to runbooks, lessons learned, and relevant architecture docs.
- Record dates, owners, results, and follow-up actions consistently.

