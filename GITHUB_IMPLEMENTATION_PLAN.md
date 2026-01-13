# GitHub Restructure Implementation Plan

> **Goal:** 142 repos → Clear story with 5 paths
> **Timeline:** Execute in phases, not dates
> **Principle:** The restructure itself demonstrates the thesis

---

## PHASE 0: BACKUP & PREPARE

### 0.1 Create Safety Net
```bash
# Create local backup of all repo metadata
gh repo list mordechaipotash --limit 200 --json name,visibility,description,url > ~/github_backup_142_repos.json

# Clone critical private repos locally (if not already)
cd ~/github-archive
gh repo clone mordechaipotash/Sparkii
gh repo clone mordechaipotash/sparkii-command-center
gh repo clone mordechaipotash/sparkii-rag-api
gh repo clone mordechaipotash/wotcfy_archive
```

### 0.2 Create Archive Organization
```bash
# Option A: Create a GitHub organization for archives
# Organization: mordechai-archive (keeps main profile clean)

# Option B: Use GitHub's archive feature
# Archived repos still exist but are clearly marked as inactive
```

---

## PHASE 1: GOLD EXTRACTION (Mine Before Restructure)

### 1.1 Extract from Sparkii Brain Dump

**Source:** `Sparkii/INTELLECTUAL_PROPERTY_CATALOG.md`
**Destination:** `bottleneck-principle/docs/05-innovations.md`

Content to extract:
- [ ] Hyperfocus Knowledge Onion System
- [ ] Force Ship at 80% System
- [ ] Context Preservation ($1000/switch)
- [ ] Fourth-Order Thinking

**Source:** `Sparkii/MORDECHAI_POTASH_COMPLETE_PROFILE.md`
**Destination:** `bottleneck-principle/docs/06-mordechainisms.md`

Content to extract:
- [ ] "Ship at 80% or Die at 0%" (325% improvement)
- [ ] "Invoice Before Code" (75% revenue capture)
- [ ] "Context Switches Cost $1000 Each"
- [ ] External Brain Prosthetic (90% context recovery)
- [ ] WOTCFY $3 vs $360 disruption story

### 1.2 Extract from sparkii-rag-api

**Source:** `sparkii-rag-api/README_04-11-25-17-20.md`
**Destination:** Update `intellectual-dna/README.md` with:

- [ ] Stella embeddings stats (MTEB #3 globally, 71.54 score)
- [ ] 287,672 items across platforms
- [ ] 94.8% average similarity (vs 52.2% old model)
- [ ] Multi-platform architecture diagram

### 1.3 Extract from wotcfy_archive

**Source:** `wotcfy_archive/pipeline_with_shapely_perfection/`
**Destination:** Create sanitized architecture doc for `enterprise-tax-credit-platform`

- [ ] Ultimate pipeline architecture
- [ ] Shapely/PostGIS patterns
- [ ] Webhook integration patterns

---

## PHASE 2: CONSOLIDATIONS

### 2.1 Thesis Suite (9 → 4 repos)

| Action | From | To | How |
|--------|------|-----|-----|
| KEEP | intellectual-dna | - | Already optimal |
| KEEP | brain-canvas | - | Already optimal |
| KEEP | bottleneck-principle | - | Add extracted content |
| KEEP | unpack | - | Already optimal |
| REDIRECT | thesis | unpack | Update README with redirect |
| MERGE | seedgarden | bottleneck-principle | Copy unique content |
| ARCHIVE | Shelet | - | `gh repo archive` |
| ARCHIVE | slim_SHELET | - | Keep private, archive |
| ARCHIVE | wotcfy_shelet | - | Keep private, archive |

```bash
# Redirect thesis to unpack
cd ~/repos/thesis
echo "# This repo has moved to [unpack](https://github.com/mordechaipotash/unpack)" > README.md
git add README.md && git commit -m "Redirect to unpack" && git push

# Merge seedgarden unique content into bottleneck-principle
# Manual: Copy any unique seeds/content not in bottleneck-principle

# Archive Shelet
gh repo archive mordechaipotash/Shelet --yes
```

### 2.2 Torah Suite (6 → 3 repos)

| Action | From | To | How |
|--------|------|-----|-----|
| KEEP | talmudic-study-app | - | Already optimal |
| KEEP | ohr-avraham-chaim | - | Already optimal |
| MERGE | jewtube + audiotube | torah-audio | Create new combined repo |
| KEEP PRIVATE | ask-rav-web | - | In progress |
| KEEP PRIVATE | Gemini-made-rav-b | - | In progress |
| ARCHIVE | jewish_jobs | - | Abandoned |

```bash
# Create torah-audio by merging jewtube and audiotube
gh repo create mordechaipotash/torah-audio --public --description "Audio-only YouTube for Torah learning. Shiurim without the video overhead."

# Clone both, merge best code into torah-audio
# Then archive originals:
gh repo archive mordechaipotash/jewtube --yes
gh repo archive mordechaipotash/audiotube --yes
```

### 2.3 Portfolio Suite (7 → 1 featured)

| Action | From | To | How |
|--------|------|-----|-----|
| KEEP | python-data-engineering-portfolio | - | Primary portfolio |
| MERGE | google-apps-script-portfolio | python-* or archive | Add as section |
| MOVE | ai-powered-learning-journey | Blog/About | Not a tool |
| ARCHIVE | portfolio-site | - | Superseded |
| ARCHIVE | mordechai-portfolio | - | Superseded |
| ARCHIVE | google-apps-script-portfolio-v2 | - | Duplicate |
| KEEP PRIVATE | aviva-portfolio | - | Client work |

```bash
# Archive redundant portfolio repos
gh repo archive mordechaipotash/portfolio-site --yes
gh repo archive mordechaipotash/mordechai-portfolio --yes
gh repo archive mordechaipotash/google-apps-script-portfolio-v2 --yes
```

### 2.4 WOTC Suite (62 → 4 working + archives)

**KEEP AS PRODUCTION (Private):**
- `wotcfy-app-production` - Main production app
- `wotc-processing-platform` - FastAPI microservices
- `sparkii-command-center` - Dashboard
- `sparkii-rag-api` - RAG system

**ARCHIVE ALL ITERATIONS:**
```bash
# Archive all wotc/tcs iterations (run for each)
for repo in wotcv8 wotcv9 wotcv9-helper-hub wotcfy wotcfy_app \
            wotcfy_shelet wotcfy-ez-service wotcfy-landing \
            wotcfy-monorepo wotcfy-partner-demo wotcfy-sh \
            wotcfy-unified wotcfy-webhook wotcfy_archive \
            tcs_app tcs_app_new tcsapp tcsprocessing tcs_railway \
            tcs-milestone tsc-data-entry tcs_19aug tcs_phaze1 \
            tcs-form-processing tcs-realtime-system; do
  gh repo archive "mordechaipotash/$repo" --yes 2>/dev/null || echo "Skipped $repo"
done
```

---

## PHASE 3: PROMOTIONS (Private → Public)

### 3.1 Promote sparkii-rag-api

**Pre-promotion checklist:**
- [ ] Remove any API keys from history
- [ ] Remove client-specific data references
- [ ] Update README with public-friendly framing
- [ ] Add MIT LICENSE

```bash
# Check for secrets
cd ~/repos/sparkii-rag-api
git log -p | grep -i "key\|secret\|password" | head -50

# If clean, make public
gh repo edit mordechaipotash/sparkii-rag-api --visibility public

# Update description
gh repo edit mordechaipotash/sparkii-rag-api \
  --description "Production RAG: 287K items, Stella embeddings (MTEB #3), multi-platform semantic search"
```

**New README structure:**
```markdown
# sparkii-rag-api

287,672 items. Stella embeddings. MTEB #3 globally.

> Unified semantic search across ChatGPT, Claude, and YouTube transcripts.

## Numbers

| Metric | Value |
|--------|-------|
| Items | 287,672 |
| Embedding Model | stella-en-1.5B-v5 |
| MTEB Score | 71.54 (#3 globally) |
| Avg Similarity | 94.8% |
| Query Speed | <100ms |

## Architecture
...
```

### 3.2 Consider Promoting sparkii-command-center

**Decision:** Likely keep private (contains client data patterns)
**Alternative:** Extract architecture docs → public blog post

---

## PHASE 4: PROFILE README UPDATE

### 4.1 New Profile Structure

```markdown
# Mordechai Potash

142 repos. 353K messages. 32K videos processed.

> "The bottleneck is the amplifier."

I compress complexity into choices you can make.

---

## 5 PATHS

### 1. RUN SOMETHING NOW
| Tool | Command | What |
|------|---------|------|
| brain-canvas | `npx brain-canvas` | Give any LLM a display |
| unpack | Paste JSON → type `unpack` | Portable thinking seeds |
| genui | `npx genui` | Gemini generates UI live |

### 2. QUERY MY BRAIN
**[intellectual-dna](https://github.com/mordechaipotash/intellectual-dna)**
353K messages → 30+ MCP tools → 256ms semantic search

### 3. SEE THE DATA ENGINEERING
**[youtube-transcription-pipeline](https://github.com/mordechaipotash/youtube-transcription-pipeline)**
32K videos · 41.8M words · Local Whisper · $0 API costs

**[sparkii-rag-api](https://github.com/mordechaipotash/sparkii-rag-api)**
287K items · Stella embeddings · MTEB #3 globally

### 4. SEE PRODUCTION SYSTEMS
**[enterprise-tax-credit-platform](https://github.com/mordechaipotash/enterprise-tax-credit-platform)**
PostGIS · AI extraction · 86-column federal compliance

**[audio_wotc_unemployment_verification](https://github.com/mordechaipotash/audio_wotc_unemployment_verification)**
$200K+ generated · Built in 1 week · Multi-tenant

### 5. UNDERSTAND THE THESIS
**[bottleneck-principle](https://github.com/mordechaipotash/bottleneck-principle)**
The framework: ∞ → compression → 5 choices → human decides → AI executes

---

## The Depth (on request)

```
142 total repos (15 public, 35 working, 92 archived)
62 WOTC system iterations → 4 production systems
3 years of AI conversations → queryable in 256ms
```

The public repos are the compression. The private repos are the proof.

---

## Stack

```
MCP · LanceDB · DuckDB · Parquet · Stella embeddings
Next.js · FastAPI · Supabase · PostGIS · Railway
```

---

*Beit Shemesh, Israel · Open to async work*
```

### 4.2 Implementation

```bash
# Update profile README
cd ~/repos/mordechaipotash
# Edit README.md with above content
git add README.md
git commit -m "Restructure profile: 142 repos → 5 clear paths"
git push
```

---

## PHASE 5: CLEANUP & ARCHIVE

### 5.1 Mass Archive Script

```bash
#!/bin/bash
# archive_repos.sh - Archive non-essential repos

ARCHIVE_LIST=(
  # StackBlitz experiments
  "citycar" "sb1-8sg9z5" "donor_v4"

  # Abandoned/empty
  "new" "html" "watc-app" "lang_cloud" "lang_cloud_private"

  # Old iterations
  "wotcv8" "wotcv9" "8550_formv2" "8850_form"

  # Superseded portfolios
  "portfolio-site" "mordechai-portfolio"

  # Duplicate boilerplates
  "nextjs-with-supabase1" "0605-supabase-boilerplate"
  "sprakii-boilerplate" "sparkii-boilerplate"
)

for repo in "${ARCHIVE_LIST[@]}"; do
  echo "Archiving $repo..."
  gh repo archive "mordechaipotash/$repo" --yes 2>/dev/null || echo "Failed: $repo"
done
```

### 5.2 Rename for Clarity (Optional)

```bash
# Consider renaming for consistency
gh repo rename mordechaipotash/QinFeedback qin-feedback
gh repo rename mordechaipotash/Sparkii sparkii-brain-dump  # if keeping
```

---

## PHASE 6: VERIFY & DOCUMENT

### 6.1 Final Inventory Check

```bash
# Count repos by visibility
gh repo list mordechaipotash --limit 200 --json visibility | jq 'group_by(.visibility) | map({visibility: .[0].visibility, count: length})'

# List all public repos
gh repo list mordechaipotash --limit 200 --public --json name,description | jq -r '.[] | "- \(.name): \(.description)"'

# List archived repos
gh repo list mordechaipotash --limit 200 --json name,isArchived | jq -r '.[] | select(.isArchived) | .name'
```

### 6.2 Update bottleneck-principle with results

Add to `bottleneck-principle/docs/07-meta-implementation.md`:

```markdown
# Meta: This Repo Restructure as Example

The restructure of 142 repos → 15 public demonstrates the thesis:

## Before (Chaos)
- 142 repos with no clear entry point
- 62 WOTC iterations (which one is production?)
- 7 portfolio attempts (which one to show?)
- Visitor paralysis

## After (Compression)
- 5 clear paths based on visitor intent
- Each path leads deeper on demand
- The depth exists but doesn't overwhelm
- Visitor agency preserved

## The Numbers
- Infinity (all possible code) → 142 repos
- 142 repos → 15 public (compression)
- 15 public → 5 paths (choice)
- 5 paths → 1 action (decision)
- 1 action → deep exploration (execution)

This is SHELET applied to GitHub.
```

---

## EXECUTION CHECKLIST

### Phase 0: Backup
- [ ] Export repo metadata JSON
- [ ] Clone critical private repos locally

### Phase 1: Gold Extraction
- [ ] Extract IP Catalog → bottleneck-principle
- [ ] Extract Mordechainisms → bottleneck-principle
- [ ] Extract Stella stats → intellectual-dna
- [ ] Extract pipeline patterns → enterprise-tax-credit-platform

### Phase 2: Consolidations
- [ ] Redirect thesis → unpack
- [ ] Merge seedgarden → bottleneck-principle
- [ ] Create torah-audio (merge jewtube + audiotube)
- [ ] Archive redundant portfolio repos
- [ ] Archive WOTC iterations

### Phase 3: Promotions
- [ ] Audit sparkii-rag-api for secrets
- [ ] Promote sparkii-rag-api to public
- [ ] Update sparkii-rag-api README

### Phase 4: Profile
- [ ] Write new profile README
- [ ] Push profile update

### Phase 5: Cleanup
- [ ] Run mass archive script
- [ ] Verify archive status

### Phase 6: Verify
- [ ] Final inventory count
- [ ] Document meta-implementation

---

## SUCCESS METRICS

| Metric | Before | After | Target |
|--------|--------|-------|--------|
| Public repos | 23 | 15-17 | Focused |
| Clear entry points | 0 | 5 | ✓ |
| Featured repos | None | 4 | ✓ |
| Archived repos | 0 | ~90 | Clean |
| Working private | 119 | ~35 | Manageable |
| Story clarity | Low | High | ✓ |

---

## ROLLBACK PLAN

If something goes wrong:

```bash
# Unarchive a repo
gh repo unarchive mordechaipotash/REPO_NAME

# Make repo private again
gh repo edit mordechaipotash/REPO_NAME --visibility private

# Restore from backup JSON
# (metadata only - code is still in git history)
```

---

*Plan created: January 2026*
*Principle: The restructure demonstrates what it teaches*
