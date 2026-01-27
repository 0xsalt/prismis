# Prismis Project Guidelines

## Git Workflow

**CRITICAL: Always create feature branches BEFORE starting work.**

### Branch Naming Convention (3 numbered categories for spec-kit compatibility)

| Range | Purpose | Example |
|-------|---------|---------|
| `0xx-name` | Features (spec-kit workflow) | `010-weather-widget`, `001-upvote-downvote` |
| `3xx-name` | Fixes and polish | `300-ui-polish` |
| `5xx-name` | Research & POCs (never merge) | `500-vesselfinder-embed` |

**Note:** Spike branches (5xx) preserve experimental code for reference but are never merged to main. Document findings in `specs/` or `docs/`.

### Rules
- Never delete branches (preserve history)
- Never commit directly to main
- Always rebase before merge (ensures linear history)
- Fast-forward merges only (no merge commits)

### Complete Workflow

```bash
# 1. Create feature branch FIRST
git checkout main && git pull
git checkout -b NNN-feature-name

# 2. Make changes, commit
git add <files>
git commit -m "feat: description"

# 3. When ready to merge - rebase first
git fetch origin
git rebase origin/main
# (resolve conflicts if any)

# 4. Merge to main (fast-forward only)
git checkout main && git pull
git merge NNN-feature-name --ff-only

# 5. Push
git push origin main

# 6. Return to feature branch for continued work
git checkout NNN-feature-name
```

**Key:** `--ff-only` fails if merge would create a merge commit. If it fails, rebase your feature branch first.

## Service Management

Prismis is a **native daemon** (not Docker-based), managed via the project Makefile.

### Ports
- **Local port: 8989** (fixed)
- **Tailscale port: dynamic** (assigned by service-dashboard, currently 5001)

### Start/Stop/Restart

```bash
cd ~/local/projects/prismis

# Start
make start

# Stop
make stop

# Restart (after code changes)
make restart
```

### Reinstalling After Code Changes

When code is modified, the daemon must be reinstalled:

```bash
cd ~/local/projects/prismis/daemon
uv tool install . --python 3.13 --reinstall

# Then restart the daemon
make restart
```

**DO NOT** use arbitrary ports or run `prismis-daemon &` directly without proper Makefile flow.

## Service Dashboard Integration

Prismis is registered in the PAI service-dashboard system:
- Registry: `~/.claude/skills/ServiceDashboard/skill/Assets/service-registry.yaml`
- Access via Tailscale: `https://the-commons.taila8bee6.ts.net:{port}`
- Port is auto-discovered - do NOT hardcode Tailscale port references

### Health Checks

```bash
# Local
curl http://localhost:8989/health

# Via service-dashboard
bun ~/.claude/skills/ServiceDashboard/Tools/check-health.ts
```

## Configuration

- Config: `~/.config/prismis/config.toml`
- Context: `~/.config/prismis/context.md`
- Data: `~/.local/share/prismis/`
- Database: `~/.local/share/prismis/prismis.db`

## Development Workflow

1. Create feature branch from main
2. Make changes
3. Reinstall daemon: `cd daemon && uv tool install . --python 3.13 --reinstall`
4. Restart: `make restart` (or stop/start)
5. Test on localhost:8989
6. Verify via Tailscale if needed
7. When approved, merge to main
