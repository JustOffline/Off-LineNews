# Sources & Methodology

## How the tracker works

The BANNED tracker is a static GitHub Pages site that auto-updates daily via GitHub Actions. A Python script fetches free RSS feeds, filters articles by keyword, deduplicates them, and injects the top 12 most recent articles into `index.html`. No API keys. No database. No hosting costs.

---

## RSS Feed Sources

| Source | URL | Type |
|---|---|---|
| BBC Technology | `http://feeds.bbci.co.uk/news/technology/rss.xml` | General tech news |
| The Guardian Technology | `https://www.theguardian.com/technology/rss` | General tech news |
| Al Jazeera | `https://www.aljazeera.com/xml/rss/all.xml` | Global news |
| OONI (Open Observatory of Network Interference) | `https://ooni.org/post/index.xml` | Internet censorship research |
| Rest of World | `https://restofworld.org/feed/` | Global tech policy |
| EFF (Electronic Frontier Foundation) | `https://www.eff.org/rss/updates.xml` | Digital rights |
| TechCrunch | `https://techcrunch.com/feed/` | Tech industry news |
| Wired | `https://www.wired.com/feed/rss` | Tech + policy |
| Techdirt | `https://www.techdirt.com/techdirt_rss.xml` | Policy + free speech |
| NetBlocks | `https://netblocks.org/feed` | Real-time internet shutdowns |
| Freedom House | `https://freedomhouse.org/rss.xml` | Democracy + internet freedom |
| Access Now | `https://www.accessnow.org/feed/` | Digital rights |
| The Intercept | `https://theintercept.com/feed/?rss` | Investigative journalism |
| AP Technology | `https://feeds.apnews.com/apnews/technology` | Wire service |

---

## Keyword Filtering

Articles are included if their title or summary contains any of the following keywords:

- `social media ban / block`
- `platform ban / block`
- `tiktok ban / block / restrict`
- `twitter / x ban / block`
- `facebook / meta / instagram ban`
- `youtube / telegram / whatsapp ban`
- `internet shutdown / blackout / censorship`
- `online censorship / digital censorship`
- `DSA fine / digital services act`
- `online safety act / bill`
- `social media law / regulation`
- `content moderation law`
- `great firewall`
- `internet freedom`
- `VPN ban / encryption ban`
- `disinformation law / fake news law`
- `age verification / under-16 ban`

---

## Platform tracker methodology

The platform status cards in Section 1.0 are maintained manually in `index.html`. Status levels are:

| Badge | Meaning |
|---|---|
| **BANNED** | Platform is completely blocked by government order in the listed countries |
| **RESTRICTED** | Platform access is throttled, partially blocked, or requires VPN |
| **AT RISK** | Active legislation or legal proceedings that could result in a ban |
| **MONITORING** | Temporary bans or ongoing compliance disputes |

---

## Legislation tracker methodology

The bills and laws in Section 2.0 are maintained manually. Status levels:

| Status | Meaning |
|---|---|
| **Signed Law / Active / Passed** | Law is in force |
| **Pending / Stalled / Draft** | Bill has not yet passed |
| **Defeated** | Bill failed or was withdrawn |

---

## Update schedule

- **News section:** Auto-updated daily at 07:00 UTC via GitHub Actions
- **Platform tracker & legislation:** Updated manually — submit corrections via [GitHub Issues](../../issues)

---

## Contributing

Spotted an error, a missing ban, or a new law?

1. Open an [Issue](../../issues/new) with the details and a source link
2. Or submit a Pull Request editing `index.html` directly

All corrections must include a primary source link (government announcement, news wire, or credible journalism).
