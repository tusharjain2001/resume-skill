# Job Search Context — handoff notes

Written 25 October 2026 so this work can continue in a fresh chat on another machine.
Read this first, then ask me what has changed since.

> Note: this file is in a **public** GitHub repo, so it deliberately leaves out phone
> number, salary expectations and anything else that should not be world-readable.
> Contact details are on the resume PDF (see *Files* below).

---

## 1. Who I am

- **Tushar Jain**, Frontend Developer, based in Bahadurgarh, Haryana (Delhi NCR).
- **B.Tech Computer Science**, Amity University Noida, 2020–2024.
- **~2 years of professional experience.** Target roles asking **0–3 years**. Not senior/lead.
- Portfolio: https://tusharjainportfolio.vercel.app/ · GitHub: https://github.com/tusharjain2001

### True work history (use these dates everywhere — older resumes had wrong ones)

| Period | Role | Notes |
|---|---|---|
| Sep 2024 – Sep 2025 | Software Engineer (Frontend), **RRhai Tech** (later renamed **Monkify.ai**) | Led 4 developers on an AI hiring platform. Frontend only — no backend work there. |
| Dec 2025 – Apr 2026 | Frontend Developer, **KreoApp** (UK, remote) | Frontend of a live decentralized exchange (Kreo.App). ~50% faster rendering, ~60% of the codebase refactored, Chrome extensions. |
| Apr 2026 – present | **Freelance** (Upwork + direct clients) | 20+ projects, 100% Job Success Score, 5.0 across 10 Upwork contracts. Some Node.js/Express work here. |

**Why KreoApp ended:** the company found its business was not coming from the website and
let the **entire web development team** go. A company decision, not performance. Say that
plainly in interviews, mention "the whole team", and do not criticise them.

### Stack

- **Strong:** React.js, Next.js, TypeScript, JavaScript, Tailwind CSS, Redux, Zustand, REST APIs, performance work, Figma-to-UI.
- **Working knowledge:** Node.js, Express, MongoDB, Mongoose, JWT auth, Cloudflare R2.
- **Not my stack** (skip jobs that require them): Java, .NET, Python, Angular, Vue, PHP, React Native, Salesforce, Android/iOS.
- **Side project that proves full-stack:** **MyPageCraft** — a multi-tenant headless CMS.
  Live at https://mypagecraft.com, code at https://github.com/tusharjain2001/cms,
  `@mypagecraft/sdk` and `@mypagecraft/mcp` published on npm. Next.js dashboard, Express +
  MongoDB API, JWT with rotating refresh tokens, draft/publish with webhook revalidation,
  300+ tests. This is the strongest thing to show for full-stack roles.

---

## 2. What I am looking for

- **Role titles:** Frontend Developer / Frontend Engineer / React Developer / Next.js Developer / UI Developer / SDE-1 Frontend. Full-stack is fine when it is **React + Node**.
- **Experience band:** 0–3 years. Anything asking 4+ years is out.
- **Location:** remote (India or worldwide), or Delhi NCR — Gurgaon, Noida, Delhi — onsite/hybrid. Other Indian cities only if remote.
- **Niche worth using:** DEX / Web3 / trading-platform frontends — rare experience, much less competition. Weak spot: wagmi + viem (worth learning, ~a weekend).
- **Availability:** immediate joiner.

### Filters to apply to every search

Drop: senior/lead/staff/principal/architect/manager titles, 4+ years, internships, unpaid,
part-time, jobs under ~₹5 LPA, and other-stack roles from the list above. Keep only jobs
that genuinely state remote when searching for remote.

---

## 3. How the searches are run

Uses an **Apify** API token (mine; kept out of this file — ask me for it, and it is on a
$5/month free plan that resets around the 26th). Scripts live in the session scratchpad and
are rewritten when it gets cleared.

| Source | Actor | Notes |
|---|---|---|
| Company careers pages (ATS) | `fantastic-jobs/career-site-job-listing-api` | **Best source.** Jobs often not on LinkedIn/Naukri. `locationSearch: ['India']`, `aiWorkArrangementFilter: ['Remote OK','Remote Solely']`, `descriptionSearch: ['React']`. ~$0.012/job. |
| LinkedIn jobs | `curious_coder/linkedin-jobs-scraper` | Feed it search URLs: `geoId=102713980` (India), `f_WT=2` remote, `f_TPR=r86400` 24h / `r604800` 7 days. ~$0.002/job. |
| Naukri | `valig/naukri-jobs-scraper` | `wfhType:['2']` remote, `jobAge`, `experience:2`. Cheap. **Gotcha:** if the keyword contains "walk-in" it ignores the rest of the query. |
| LinkedIn people | `harvestapi/linkedin-profile-search` | Short mode, `currentCompanies` (company URLs) + `currentJobTitles`. ~$0.10 per 25 profiles. Used to find recruiters and hiring managers. |
| Genpact | Workday JSON endpoint, free | `POST https://genpact.wd108.myworkdayjobs.com/wday/cxs/genpact/External_Careers/jobs` with `{"searchText":"React","limit":20,"offset":0}`. |

**Dead ends — do not repeat:** RemoteOK, Remotive, Jobicy, Himalayas, We Work Remotely
(almost all US/EU-only or senior); Wellfound search results (mostly stale/404);
Glassdoor India (returned nothing); YC Work at a Startup (needs login, few public jobs).

**Rules learned the hard way**

1. **Never retype or complete a URL.** Copy it verbatim from the data and open it to check.
   I once hand-typed LinkedIn job IDs and the links opened unrelated jobs.
2. **Open every link before handing it over**; drop anything closed.
3. **Exclude everything already shown.** Keep the old CSVs and dedupe on company+title and URL.
4. Say when a batch is small instead of padding it with poor matches.

---

## 4. What has already been tried

- **Portals alone do not work.** Hundreds of applications since roughly March 2026, almost no replies. By late September I had already applied to essentially everything on LinkedIn and Naukri for this role, so board scraping mostly returns things I have seen.
- **What gets replies instead:** direct messages to founders, engineering managers and recruiters; referrals; and applying within 24–48 hours of a posting.
- **Resume was the first real problem, now fixed** (see Files). The old versions had two conflicting sets of dates, duplicated and unmeasurable metrics, no freelance work, no portfolio link, and a "Full Stack" title with no backend skills listed.
- **Walk-in interviews:** checked 652 Naukri walk-ins over 15 days — only 3 were developer roles, none React, none in NCR. Not a useful channel for this role. TCS is the exception; it runs developer walk-ins, mostly Bengaluru and Pune.
- **Service companies:** TCS has the most pure-React roles; Capgemini is mostly Java+React or .NET+React; **Genpact has nothing** for this stack (it is almost entirely F&A/BPO hiring).
  - TCS referrals need a **NextStep reference ID** — register at nextstep.tcs.com as *IT* first.
  - Capgemini referrals need the **job ID** from careers.capgemini.com (e.g. `1440336833`).
  - A friend has offered to refer me, so job IDs matter more than application links.

---

## 5. Files on the Windows laptop

| What | Where |
|---|---|
| Current resume (ATS-friendly, one page) | `Desktop\TUSHAR\Tushar_Jain_Frontend_Developer_Resume.pdf` |
| Latest apply list (29 jobs, 23 Oct) | `Desktop\TUSHAR\Job_Applications\APPLY_LIST_23_OCT.html` + `.csv` |
| Portfolio source | `Desktop\portfolio` — **its dates are still wrong** (says KreoApp Jan 2026, RRhai Oct 2024–Oct 2025, "Full Stack", "a year on a DEX"). Fix to match the table above. |
| MyPageCraft CMS source | `Desktop\cms` |

Earlier lists (recruiters, walk-ins, 15 Sep – 8 Oct job batches) were in `Desktop\Job_Leads`,
which got **deleted twice**, so outputs now go to `Desktop\TUSHAR\Job_Applications` instead.

---

## 6. How I like this work done

- **Discuss the plan in chat first**, then generate the file — not the other way round.
- Give me the **file/page to open**, not long link tables typed into chat.
- Be honest when a channel is not working; do not pad lists to look productive.
- **No bot auto-applying** on Naukri or LinkedIn. It breaks their terms, the ban risk is real, and screening questions break it anyway. Semi-automation is fine: open shortlisted jobs in my own browser, prepare answers to paste.
- Outreach messages: short connection note under 200 characters, longer message after they accept, 15–20 requests a day maximum.

---

## 7. Next steps

1. Apply to the remote jobs in `APPLY_LIST_23_OCT.csv`, careers-page ones first.
2. For each application, message one engineer or recruiter at that company.
3. Send my friend 2–3 TCS/Capgemini roles with their job IDs; register on NextStep.
4. Re-run the search every 2–3 days — being early matters more than volume.
5. Fix the portfolio dates so they match the resume.
6. Learn wagmi + viem, then add a connect-wallet demo to the portfolio to strengthen the Web3 angle.
