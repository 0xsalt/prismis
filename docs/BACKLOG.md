# BACKLOG.md

> Single source of work.
> Review regularly.
> Top item is next.

---

## NOW

- [ ] **000-webui-collapse-duplicates** - Collapse duplicate items (Top 3 vs main list) with count indicator instead of filtering
- [ ] **001-webui-upvote-downvote** - Add thumbs up/down buttons for user feedback on content relevance
- [ ] **002-feedback-storage** - Store user feedback in DB (expand interesting_override or new field)
- [ ] **003-light-preference-learning** - Use stored feedback to adjust LLM prioritization via prompt context

## BACKLOG

- [ ] **Twitter/X API for Boris feed** - Monitor Anthropic co-founder @borispower for AI insights. Requires Twitter API key setup and prismis twitter source support
- [ ] **GitHub trending projects briefing** - Curate relevant trending repos. Options: GitHub trending RSS, custom scraper, or GitHub API polling. Need strategy discussion
- [ ] **OpenAI news workaround** - Direct RSS blocked (403). Options: RSS-Bridge, different URL, or custom fetcher
- [ ] **Anthropic official news** - No public RSS. Options: scrape blog, RSS-Bridge, or monitor r/ClaudeAI
- [ ] **Friends' daemon feeds** - Architecture for subscribing to friends' prismis instances. Need planning on auth, discovery, and feed format
- [ ] **Test alternative LLM providers** - Compare gpt-4o-mini vs Claude Haiku vs Groq for quality/speed/cost tradeoffs
- [ ] **Reddit source tuning** - Adjust max_comments and filtering based on signal-to-noise ratio
- [ ] **arXiv feed tuning** - High volume, may need filtering by score/citations or time-based limits

## ROADMAP

- [ ] **Custom priority keywords** - Allow keyword-based priority boosting beyond context.md
- [ ] **Source grouping** - Organize sources into categories for filtered views
- [ ] **Notification tuning** - Different notification rules per source type
- [ ] **Export to Obsidian** - Daily digest export to knowledge base

## DONE

- [x] **Configure context.md with personal interests** - Curated from TELOS for AI/security/privacy priorities [2026-01-27]
- [x] **Add initial content sources** - 25 sources: Reddit (7), RSS/arXiv (14), YouTube (3), Podcast (1) [2026-01-27]
- [x] **Publish to service-dashboard** - Exposed via tailscale serve on port 5001 [2026-01-27]
- [x] **Configure 0.0.0.0 binding** - Enable LAN/Tailscale access [2026-01-27]
