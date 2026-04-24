# Wiki Log

Append-only record of operations on this wiki. Most recent entries at the top.

#configuration 

---

## 2026-04-23 — Korean scaffolding pass complete (all 67 pages)

### What was done

Added **3-layer Korean scaffolding** to every page in `concepts/` (61) and `protocols/` (6):

1. **`> [!abstract]+ 한글 요약`** at top — expanded Korean overview of the entire page.
2. **`> *요약: ...*`** italic blockquote after each major section — section-level Korean paraphrase.
3. **`> [!tip]+ 핵심 정리`** before `## Related pages` — 6-bullet takeaway in Korean.

English body preserved intact. Tone maintained as declarative **~다** style throughout (no casual 야/거든/해). Technical terms kept in English + Korean translation in first occurrence.

### Execution order (6 batches)

- **Pilot (15)**: atopic-dermatitis, skin-barrier-dysfunction, filaggrin, th2-inflammation, pruritus, brain-skin-axis, gut-brain-axis, vagus-nerve, sleep-architecture, rem-sleep, slow-wave-sleep, stress-response, interoception, hpa-axis, adhd.
- **Batch A (14)** — AD molecular/treatment: epithelial-alarmins, tslp, il-4-and-il-13, il-31, jak-stat-signaling, ige, atopic-dermatitis-mental-health, sleep-disturbance-in-atopic-dermatitis, dupilumab, skin-microbiome, gut-skin-axis, leaky-gut, zonulin, dysbiosis.
- **Batch B (10)** — gut-brain/microbiome: gut-microbiome, short-chain-fatty-acids, fecal-microbiota-transplantation, probiotics, irritable-bowel-syndrome, multiple-sclerosis, autism-spectrum-disorder, t-regulatory-cells, th17-cells, microbial-cloud.
- **Batch C (7)** — ANS/stress/meditation: autonomic-nervous-system, sympathetic-nervous-system, parasympathetic-nervous-system, active-inference-and-chronic-pain, acupuncture, inner-communication-meditation, forgiveness-and-self-compassion.
- **Batch D (12)** — sleep: two-process-model-of-sleep, circadian-rhythm, melatonin, glymphatic-system, dreams, lucid-dreaming, nightmares, rem-sleep-behavior-disorder, sleep-apnea, insomnia, zolpidem, sleep-position-and-brain-clearance.
- **Batch E (3)** — cognition/ADHD: cognitive-overload, deep-work, adhd-strengths-framework.
- **Batch F (6)** — protocols: exercise-with-eczema, parasympathetic-activation, gut-health-diet, sleep-hygiene-protocol, digital-minimalism-protocol, meditation-practice.

### Final state

- **67/67 pages scaffolded** (concepts 61 + protocols 6).
- **0 broken wiki-links** across the whole wiki.
- Average page now has **1 abstract + 4–8 section summaries + 1 tip callout**.

### Design decisions

- User feedback earlier: "영어를 주로 하는 것은 유지하되, 한글로 도움을 받는 게 장기적으로 가장 좋을 것 같아." The scaffolding pattern honors that — English stays as primary body, Korean provides comprehension scaffolding at three zoom levels (page → section → bullet).
- **Tone consistency**: Before starting, user set "건조한 ~다. 같은 문체". Every 요약 uses declarative forms. No casual endings.
- **Evidence annotations preserved**: `[검증 필요]` marks and source/evidence-level citations survive intact; Korean summaries include them where load-bearing.
- **Batch sizing driven by cluster coherence**, not page count: ADs grouped together so terminology (Th2·Th17·Treg·IL-31) cross-reference naturally within one reading session.

### Known limitations of the scaffolding

- Single-source/promotional-heavy flags in original pages are still present; Korean summaries faithfully note "증거 약함", "홍보성", `[검증 필요]`.
- Korean summary for very long pages (e.g. sleep-hygiene-protocol, insomnia, dreams) is correspondingly long — expected.

---

## 2026-04-23 — Session 3 (final): Sleep + psych/cognition/stress (10 sources, final 1/3)

### Design decisions this session

- User asked for final 10 with "quality first" emphasis — took extra care on evidence annotations and caveats where sources were promotional.
- Two tight subclusters: sleep (6) and psych/cognition/stress (4). Resisted temptation to split hub concepts further (e.g. `rem-sleep-behavior-disorder` stayed as one page rather than splitting parkinsonism conversion into its own node).
- **Cross-cluster linking**: used the psych/cognition concepts to strengthen existing AD infrastructure — notably `active-inference-and-chronic-pain` is positioned to connect to `pruritus` as a central-itch framework, and `cognitive-overload` / `deep-work` connect to `adhd`.
- **Promotional-source hygiene**: two sources were heavily promotional (Ancient Sleep Position, Neuroscience Weakens Brain). Extracted the real underlying biology; flagged the hype explicitly in-page.
- **Korean sources**: kept English for concept names, added Korean aliases. Preserved specific Korean terms in aliases when they are the way the user would naturally search (e.g. 내면소통, 자기 긍정, 꿈잠).

### Sources ingested

From `1. RAW/0.1. Youtube Transcripts/`:

1. `Scientists Can't Explain Why This Ancient Sleep Position Reverses Brain Aging Overnight.md`
2. `The Sleepy Scientist - Dreams and the Sleeping Brain - What Science Knows So Far.md`
3. `졸리지 않으려면 얼마나 자야 할까? (카이스트 김재경, 송윤민).md`
4. `일찍 자고 오래 잔다고 해서 개운한 건 아니다? (카이스트 김재경, 송윤민).md`
5. `잠을 잘 때 무슨일이 일어나는 것인가? '뇌'와 '수면'의 과학.md`
6. `수면 전문의가 매일 아침 스마트워치로 체크하는 '3가지' (주은연 교수).md`
7. `'나'라는 존재에 대한 가장 소름 돋는 착각 (우리는 조종당하고 있다).md`
8. `How to Turn ADHD Into a Genius-Level Advantage.md`
9. `Neuroscience Confirms- This One Behavior Quietly Weakens Your Brain.md`
10. `어떻게하면 스트레스를 다스릴 수 있을까?! (연세대학교 김주환 교수).md`

### New pages created (27)

**Sleep concepts (15)**:
- [[sleep-architecture]] (hub), [[rem-sleep]], [[slow-wave-sleep]]
- [[glymphatic-system]], [[two-process-model-of-sleep]], [[circadian-rhythm]], [[melatonin]]
- [[dreams]], [[lucid-dreaming]], [[nightmares]]
- [[rem-sleep-behavior-disorder]], [[sleep-apnea]], [[insomnia]], [[zolpidem]]
- [[sleep-position-and-brain-clearance]]

**Psych/cognition concepts (9)**:
- [[microbial-cloud]], [[interoception]], [[stress-response]], [[active-inference-and-chronic-pain]]
- [[cognitive-overload]], [[deep-work]]
- [[inner-communication-meditation]], [[forgiveness-and-self-compassion]]
- [[adhd-strengths-framework]]

**Protocols (3)**:
- [[sleep-hygiene-protocol]], [[digital-minimalism-protocol]], [[meditation-practice]]

### Updates to existing pages (12)

- [[sleep-disturbance-in-atopic-dermatitis]] — added sleep-architecture section and link to sleep-apnea, RBD
- [[hpa-axis]] — added links to stress-response, interoception
- [[gut-brain-axis]] — added link to microbial-cloud, stress-response, interoception
- [[gut-microbiome]] — added link to microbial-cloud
- [[adhd]] — added links to adhd-strengths-framework, cognitive-overload, deep-work
- [[vagus-nerve]] — added links to microbial-cloud, stress-response, interoception, meditation-practice
- [[pruritus]] — added links to active-inference-and-chronic-pain, interoception, meditation-practice
- [[autonomic-nervous-system]] — added links to stress-response, interoception, meditation-practice
- [[parasympathetic-nervous-system]] — same additions
- [[sympathetic-nervous-system]] — same additions
- [[parasympathetic-activation]] (protocol) — added cross-links to inner-communication-meditation, forgiveness, interoception, active-inference, meditation-practice
- [[atopic-dermatitis-mental-health]] — added links to adhd-strengths-framework, stress-response, interoception, active-inference

### Session 3 totals

- New concept pages: 24
- New protocol pages: 3
- Updates to existing pages: 12

### Final cumulative totals across all 3 sessions

- **Concepts: 61**
- **Protocols: 6**
- **Meta (index + log): 2**
- **Total: 69 files**
- **Total unique wiki-link targets: validated in session closeout**

### Notable evidence patterns

- **Strongest evidence anchors**: Xie et al. 2013 *Science* (glymphatic system), Siclari et al. 2017 (hot-spot dreaming), Borbély two-process model + KAIST SleepWake validation (2-process-model), Vallès-Colomer et al. 2023 (microbial transmission), Wisconsin Siclari study (dream detection), Kim Hyung-jun carpal tunnel acupuncture *Brain* paper (retained from session 2).
- **Clinical expert**: 주은연 (Samsung Medical Center) is the primary source for [[zolpidem]], [[rem-sleep-behavior-disorder]], [[sleep-apnea]] claims. Her specific clinical anecdotes (zolpidem paradoxical behaviors, RBD conversion rates) are expert-opinion but grounded in widely published literature.
- **Academic expert**: 김주환 (Yonsei University communication) is primary source for [[inner-communication-meditation]], [[stress-response]] detail, [[forgiveness-and-self-compassion]], [[active-inference-and-chronic-pain]] framing. His 2023 book *내면소통* synthesizes peer-reviewed neuroscience.
- **Math/biology expert**: 김재경 / 송윤민 (KAIST) — primary source for [[two-process-model-of-sleep]]; their mathematical modeling work is published in high-impact journals and now integrated into Samsung Health as "Bedtime Guidance."
- **Promotional content flagged explicitly**: Ancient Sleep Position (mixes real Xie 2013 with Ayurvedic hype), Neuroscience Weakens Brain (real science with productivity-creator framing). Extracted real biology, flagged hype in-page.

### Lint summary at end of session 3

New flagged pages (single-source or promotional-heavy): [[adhd-strengths-framework]] (survivorship bias), [[cognitive-overload]], [[deep-work]], [[digital-minimalism-protocol]] (all Dr. Matt Jones), [[sleep-position-and-brain-clearance]] (Ancient Sleep Position hype flag), [[zolpidem]] (single clinical source but grounded in standard clinical knowledge), [[inner-communication-meditation]] (single academic source — 김주환).

The **active-inference-and-chronic-pain → pruritus** linkage is a suggestion added by us based on concordance between 김주환's chronic-pain framing and our existing [[pruritus]] page; specific primary literature for AD central itch in Friston's terms not yet ingested — flagged `[needs verification]`.

### Closing observations

- The wiki now has **good structural integrity** — 4 top-level clusters (skin/AD, gut/microbiome, nervous system/stress, sleep, mental health/cognition) each with identifiable hubs and internally-linked concepts.
- **Good cross-axis linking**: sleep ↔ AD (via sleep-disturbance-in-AD), gut ↔ brain (via microbial-cloud, gut-brain-axis), stress ↔ AD (via brain-skin-axis, HPA axis, pruritus), stress ↔ gut (via HPA, leaky gut).
- **Protocols** integrate concepts across clusters: sleep-hygiene-protocol links sleep + AD + parasympathetic; digital-minimalism-protocol links cognitive-overload + ADHD + sleep; meditation-practice links interoception + parasympathetic + active-inference.

### For next phase (post-RAW)

Now that RAW is fully ingested, natural next moves would be:

1. **PDFs** — the `0.1. pdf` folder is currently empty; user adding primary literature would enable upgraded evidence levels on many claims.
2. **personal/** pages — the `personal/` folder is empty; if the user has AD, sleep data, lab results, dietary habits, they can now be documented with links into the relevant concept framework.
3. **Lint audit** — with 61 concepts, it's worth running the audit checks in CLAUDE.md (contradictions, orphans, outdated claims, single-source heavy pages).
4. **Integration with user's actual AD management** — linking concepts to their specific treatment and monitoring in personal/.
5. **Re-check Korean source transcripts** — several Korean YouTube auto-transcripts had poor quality (especially 잠을 잘 때 무슨일); user may have higher-quality version or primary references they want to add.

---

## 2026-04-23 — Session 2: Gut-brain + Nervous system + AD-adjacent (10 sources, second 1/3)

### Design decisions this session

- User asked for "about half" of the remaining 20 sources → picked 10 that form a coherent extension of the session-1 AD scaffold.
- Clusters ingested: gut-brain (5), AD neuro/behavior bridge (3), autonomic nervous system (2).
- Kept gluten/zonulin claims tightly scoped (celiac-anchored; non-celiac flagged as `[needs verification]`).
- Separated ADHD into its own page rather than keeping all ADHD content inside `atopic-dermatitis-mental-health`, because upcoming session has ADHD-specific general sources (Karpathy-style: when a concept is about to recur independently, give it a home).
- Kept `autism-spectrum-disorder` as a disease page rather than merging into gut-brain-axis, because the POSTECH study gives enough specific mechanistic content (BTBR model, L. murinus, L. reuteri IMB016).
- Did **not** create separate pages for: Parkinson's disease (mentioned only in passing), EFT (folded into `acupuncture`), hepatic encephalopathy (mentioned only in passing).

### Sources ingested

From `1. RAW/0.1. Youtube Transcripts/`:

1. `!Microbiota-gut-brain axis in health and disease- From mice to men.md` (Premysl Bercik, McMaster University)
2. `!The Gut-Brain Axis - Gut Microbiome Influences on Neurological Disease.md` (Sergio Baranzini, UCSF, 2022-05-24)
3. `How Does Alcohol Impact Your Gut Microbiome & Leaky Gut? - Dr. Andrew Huberman.md`
4. `What is leaky gut, and how do you prevent it?.md` (Dr. Steven Gundry — promotional)
5. `"자폐증, 뇌가 아니라 '장' 때문이다?"` (안될과학, summarizing POSTECH BTBR study — L. murinus and L. reuteri IMB016)
6. `How To Activate Your Parasympathetic Nervous System For Healing.md` (Alex Howard)
7. `Understanding the Link Between Eczema and ADHD in Children.md` (Jennifer Moyer, LCSW, National Jewish Health)
8. `Why Your Child's Allergies & Eczema Keep Coming Back - The Nervous System Connection.md` (chiropractic promotional — flagged)
9. `Autonomic Nervous System - Crash Course Anatomy & Physiology 13.md` (Hank Green / Crash Course educational)
10. `말초 신경의 자극을 통해서 뇌기능 조절이 가능하다?! 침의 과학적인 효능 분석!` (김형준 박사, 한국한의학연구원)

### New pages created (22)

**Concepts (20)**:
- [[gut-brain-axis]], [[vagus-nerve]], [[gut-microbiome]], [[short-chain-fatty-acids]], [[dysbiosis]], [[leaky-gut]], [[zonulin]]
- [[fecal-microbiota-transplantation]], [[probiotics]]
- [[irritable-bowel-syndrome]], [[multiple-sclerosis]], [[autism-spectrum-disorder]]
- [[t-regulatory-cells]], [[th17-cells]]
- [[autonomic-nervous-system]], [[sympathetic-nervous-system]], [[parasympathetic-nervous-system]], [[hpa-axis]]
- [[acupuncture]]
- [[adhd]]

**Protocols (2)**:
- [[parasympathetic-activation]]
- [[gut-health-diet]]

**Updates to existing pages (5)**:
- [[gut-skin-axis]] — slimmed down leaky-gut/zonulin sections to cross-links; added links to [[gut-brain-axis]], [[short-chain-fatty-acids]], [[hpa-axis]], [[gut-health-diet]].
- [[brain-skin-axis]] — added ANS relationship section and links to [[autonomic-nervous-system]], [[sympathetic-nervous-system]], [[parasympathetic-nervous-system]], [[vagus-nerve]], [[hpa-axis]], [[parasympathetic-activation]].
- [[atopic-dermatitis-mental-health]] — linked to [[adhd]]; added Moyer's skin-first-then-reassess caveat and dupilumab-reduces-ADHD-symptoms note.
- [[skin-microbiome]] — linked to [[gut-microbiome]] and [[gut-brain-axis]] for contrast.
- [[atopic-dermatitis]] (hub) — added related-page links for gut-brain-axis, leaky-gut, dysbiosis, ANS/SNS/PNS, vagus, HPA, adhd, parasympathetic-activation, gut-health-diet.

### Session 2 totals

- Concept pages now: 17 (session 1) + 20 (session 2) = **37 concept pages**.
- Protocols now: 1 + 2 = **3 protocol pages**.
- With index.md + log.md = **42 files total** in WIKI.

### Notable evidence patterns

- **Strongest evidence**: germ-free mouse transfer experiments (Bercik IBS, Baranzini MS, POSTECH autism) — causal; Kim's carpal tunnel acupuncture study (sham-controlled RCT with objective outcomes).
- **Moderate**: FMT for C. difficile (RCTs); B. longum RCT for IBS+depression; fermented foods RCT (Sonnenburg/Gardner).
- **Weak / promotional**: Gundry (prebiotic marketing), Petersburg Family Chiropractic (vagal tone claims for chiropractic), Alex Howard (no RCT for his framework), Why Your Child's Allergies (chiropractic promotional).
- Applied the `[needs verification]` tag consistently where primary sources were promotional or single-source.

### Design memo for session 3 (final session, sleep + behavior/stress, 10 sources)

- **Sleep cluster (6) will build on**: existing [[sleep-disturbance-in-atopic-dermatitis]] page (AD-specific); new general pages likely include `rem-sleep`, `non-rem-sleep`, `sleep-architecture`, `circadian-rhythm`, `sleep-position-brain-aging` (if Scientists Can't Explain source is robust), `sleep-cycles`. Also protocols around sleep hygiene.
- **Behavior/stress cluster (4) will connect to**: existing [[atopic-dermatitis-mental-health]], [[adhd]], and [[hpa-axis]]. New concept pages likely: `loneliness-and-brain-health` (from Neuroscience Confirms video), `adhd-reframing` (ADHD strengths — from "Genius-Level Advantage"), `stress-resilience` (from 김주환 — his work is substantial).
- **Korean 김주환 talk**: likely to introduce concepts like 회복탄력성, which map to `psychological-resilience` in English with Korean alias.
- **Likely new cross-links**: sleep ↔ brain-skin axis, HPA axis, pruritus; resilience ↔ parasympathetic activation.

### Lint summary at end of session 2

Wiki-link validator (Python script): **0 broken links, 0 orphaned pages** across 42 files.

New single-source pages flagged: [[autism-spectrum-disorder]], [[acupuncture]], [[hpa-axis]] (weak composite), [[zonulin]].

Weak-source heavy pages flagged: [[leaky-gut]] (Gundry), [[vagus-nerve]] (chiropractic section), [[parasympathetic-activation]] (Howard), [[gut-health-diet]] (Gundry).

---

## 2026-04-23 — Session 1: Atopic Dermatitis cluster (10 sources, first 1/3 of RAW)

### Infrastructure setup

- Created `concepts/`, `personal/`, `protocols/` subfolders under `2. WIKI/`.
- Created `index.md` (table of contents + ingest status) and this `log.md`.
- Language decision: concepts/ in English with Korean Aliases; personal/ and protocols/ permitted in Korean or mixed.
- Ingest strategy: concept-based, maximum concept separation to support link-based lookup; no per-source summary pages (user decision).

### Sources ingested

From `1. RAW/0.1. Youtube Transcripts/`:

1. `Pathophysiology of Atopic Dermatitis.md`
2. `Atopic Dermatitis- Beyond Scratching the Surface.md` (Dr. Jeffrey Weinberg)
3. `Aspects of AD that Don't Get Enough Attention.md`
4. `The microbiome in atopic dermatitis - Dr. Heidi Kong.md`
5. `Atopic Dermatitis and the intestinal microbiota - Thursday's Thought.md` (Nel Cook, K9 Ceuticals; cites 2016 *Veterinary Medicine and Science* review)
6. `Brain skin connections in atopic dermatitis - Pr. Martin Steinhoff.md`
7. `Links between inflammation, sleep disturbance and neurocognitive function in atopic dermatitis.md` (Carsten Flohr, King's College London; cites their *Allergy* review)
8. `Treatment of Moderate-Severe Atopic Dermatitis - Line 1 Stop 1 Overview.md`
9. `Treatment of Moderate-Severe Atopic Dermatitis - Line 1 Stop 3 Inflammatory Cells.md`
10. `How to EXERCISE with ECZEMA and TSW.md` (Larry, Fighting Eczema)

### Pages created (17 concepts + 1 protocol + index + log = 20 files)

**Concepts (17):**
- [[atopic-dermatitis]] (hub)
- [[skin-barrier-dysfunction]]
- [[filaggrin]]
- [[th2-inflammation]]
- [[epithelial-alarmins]]
- [[tslp]]
- [[il-4-and-il-13]]
- [[il-31]]
- [[jak-stat-signaling]]
- [[ige]]
- [[pruritus]]
- [[brain-skin-axis]]
- [[skin-microbiome]]
- [[gut-skin-axis]]
- [[atopic-dermatitis-mental-health]]
- [[sleep-disturbance-in-atopic-dermatitis]]
- [[dupilumab]]

**Protocols (1):**
- [[exercise-with-eczema]]

**Meta:**
- `index.md`
- `log.md` (this file)

### Design notes for future sessions

- **IL-25 and IL-33** do not yet have dedicated pages — they are covered inside [[epithelial-alarmins]]. Split out when future sources provide enough detail.
- **IL-5, IL-22** mentioned only in passing; not pages yet.
- **Staphylococcus aureus** detail lives inside [[skin-microbiome]]; split out when future sources warrant.
- **ADHD, depression, anxiety** each likely merit their own concept pages; currently they live inside [[atopic-dermatitis-mental-health]] until general sources (not AD-specific) are ingested. ADHD particularly will need dedicated page when the ADHD-cluster sources are ingested next session.
- **Acupuncture, autonomic nervous system, parasympathetic activation, vagal nerve** will be pulled in from the ANS cluster next session and will likely connect back to [[brain-skin-axis]] and [[pruritus]].
- **Sleep architecture concepts** (REM, NREM, sleep cycles, etc.) will emerge from the sleep cluster and should get their own pages; [[sleep-disturbance-in-atopic-dermatitis]] references REM but does not define it.

### Lint flags (to address when corroborating sources arrive)

- [[dupilumab]] — single source; missing efficacy numbers, adverse effects, dosing, non-AD indications.
- [[gut-skin-axis]] — single source, and that source is veterinary-oriented and commentary-based; human AD claims need corroboration.
- [[exercise-with-eczema]] — single source, non-physician YouTube channel. Mechanistic plausibility assumed; AD-specific outcome evidence not given.
- [[atopic-dermatitis-mental-health]] — "~30% depression" is cited generically; primary study not named.
- Zonulin mechanism in [[gut-skin-axis]] flagged `[needs verification]` outside celiac context.

### Open question / user preference

- The sources are YouTube transcripts (many educational/CME in nature). Evidence levels for most claims on these pages are marked `expert-opinion` because they synthesize primary literature without presenting it directly. Where a speaker refers to a specific published review (Flohr / *Allergy*; Cook / *Vet Med Sci* 2016), I tagged `review`. When future sessions ingest primary literature, these pages should be upgraded with stronger citations.

## 2026-04-23 — Initial setup

- CLAUDE.md present at project root.
- RAW folder contains ~30 YouTube transcripts (English and Korean); no PDFs yet.
- WIKI folder initially empty.
