# T Regulatory Cells (Tregs)

**Summary**: A specialized subset of CD4+ T lymphocytes whose role is to **suppress** immune responses, maintaining self-tolerance and preventing autoimmunity. Defined by co-expression of CD25 (IL-2 receptor α) and the transcription factor **Foxp3**. Central players in the [[gut-brain-axis]] / immune-microbiome story: gut microbes and their metabolites (especially [[short-chain-fatty-acids]]) expand the Treg population, while [[dysbiosis]] can deplete Tregs and tilt the system toward inflammation. Deficit is implicated in [[multiple-sclerosis]], [[atopic-dermatitis]], inflammatory bowel disease, and other autoimmune conditions.

**Aliases**: Tregs, T-reg, regulatory T-cell, CD4+CD25+Foxp3+ T-cell, 조절 T 세포, suppressor T-cell

**Sources**: !The Gut-Brain Axis - Gut Microbiome Influences on Neurological Disease.md (Baranzini)

**Source dates**: 2022

**Last updated**: 2026-04-23

> [!abstract]+ 한글 요약
> **Treg(T regulatory cells, 조절 T세포)** 는 CD4+ T림프구의 특별한 하위군으로, **면역 반응을 억제**해 자기 관용을 유지하고 자가면역을 방지한다. 표지는 **CD25 + Foxp3 동시 발현**. [[th17-cells|Th17 세포]]와 반대 축을 이루며, 둘의 균형이 면역 긴장도를 결정한다. [[gut-microbiome|장내 미생물]]이 Treg를 조절하는 핵심 경로 — **[[short-chain-fatty-acids|SCFAs]]** (butyrate 등)와 ***Bacteroides fragilis*의 polysaccharide A(PSA)** 가 대표적 Treg 유도 신호. [[dysbiosis|장내 불균형]]이 Treg를 줄이고 면역이 염증 쪽으로 기울게 한다. Treg 결핍은 [[multiple-sclerosis|MS]], [[atopic-dermatitis|AD]], 염증성 장 질환 등 자가면역·염증성 질환의 공통 특징. 치료적 함의 — Treg 확장은 자가면역 치료의 주요 목표이며, 경로는 섬유 식이·Treg 유도 프로바이오틱스·FMT·저용량 IL-2 요법 등이 있다.

---

## What Tregs do

- Suppress excessive immune activation and prevent the immune system from attacking self-tissues.
- Counter-balance pro-inflammatory T-cell populations, especially [[th17-cells|Th17 cells]].
- Produce anti-inflammatory cytokines, notably IL-10 and TGF-β.
- Marker signature: **CD4+ CD25+ Foxp3+** (source: !The Gut-Brain Axis - Baranzini.md, evidence: expert-opinion).

> *요약: Treg의 역할 — (1) 과도한 면역 활성화 억제, 자기 조직 공격 방지, (2) Th17 등 염증성 T세포군과 대항 축, (3) 항염증 사이토카인(**IL-10, TGF-β**) 분비, (4) 표지는 **CD4+ CD25+ Foxp3+**(Foxp3가 Treg 특이 전사인자).*

## How microbes shape Tregs

Two well-characterized pathways (source: !The Gut-Brain Axis - Baranzini.md, evidence: expert-opinion citing peer-reviewed work):

1. ***Bacteroides fragilis* polysaccharide A (PSA)** — binds Toll-like receptor 2 (TLR2) on immune cells → stimulates Treg differentiation → suppresses inflammation, enables the bacterium's own colonization. A bacterium that "asks permission" to colonize by activating regulatory immunity.
2. **[[short-chain-fatty-acids]]** — fermentation products of dietary fiber (butyrate, propionate, acetate) regulate Treg size and function, protect against colitis and other inflammatory events.

So: fiber + SCFA-producing bacteria + *B. fragilis*-like commensals → expand Tregs → reduce inflammation.

> *요약: 미생물이 Treg를 조절하는 두 경로 — (1) ***B. fragilis*의 polysaccharide A(PSA)** 가 면역 세포의 TLR2 수용체에 결합 → Treg 분화 유도 → 염증 억제 → 세균 자신의 정착 허용(숙주에게 "허락"을 구하는 방식). (2) **SCFAs**(butyrate·propionate·acetate)가 Treg 크기·기능 조절. **섬유 + SCFA 생산 세균 + *B. fragilis* 같은 공생균 → Treg 확장 → 염증 감소**의 경로.*

## Tregs in disease

### [[multiple-sclerosis]]

Central to the MS-microbiome hypothesis (source: !The Gut-Brain Axis - Baranzini.md, evidence: mechanistic):

- Antibiotic-treated mice resistant to EAE show expanded Tregs and increased IL-10/IL-13.
- **MS patient microbiota is less efficient at inducing Tregs** in vitro than healthy control microbiota — a functional signature of dysbiotic immune tone.
- Specific taxa:
  - *Acinetobacter calcoaceticus* (higher in MS): **decreases** Treg differentiation.
  - *Parabacteroides distasonis* (lower in MS): induces IL-10 production (supporting regulatory tone).

### Connection to skin / [[atopic-dermatitis]]

Tregs are not detailed in the AD sources covered so far, but they are known to suppress [[th2-inflammation|Th2]] responses — the mainstay of AD pathology. Low Treg activity is implicated in AD in the broader literature `[needs verification from AD-specific sources]`.

> *요약: MS에서 Treg 중심성 — 항생제 처리 마우스(EAE 저항) → Treg 확장 + IL-10/IL-13 증가. **MS 환자 마이크로바이옴은 Treg 유도 능력이 건강인보다 약함**(dysbiosis의 기능적 서명). 특정 세균 — *Acinetobacter calcoaceticus*(MS에서 증가, Treg 분화 감소), *Parabacteroides distasonis*(MS에서 감소, IL-10 유도). AD와의 연결 — Treg가 Th2 반응(AD 핵심 병태)을 억제한다는 일반 문헌이 있으나 현 위키 출처에는 상세 없음.*

## Flow cytometry identification

Standard lab method (source: !The Gut-Brain Axis - Baranzini.md, evidence: expert-opinion):

- Y-axis: Foxp3 (transcription factor, Treg-specific).
- X-axis: CD25 (surface marker; also on activated T-cells).
- Tregs = cells high in both.
- "Polarizing conditions" in vitro: culture T-cells with TGF-β and IL-2 to push differentiation toward Tregs; then test whether a given bacterial extract enhances or suppresses this.

> *요약: 실험실에서 Treg 식별 — 유세포 분석(flow cytometry)에서 Y축 Foxp3, X축 CD25, 둘 다 높은 세포가 Treg. 시험관에서 "polarizing condition"(TGF-β + IL-2)으로 T세포를 Treg 분화 방향으로 밀어 놓고, 특정 세균 추출물이 이 분화를 돕는지 방해하는지 측정하는 방법이 표준.*

## Therapeutic implications

Expanding or restoring Tregs is a major goal in autoimmunity:
- **Indirect** routes: diet high in fermentable fiber ([[short-chain-fatty-acids]]), avoiding [[dysbiosis]] triggers (unnecessary antibiotics, chronic stress).
- **[[probiotics]]** targeted at Treg-inducing strains (research-grade only).
- **[[fecal-microbiota-transplantation]]** indirectly, if donor microbiota is more Treg-inducing than recipient's.
- Pharmacologic Treg expansion (low-dose IL-2, Treg cell therapy) is in clinical development for several autoimmune diseases.

> *요약: Treg를 확장·복원하는 것은 자가면역 치료의 주요 목표. (1) **간접 경로** — 발효성 섬유 풍부한 식단(SCFA 생산), dysbiosis 유발 요인(불필요한 항생제·만성 스트레스) 회피. (2) **프로바이오틱스** — Treg 유도 균주 표적(연구 단계). (3) **FMT** — 기증자 마이크로바이옴이 더 Treg 유도적이면 간접 효과. (4) **약물학적 Treg 확장**(저용량 IL-2, Treg 세포 치료) — 여러 자가면역 질환 임상 개발 단계.*

> [!tip]+ 핵심 정리
> 1. **Treg = 면역 억제자**. CD4+ T세포의 조절 하위군. 표지: Foxp3 + CD25.
> 2. **Th17과 반대 축**: 둘의 균형이 면역 긴장도를 결정.
> 3. **장내 미생물이 Treg를 조절**: SCFAs와 *B. fragilis* PSA가 대표 유도 신호.
> 4. **MS·AD·IBD 등 자가면역에서 Treg 결핍**: 치료 전략의 핵심 표적.
> 5. **확장 방법**: 섬유 식이 → SCFA → Treg. 프로바이오틱스(표적 균주), FMT, 저용량 IL-2.
> 6. **섬유가 많고 dysbiosis 유발 요인이 없는 생활 → 면역이 조절 쪽으로 기울어짐**.

## Related pages

- [[th17-cells]] (counterbalance)
- [[short-chain-fatty-acids]]
- [[gut-brain-axis]], [[gut-microbiome]], [[dysbiosis]]
- [[multiple-sclerosis]]
- [[th2-inflammation]] (general T helper context)
