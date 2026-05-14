## 2026-05-14 — Verification pass on the Workday-adjacent rows.

The bucketing pass left 10 rows in (or near) the Workday bucket at Medium confidence — the research agents had inferred Workday without seeing a `myworkdayjobs` URL directly. Ran a verification pass with direct search + page fetches. 9 of 10 resolved:

- **Confirmed Workday (6):** Bank of America (`ghr.wd1`), Nike (`nike.wd1/nke`), World Kinect (`wfscorp.wd5/wfscareers`), Cleveland-Cliffs (`aksteel.wd1` — legacy AK Steel tenant name), Discover (`discover.wd5`), ConocoPhillips (`conocophillips.wd1/External` — page fetch confirmed, upgraded Medium→High).
- **URL was wrong (1):** Loews — the file had the *hotels subsidiary* tenant. The Fortune 250 entity is Loews Corporation: `loewscorp.wd1.myworkdayjobs.com/loewscorp`. Still Workday, just the wrong site.
- **Misbucketed — not Workday (2):** AMD is **iCIMS** (`careers-amd.icims.com`, confirmed by fetch). Lincoln National is **SAP SuccessFactors** (`rmkcdn.successfactors.com` + `/go/` paths, confirmed by fetch). The original agent had also mis-assigned Lincoln the `ghr.wd1` URL — which is actually Bank of America's tenant. Two companies crossed.
- **Still open (1):** Phillips 66. `careers.phillips66.com/go/...` paths point to SAP SuccessFactors, but the direct fetch was declined, so it's unverified. Left in the Workday bucket flagged Low/UNVERIFIED.

Net: Workday 129 → 127. Lesson for the rest of the buckets — the agents' Medium-confidence Workday calls were right 7 times out of 9, but the 2 misses were confident-looking and would have wasted v1 integration effort. Any Medium row that v1 depends on gets a direct page fetch before it's trusted.

This session ran long (~4 hrs wall clock, mostly background agents + being away). Stopped here after writing the verification results into `ats-buckets.md`.

**What's next.** Resolve Phillips 66. Then the bigger open question still stands: decide whether Phenom/Avature get verified into the Workday bucket, and design the Workday discovery mechanism (tenant job-search API vs. per-tenant crawling).

## 2026-05-13 — New project. Scoped the job-hunt agent and bucketed the Fortune 250.

Workday-autofill-agent is done for now — the LinkedIn post went out, the tool works, that arc is closed. This is the next one.

**The idea.** An agent (maybe multi-agent) that combs job listings matching my skills, drafts tailored application materials, and gets my application in early — because the best roles get flooded and early applicants get seen before reviewer fatigue sets in. I'm a senior PM, 20+ years; I'm tired of doing this manually and I need an edge.

**The reframe I bought into.** My first instinct was "completely automate applying." Talked it through and backed off the fully-autonomous version. At senior level, volume isn't the edge — fit and positioning are, and a fully-roboticized application strips out the judgment that's the actual reason a senior PM gets a callback. Mass auto-apply optimizes me *down* the pile. So: automate everything up to the apply decision, keep me in the loop for the final submit. The edge becomes speed of detection + pre-drafted tailoring, not a submission bot. (Also dodges the ToS mess of bots submitting at scale.)

**Scope decided so far.**
- Discovery surfaces: LinkedIn + a targeted list of direct-from-company career sites.
- LinkedIn: don't scrape it — use LinkedIn's own job-alert emails as the feed. Legitimate, robust, no ToS fight. Tradeoff: slightly less real-time, but alerts fire fast enough.
- Company sites: target the Fortune 250 + a handful of one-offs.
- Workday-first wedge: build v1 against the Workday slice end-to-end (discovery → fit-score → draft → apply via the extension). Other vendors are v2+.
- The old workday-autofill-agent becomes the submission layer for Workday-hosted roles. Nice continuity.

**Today's work: bucketed the Fortune 250 by ATS vendor.** Pulled the Fortune 500 2025 ranking, took the top 250 (`data/fortune-250.md`), then ran 5 parallel research agents to identify each company's ATS by careers-page URL. Full result in `data/ats-buckets.md`. The headline:

- **Workday: 129 of 250 (52%)** — more than the next five vendors combined.
- Then a long tail: Oracle Cloud Recruiting 22, SAP SuccessFactors 20, Phenom 12, iCIMS 12, Oracle Taleo 11, Eightfold 8, SmartRecruiters 6, IBM BrassRing 3, Avature 2, Greenhouse 2, Custom/in-house 23.

This validates the Workday-first wedge hard. One integration covers more than half the target list — and it's the one integration I've already built tooling for. The clean-JSON vendors (Greenhouse, Lever, Ashby) I'd hoped for barely show up at this company size; the Fortune 250 is enterprise-ATS territory, exactly as expected.

Two caveats worth remembering. First, the research agents couldn't fetch raw page source, so the Medium/Low confidence rows need a manual verification pass — especially the ones near the Workday bucket. Second, Phenom and Avature are front-end layers that often sit on top of another ATS (frequently Workday) at the actual apply step — so the *effective* Workday number is probably higher than 129. A verification pass could push it past 135.

**Stepping away here.** Ben stepped away after the buckets were compiled. Repo is scaffolded (`README.md`, `.gitignore`, `data/fortune-250.md`, `data/ats-buckets.md`, this journal).

**Committed, pushed, public.** Came back, committed the scaffold (`c5ab303`, root commit on `main`) and pushed it to a new public GitHub repo: https://github.com/BenDay123/job-hunt-agent. Build-in-public from commit one this time — the bucketed Fortune 250 is the first thing visible.

**What's next.**
- Verification pass on the Medium/Low Workday-adjacent rows.
- Decide whether Phenom/Avature get verified into the Workday bucket.
- Confirm the Workday slice as the v1 target, then design the discovery mechanism — Workday tenant job-search API vs. per-tenant crawling.
