# BACKLOG.md

> Single source of work.
> Review regularly.
> Top item is next.

---

## NOW

- [ ] **Reddit source fix** - 401 errors in logs; Reddit fetcher broken. Fix before adding new sources

## BACKLOG

- [ ] **MCP server for AI agent queries** - Daemon service for prismis queries. High value for Graybeard Meetup. DEPENDS ON: daemon-mcp server updates first
- [ ] **Export to Obsidian** - Daily digest export to knowledge base (markdown format)
- [ ] **Better source error handling** - Improve daemon error recovery and retry logic
- [ ] **arXiv feed tuning** - High volume, filter by score/citations or time-based limits
- [ ] **Papers support (arXiv PDF)** - PDF ingestion beyond RSS metadata
- [ ] **Manual content ingestion** - One-off URLs/PDFs for ad-hoc analysis
- [ ] **OpenAI news workaround** - Direct RSS blocked (403). Use RSS-Bridge or custom fetcher
- [ ] **Anthropic official news** - No public RSS. Options: scrape blog, RSS-Bridge, or monitor r/ClaudeAI
- [ ] **Daemon process management (Linux)** - systemd service unit for prismis-daemon
- [ ] **Daemon process management (macOS)** - launchd plist for prismis-daemon
- [ ] **Twitter/X API for Boris feed** - Monitor @borispower. Requires Twitter API key ($100/mo)
- [ ] **GitHub trending projects briefing** - Curate relevant trending repos. Options: GitHub trending RSS, custom scraper, or GitHub API polling
- [ ] **Friends' daemon feeds** - Architecture for subscribing to friends' prismis instances. Need planning on auth, discovery, and feed format

## ROADMAP

- [ ] **Custom priority keywords** - Allow keyword-based priority boosting beyond context.md
- [ ] **Source grouping** - Organize sources into categories for filtered views
- [ ] **Notification tuning** - Different notification rules per source type

## DONE

- [x] **003-light-preference-learning** - Learned preferences from user feedback supplement LLM prioritization with 5-vote threshold [2026-01-27]
- [x] **002-feedback-storage** - Feedback statistics API endpoint with source/topic aggregation for preference learning [2026-01-27]
- [x] **001-webui-upvote-downvote** - Thumbs up/down buttons with toggle behavior, persisted to DB [2026-01-27]
- [x] **000-webui-collapse-duplicates** - Fuzzy title matching (80%+) in daemon API groups duplicates with count indicator [2026-01-27]
- [x] **Configure context.md with personal interests** - Curated from TELOS for AI/security/privacy priorities [2026-01-27]
- [x] **Add initial content sources** - 25 sources: Reddit (7), RSS/arXiv (14), YouTube (3), Podcast (1) [2026-01-27]
- [x] **Publish to service-dashboard** - Exposed via tailscale serve on port 5001 [2026-01-27]
- [x] **Configure 0.0.0.0 binding** - Enable LAN/Tailscale access [2026-01-27]
