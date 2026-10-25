# Evolve Scholarship Library

A community scholarship center for Evolve students and families — a verified library, an application tracker, a shared deadline calendar, and a private essay vault.

**Dashboard:** https://ladyfallona.github.io/Scholarship-library/ (after GitHub Pages is turned on)

| Dashboard tab | Lives in |
|---|---|
| Library | [`data/scholarships.json`](data/scholarships.json) in this repository |
| Scholarship Tracker | [Scholarship Tracker project](https://github.com/users/LadyFallonA/projects/9) — each application is an issue here labeled `application` |
| Calendar & Reminders | [Roadmap view](https://github.com/users/LadyFallonA/projects/9/views/2) plus downloadable `.ics` files with reminders |
| Essay Vault | Private repository `Scholarship-essays` |

## How families use it

1. **Find** an opportunity in the Library tab and open the official site to confirm eligibility.
2. **Track** it with the "+ Track" button. That opens a pre-filled issue: add the student code, then submit.
3. **Move** it along by changing the `status:` label — `interested`, `drafting`, `submitted`, `awarded`, `not selected`.
4. **Write** essays in the private Essay Vault, starting from the student's own story bank.
5. **Remember** deadlines by downloading the calendar file (reminders 14 and 3 days before).

## Privacy

This repository is public. Use student codes such as `EV-014` — never names, school IDs, contact details, financial information, or essays. Essays stay in the private vault.

## Adding or updating a scholarship

Anyone can use **Suggest a scholarship** or **Report a change** (Issues → New issue). A maintainer confirms the details on the sponsor's official page, then edits `data/scholarships.json`:

```json
{
  "id": "short-unique-id",
  "name": "Scholarship name",
  "sponsor": "Organization",
  "url": "https://official-page",
  "amount": "$5,000",
  "amount_value": 5000,
  "opens": "2026-11-01",
  "deadline": "2027-02-01",
  "date_note": "Anything families should know about the dates",
  "location": "National",
  "levels": ["HS Senior"],
  "tags": ["Financial need"],
  "eligibility": "Who can apply",
  "requirements": "What to submit",
  "essays": "Essay requirements",
  "effort": "Low | Medium | High",
  "renewable": false,
  "verified_on": "2026-10-25"
}
```

Dates use `YYYY-MM-DD`. Leave `opens` or `deadline` as `null` when the sponsor hasn't posted them. The dashboard works out "open", "opening soon", "closed", and "dates not posted" on its own.

## One-time setup

- **Labels:** Actions → *Set up tracker labels* → Run workflow (it also runs automatically on the first push).
- **Pages:** Settings → Pages → Deploy from branch → `main` / root.
- **Project fields** (Scholarship Tracker project): `Status` options *Interested, Drafting, Submitted, Awarded, Not selected*; date fields `Start` and `Deadline`; text fields `Student code` and `Award amount`. The Roadmap view uses `Start` → `Deadline`.
- **Optional automatic project sync:** create a classic personal access token with the `project` scope, then add it as a repository secret named `PROJECT_TOKEN`. New and edited application issues will then be added to the project with their deadline, student code, amount, and status filled in. Without the secret, add issues to the project by hand (or turn on the project's built-in *Auto-add to project* workflow).

Scholarship information is for planning only. Sponsors change rules and dates — always confirm on the official link. Never pay a fee to apply for a scholarship.

— EVOLVE, LLC · [evolvetoday.org](https://evolvetoday.org)
