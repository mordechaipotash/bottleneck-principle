# Execution Tracker

## Quick Reference: The 5 Paths

```
PATH 1: RUN NOW      → brain-canvas, unpack, genui
PATH 2: QUERY BRAIN  → intellectual-dna
PATH 3: DATA ENG     → youtube-pipeline, sparkii-rag-api
PATH 4: PRODUCTION   → enterprise-tax-credit, audio_wotc
PATH 5: THESIS       → bottleneck-principle
```

---

## IMMEDIATE ACTIONS (Do First)

### Action 1: Backup
```bash
gh repo list mordechaipotash --limit 200 --json name,visibility,description,url > ~/github_backup_$(date +%Y%m%d).json
```
- [ ] Done

### Action 2: Audit sparkii-rag-api for Secrets
```bash
cd /path/to/sparkii-rag-api
git log -p --all | grep -iE "(sk-|api_key|secret|password|token)" | head -100
```
- [ ] Clean? Y/N
- [ ] Ready to promote? Y/N

---

## GOLD EXTRACTION TASKS

### From Sparkii Brain Dump

| Source File | Extract To | Status |
|------------|-----------|--------|
| `INTELLECTUAL_PROPERTY_CATALOG.md` | `bottleneck-principle/docs/05-innovations.md` | [ ] |
| `MORDECHAI_POTASH_COMPLETE_PROFILE.md` | `bottleneck-principle/docs/06-mordechainisms.md` | [ ] |
| `TORAH_BOOK_IDEAS.md` | Personal archive | [ ] |

**Key extractions:**
- [ ] Hyperfocus Knowledge Onion System
- [ ] Force Ship at 80% System
- [ ] Context Preservation ($1000/switch)
- [ ] WOTCFY $3 vs $360 story
- [ ] 325% completion improvement stat
- [ ] 90% context recovery stat

### From sparkii-rag-api

| Content | Extract To | Status |
|---------|-----------|--------|
| Stella MTEB #3 stats | `intellectual-dna/README.md` | [ ] |
| 287K items architecture | Public showcase | [ ] |
| Multi-platform diagram | Docs | [ ] |

---

## REPO-BY-REPO ACTIONS

### PUBLIC REPOS (23 → 15)

| Repo | Action | New State | Done |
|------|--------|-----------|------|
| intellectual-dna | KEEP + UPDATE | Public Featured | [ ] |
| brain-canvas | KEEP | Public Featured | [ ] |
| unpack | KEEP | Public Featured | [ ] |
| bottleneck-principle | KEEP + EXPAND | Public Featured | [ ] |
| thesis | REDIRECT to unpack | Public Archived | [ ] |
| seedgarden | MERGE into bottleneck | Public Archived | [ ] |
| youtube-transcription-pipeline | KEEP | Public Proof | [ ] |
| enterprise-tax-credit-platform | KEEP | Public Proof | [ ] |
| genui | KEEP | Public Tool | [ ] |
| digital_8850 | KEEP | Public Domain | [ ] |
| audio_wotc_unemployment_verification | KEEP | Public Domain | [ ] |
| talmudic-study-app | KEEP | Public Domain | [ ] |
| ohr-avraham-chaim | KEEP | Public Domain | [ ] |
| jewtube | MERGE into torah-audio | Archived | [ ] |
| audiotube | MERGE into torah-audio | Archived | [ ] |
| QinFeedback | KEEP (niche) | Public Niche | [ ] |
| sparkii-scripts-archive | MAKE PRIVATE | Private | [ ] |
| pdf-extraction-dashboard | MAKE PRIVATE | Private | [ ] |
| aviva-sacred-studio | KEEP (client showcase) | Public | [ ] |
| ai-powered-learning-journey | ARCHIVE | Archived | [ ] |
| python-data-engineering-portfolio | KEEP | Public Proof | [ ] |
| google-apps-script-portfolio | ARCHIVE | Archived | [ ] |
| mordechaipotash | UPDATE README | Public Profile | [ ] |

### PRIVATE → PUBLIC (Promotions)

| Repo | Pre-checks | Status |
|------|-----------|--------|
| sparkii-rag-api | Secrets audit, README update | [ ] Ready |

### PRIVATE → ARCHIVED (Mass Archive)

**WOTC Iterations (Archive all):**
```
wotcv8, wotcv9, wotcv9-helper-hub, wotcfy, wotcfy_app,
wotcfy_shelet, wotcfy-ez-service, wotcfy-landing,
wotcfy-monorepo, wotcfy-partner-demo, wotcfy-sh,
wotcfy-unified, wotcfy-webhook, webhook-1-gemini,
webhook-2-claude, wotcfy-webhook
```
- [ ] All archived

**TCS Iterations (Archive all):**
```
tcs_app, tcs_app_new, tcsapp, tcsprocessing, tcs_railway,
tcs-milestone, tsc-data-entry, tcs_19aug, tcs_phaze1,
tcs-form-processing, tcs-realtime-system, TCS, TCS_natan_abba,
tcs-sparkii, TCS-Microservice-App
```
- [ ] All archived

**Experiments/Boilerplate (Archive all):**
```
citycar, sb1-8sg9z5, donor_v4, new, html, watc-app,
nextjs-with-supabase1, 0605-supabase-boilerplate,
sprakii-boilerplate, sparkii-boilerplate, next-js-and-shadcn-ui-admin-dashboard,
nextjs-ai-chatbot, obsidian-alternative
```
- [ ] All archived

**Superseded (Archive all):**
```
portfolio-site, mordechai-portfolio, google-apps-script-portfolio-v2,
aviva-portfolio (keep private, client), 8550_formv2, 8850_form
```
- [ ] All archived

---

## PROFILE README DRAFT

Final content to push:

```markdown
# Mordechai Potash

142 repos. 353K messages. 32K videos. One thesis.

> "The bottleneck is the amplifier."

I compress complexity into choices you can make.

---

## 5 PATHS

### 1. RUN SOMETHING NOW
```
npx brain-canvas     → Give any LLM a display
paste → unpack       → Activate a seed in any LLM
npx genui            → Gemini generates UI live
```

### 2. QUERY MY BRAIN
[**intellectual-dna**](https://github.com/mordechaipotash/intellectual-dna)
353K messages · 30+ MCP tools · 256ms semantic search

### 3. SEE THE DATA ENGINEERING
[**youtube-transcription-pipeline**](https://github.com/mordechaipotash/youtube-transcription-pipeline)
32K videos · 41.8M words · Local Whisper · $0 API

[**sparkii-rag-api**](https://github.com/mordechaipotash/sparkii-rag-api)
287K items · Stella embeddings · MTEB #3 globally

### 4. SEE PRODUCTION SYSTEMS
[**enterprise-tax-credit-platform**](https://github.com/mordechaipotash/enterprise-tax-credit-platform)
PostGIS · AI extraction · 86-column federal compliance

[**audio_wotc_unemployment_verification**](https://github.com/mordechaipotash/audio_wotc_unemployment_verification)
$200K+ generated · Built in 1 week · Multi-tenant

### 5. UNDERSTAND THE THESIS
[**bottleneck-principle**](https://github.com/mordechaipotash/bottleneck-principle)
∞ → compression → 5 choices → human decides → AI executes

---

## The Depth

```
142 repos (15 public · 35 working · 92 archived)
62 WOTC iterations → 4 production systems
3 years of AI → queryable in 256ms
```

The public repos are the compression.

---

*Beit Shemesh, Israel · Open to async work*
```

- [ ] Content finalized
- [ ] Pushed to GitHub

---

## VERIFICATION COMMANDS

After all changes:

```bash
# Count by visibility
gh repo list mordechaipotash --limit 200 --json visibility | \
  jq 'group_by(.visibility) | map({v: .[0].visibility, n: length})'

# List public repos
gh repo list mordechaipotash --public --json name -q '.[].name'

# List archived
gh repo list mordechaipotash --limit 200 --json name,isArchived | \
  jq '[.[] | select(.isArchived)] | length'

# Verify profile
open https://github.com/mordechaipotash
```

---

## FINAL COUNTS TARGET

| Category | Target |
|----------|--------|
| Public Featured | 4-5 |
| Public Proof | 4-5 |
| Public Domain | 3-4 |
| Public Total | ~15 |
| Private Working | ~35 |
| Archived | ~90 |
| Total | 142 |

---

## NOTES

Space for tracking issues/decisions during execution:

```
[Date] Note:
-
```
