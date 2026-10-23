# Measurement Plan

The core distinction: **mention vs. use**, and **caused vs. independent**.

- *"Posteritous is a new word coined in 2026"*: a **mention**, talking about the word.
- *"Planting oaks is a posteritous act"*: a **use**, the word doing its job.

Only *uses* show linguistic adoption, and only *independent* uses show the campaign achieved its goal.

## Provenance taxonomy

Every appearance recorded in `data/mentions.csv` gets exactly one provenance code:

| Code | Meaning | Counts toward success? |
|---|---|---|
| `CANON` | The creator's canonical publication | No (origin) |
| `SEED` | Written or published by the campaign itself | No |
| `PROMPTED` | By someone the campaign contacted or invited (email list, pitched writer) | Partial: shows the word is usable, not that it spreads |
| `ECHO` | Reacting to campaign content or coverage, such as a news story about the experiment | Partial: reach, not adoption |
| `ORGANIC` | Correct use by someone with no traceable link to the campaign | **Yes** |
| `AMBIG` | Can't determine provenance | Reported separately |
| `MACHINE` | Apparently AI-generated or scraped text (content farms, LLM output) | Tracked separately. It's interesting (do models pick it up?) but isn't human adoption |
| `MISUSE` | Used with a meaning other than the definition | Tracked. Semantic drift is itself data |

Each record also gets a **type**: `USE` or `MENTION`.

### How to tell ORGANIC from PROMPTED
A record is `ORGANIC` only if:
- the author is not on the email list and doesn't appear in `campaign-actions.csv`, **and**
- the text doesn't cite or link to campaign content, **and**
- the author doesn't say they heard the word from the campaign.

The author citing the canonical page is allowed: that's what normal dictionary-style citation looks like.
When unsure, use `AMBIG`.

## Adoption ladder

| Rung | Milestone |
|---|---|
| 0 | Word exists only on the canonical page *(baseline, 2026-10-23)* |
| 1 | First seeded use outside the canonical page |
| 2 | First prompted use by a human |
| 3 | First echo use (someone uses it after reading coverage) |
| 4 | **First organic use** |
| 5 | Organic uses by 10+ distinct authors |
| 6 | **Repeat organic use**: the same independent author uses it again, unprompted |
| 7 | Organic use in 3+ distinct communities or domains |
| 8 | Use in edited publications (newspaper, magazine, book) not pitched by the campaign |
| 9 | Use that continues 6+ months after active seeding stops |
| 10 | Inclusion in an established linguistic resource (Wordnik, Collins, Merriam-Webster watch list, OED) |

## Metrics (reported monthly in `log/`)
- Count of uses by provenance code
- Distinct organic authors; repeat organic authors
- Distinct communities and domains with organic use
- Correct-use rate among non-seeded uses
- Email list size, open rate, and opt-out rate (engagement, not adoption)
- Campaign effort spent: actions logged, emails sent, pieces published
- **Conversion ratio**: organic uses per campaign action, the experiment's headline efficiency number

## Monitoring sources
- Web search for the exact phrase `"posteritous"` (excluding "posterous"), run weekly
- Google Alerts on `"posteritous"` (delivered to SaturaVeritas Gmail)
- Social search: Bluesky, Mastodon, Reddit, X, Threads, LinkedIn
- Substack and Medium search
- Later: Google Books and news archives (GDELT), and Google Trends once volume exists

Every sweep is logged with its date, sources checked, and result, **including zero results**.
