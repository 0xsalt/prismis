# Proposed Content Sources for Prismis

Based on TELOS interests: AI, Security, Privacy, Personal Infrastructure

---

## RSS Feeds

### AI & LLM
| Feed | URL | Notes |
|------|-----|-------|
| Anthropic Blog | https://www.anthropic.com/blog/rss.xml | Primary - Claude ecosystem |
| Simon Willison | https://simonwillison.net/atom/everything/ | LLM practitioner, tools |
| Hugging Face Blog | https://huggingface.co/blog/feed.xml | Models, papers |
| The Gradient | https://thegradient.pub/rss/ | AI research digest |

### Security
| Feed | URL | Notes |
|------|-----|-------|
| Krebs on Security | https://krebsonsecurity.com/feed/ | Investigative security |
| Schneier on Security | https://www.schneier.com/feed/atom/ | Security thinking |
| PortSwigger Research | https://portswigger.net/research/rss | Web security research |
| Project Zero | https://googleprojectzero.blogspot.com/feeds/posts/default | Vuln research |

### Developer/Infrastructure
| Feed | URL | Notes |
|------|-----|-------|
| Julia Evans | https://jvns.ca/atom.xml | Systems, debugging |
| Tailscale Blog | https://tailscale.com/blog/index.xml | Networking, self-host |
| Fly.io Blog | https://fly.io/blog/feed.xml | Edge, distributed |

---

## Reddit Subreddits

### AI
| Subreddit | Why |
|-----------|-----|
| r/LocalLLaMA | Self-hosted LLMs, quantization, inference |
| r/ClaudeAI | Claude-specific discussions, MCP |
| r/MachineLearning | Research papers, breakthroughs |

### Security
| Subreddit | Why |
|-----------|-----|
| r/netsec | Security research, CVEs |
| r/ReverseEngineering | Low-level security |
| r/AskNetsec | Practitioner discussions |

### Infrastructure
| Subreddit | Why |
|-----------|-----|
| r/selfhosted | Self-hosted tools, homelab |
| r/homelab | Infrastructure, experiments |

---

## YouTube Channels

| Channel | Handle | Why |
|---------|--------|-----|
| Computerphile | @Computerphile | CS fundamentals, clear explanations |
| LiveOverflow | @LiveOverflow | Security research, CTF |
| John Hammond | @_JohnHammond | Security, CTF, practical |
| Fireship | @Fireship | Dev news, concise |
| ThePrimeagen | @ThePrimeagen | Systems, performance, Rust |

---

## Priority Recommendations

**Start with (high signal):**
1. `reddit://r/LocalLLaMA` - Active, high-quality local AI discussion
2. `reddit://r/netsec` - Security research
3. Anthropic Blog RSS - Primary AI interest
4. Simon Willison RSS - Practical LLM content

**Add later (once tuned):**
- More RSS feeds for broader coverage
- YouTube channels (transcripts are token-heavy)
- More subreddits based on signal quality

---

## Commands to Add Sources

```bash
# High priority first
prismis-cli source add "reddit://r/LocalLLaMA" -n "Local LLM Community"
prismis-cli source add "reddit://r/netsec" -n "Network Security"
prismis-cli source add "https://www.anthropic.com/blog/rss.xml" -n "Anthropic Blog"
prismis-cli source add "https://simonwillison.net/atom/everything/" -n "Simon Willison"

# Security RSS
prismis-cli source add "https://krebsonsecurity.com/feed/" -n "Krebs on Security"
prismis-cli source add "https://www.schneier.com/feed/atom/" -n "Schneier on Security"

# Dev RSS
prismis-cli source add "https://jvns.ca/atom.xml" -n "Julia Evans"
prismis-cli source add "https://tailscale.com/blog/index.xml" -n "Tailscale Blog"

# More Reddit
prismis-cli source add "reddit://r/ClaudeAI" -n "Claude AI"
prismis-cli source add "reddit://r/selfhosted" -n "Self-Hosted"
```
