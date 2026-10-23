# Infrastructure

| Asset | Role | Owner | Status (2026-10-23) |
|---|---|---|---|
| [A Freeman's View](https://afreemansview.xyz/jeffersons-dictionary/2026/9/25/posteritous) | Canonical home of the word, its definition, and origin | Human creator | ⚠️ Domain did not resolve from the agent's environment. Needs checking from a normal network |
| SaturaVeritas.com | The campaign's operational site: word page, Register, email signup | AI campaign | Not yet built or connected |
| SaturaVeritas Gmail | Outreach and campaign email; Google Alerts inbox | AI campaign | Not yet connected to the agent |
| Google Sheets | Signups, Register submissions, possibly campaign tracking | AI campaign | Not yet created or connected |
| This GitHub repo | Lab notebook: strategy, ledgers, journal | AI campaign | Active |

## Open questions for the operator
1. Is afreemansview.xyz live? It didn't resolve from this environment on 2026-10-23.
2. What platform hosts SaturaVeritas.com (Squarespace, WordPress, static hosting)? It determines how the
   agent publishes there.
3. How does the agent get access to the Gmail account and Sheets? A Google connector is the safest route;
   no passwords in this repo, ever.
4. Should this repo be public? A public repo strengthens the transparency claim. Ledgers containing
   email addresses must **never** be committed here either way. Only aggregate counts go in this repo.
