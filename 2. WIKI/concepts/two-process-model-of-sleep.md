# Two-Process Model of Sleep

**Summary**: The standard model of sleep regulation, originally proposed by Alexander Borbély (1982). Sleep/wake state is determined by the interaction of **two processes**: **Process S (sleep pressure)** — a homeostatic drive that accumulates during wakefulness and dissipates during sleep — and **Process C (circadian alerting signal)** — a ~24-hour rhythm that modulates wakefulness. Understanding this model is the mathematical foundation of the **SleepWake app** developed by 김재경 (KAIST) and 송윤민 — which uses personalized modeling to recommend when and how long to sleep.

**Aliases**: Borbély two-process model, S-C model, sleep pressure + circadian rhythm, 수면압-일주기 모델, 2-process model

**Sources**: 졸리지 않으려면 얼마나 자야 할까? (김재경, 송윤민).md; 일찍 자고 오래 잔다고 (김재경, 송윤민).md

**Source dates**: undated; SleepWake papers published in high-impact journals; now integrated into Samsung Health as "Bedtime Guidance"

**Last updated**: 2026-04-23

> [!abstract]+ 한글 요약
> **2-process 모델**(Borbély, 1982)은 수면/각성 상태의 표준 모델이다. 두 과정의 상호작용으로 결정된다 — **Process S(수면압, 항상성)**: 깨어 있을수록 누적, 자면 분산됨. 분자적 상관물은 **아데노신**. **Process C(일주기 각성 신호)**: ~24시간 리듬으로 각성을 변조. 낮에 높음(수면압에 맞서 각성 유지), 밤에 낮음(수면압 + 낮은 각성 → 잠듦). 이 모델은 KAIST **김재경 교수**와 **송윤민 박사**가 개발한 **SleepWake 앱**(현 삼성헬스 **"취침 시간 가이드"**)의 수학적 기반. 개인별 수면 이력(웨어러블 데이터, 최소 3일)으로 모델 보정. 임상 시험 2건(교대 근무 간호사 19명, 일반 수면 불편군 ~145명) 결과 — **권고 이행도(agreement score)가 개운함 점수와 상관**, **총 수면 시간은 개운함을 잘 예측하지 못함**. 비자명한 예측 — 같은 시간을 자도 일주기와 **정렬**되면 개운함, 아니면 피곤함. **정기성이 총 시간보다 중요**. 교대 근무자에게는 시뮬레이션 기반 **분할 수면**이 효과적일 수 있음. 함의 — "8시간 자라"는 조언은 부적절, 교대 근무·시차가 총 수면에도 불구하고 해를 끼치는 이유 설명. 한계 — 병·약·만성 불면·교대 근무 이력이 모델을 흐트림. 유전적 short/long sleeper는 평균 모수에 안 맞음 → 개별 보정 필요.

---

## The two processes

### Process S — sleep pressure (homeostatic)

- Accumulates during wakefulness; the longer you're awake, the more "pressure" to sleep.
- Dissipates during sleep, fastest during [[slow-wave-sleep|deep NREM]].
- Bercik-style analogy (source: 졸리지 않으려면.md, evidence: expert-opinion): think of a vacuum cleaner — dust accumulates during use, gets emptied during rest.
- Biologically: adenosine accumulation in certain brain regions is the leading molecular correlate.

### Process C — circadian alerting signal

- ~24-hour oscillation of alertness, driven by the [[circadian-rhythm]].
- High during subjective day, low during subjective night.
- Opposes sleep during day (keeps you awake despite building sleep pressure); permits sleep during night (sleep pressure + low alertness → fall asleep).

> *요약: **두 과정**. **Process S(수면압, 항상성)** — 깨어 있을수록 누적, 수면 특히 [[slow-wave-sleep|깊은 NREM]]에서 급속히 해소. 청소기 먼지 비유(사용 중 누적, 휴식 중 비움). 분자 상관물 = **아데노신 축적**. **Process C(일주기 각성 신호)** — [[circadian-rhythm|일주기]] 구동 ~24시간 각성 진동. 주관적 낮 높음, 주관적 밤 낮음. **낮에는 수면압에 맞서 각성 유지**, **밤에는 수면압 + 낮은 각성 = 잠듦**.*

## The model in practice

Both processes interact (source: 졸리지 않으려면.md, evidence: expert-opinion):

- **Sleep onset** occurs when Process S crosses an upper threshold relative to Process C.
- **Wake onset** occurs when Process S falls below a lower threshold relative to Process C.
- If you fall asleep "on schedule" and wake naturally, both thresholds are crossed in the right order.
- If forced to wake early (alarm), Process S may still be high → grogginess. If forced to stay up late, Process S is very high and Process C is low → intense sleepiness.

> *요약: **상호작용** — 수면 개시는 S가 상한 역치를 Process C에 대해 넘어설 때. 각성은 S가 하한 역치를 넘어 하강할 때. 알람으로 이른 기상 → S 여전히 높아 아침 피곤(grogginess). 늦게까지 깨어 있으면 S 매우 높음 + C 낮음 → 극도의 졸음.*

## The SleepWake app

김재경 교수 (KAIST, mathematical biology) and 송윤민 박사 developed a mathematical model of the two-process interaction calibrated to each person's sleep history via wearable data (source: 졸리지 않으려면.md and 일찍 자고 오래 잔다고.md, evidence: RCT-adjacent clinical trials):

### Data

- Collected from **Samsung Galaxy Watch / Apple Health** via Samsung Health (or equivalent).
- Minimum 3 days of sleep history to make a useful recommendation.

### Validation

- **First clinical trial** (with 주은연 교수 at Samsung Medical Center and 최수정 교수 at Sungkyunkwan): nurses in shift work, 19 participants. The 10 who followed recommendations (high-compliance) reported significantly improved subjective refreshment (KSS score) in Period 2 (app guidance active) vs Period 1 (no guidance).
- The 10 who did not follow recommendations did not improve — or declined — in refreshment.
- **Second trial** (general population with sleep complaints, ~145 → 73 analyzable): similar pattern. ~half complied (high-compliance group), ~half did not. Same direction of benefit.
- **Key finding**: **agreement score** (how closely actual sleep matched recommendation) correlated with refreshment — regardless of *total sleep time*. Duration alone poorly predicted refreshment.

### Integration

- Licensed to Samsung; now part of **Samsung Health "Bedtime Guidance" (취침 시간 가이드)**.
- KAIST's largest-ever software technology transfer and the mathematics department's first.

> *요약: **SleepWake 앱**(김재경 KAIST 수리생물학 + 송윤민). 수학 모델을 웨어러블 데이터로 개인 보정(삼성 갤럭시 워치·애플 헬스·삼성헬스). 최소 3일 이력 필요. **임상 시험 1**: 삼성의료원 주은연·성균관대 최수정 협력, 교대 근무 간호사 19명. 권고 이행군 10명은 KSS 개운함 점수 유의 개선(Period 2 앱 가이드 활성 vs Period 1 무 가이드). 비이행군 10명은 변화 없거나 악화. **임상 시험 2**: 일반 수면 불편군 ~145→73명 분석 가능. 유사 패턴 — 이행군 개선. **핵심 발견** — **이행도(agreement score)**가 개운함과 상관, **총 수면 시간은 상관 약함**. 삼성에 기술 이전 → **삼성헬스 "취침 시간 가이드"** 로 통합. KAIST 최대 규모 소프트웨어 기술 이전이자 수학과 최초.*

## Why the model's prediction is non-obvious

A concrete example from 일찍 자고 오래 잔다고.md (source: evidence: observational from SleepWake data):

- A nurse sleeps the same number of hours on two consecutive nights.
- Night A: misaligned with circadian rhythm (e.g. jet-lagged schedule) → agreement score 60% → refreshment score low.
- Night B: aligned with circadian rhythm → agreement score 100% → refreshment score high.
- **Same sleep duration, different feeling** — entirely driven by circadian alignment.

This is the main argument for *regular* (not just long) sleep.

> *요약: **비자명한 예측**. 한 간호사 사례 — 연속 두 밤 같은 시간 수면. A: 일주기와 어긋남(시차 같은 스케줄) → 이행도 60% → 개운함↓. B: 일주기 정렬 → 이행도 100% → 개운함↑. **같은 수면 시간, 다른 느낌**. 정렬이 전적으로 좌우. **정기성(긴 것이 아니라)**이 중요한 주요 논거.*

## The split-sleep finding for shift workers

For night-shift workers whose circadian rhythm is misaligned with their work (source: 졸리지 않으려면.md, evidence: simulation + observational):

- **Strategy 1 — sleep right after work**: some sleep happens during a suboptimal circadian window → back to work, half of work shift is in the "sleepy zone" (very tired).
- **Strategy 2 — stay awake until late afternoon, then sleep**: better for work shift but requires enduring a difficult awake window.
- **Strategy 3 — split sleep (some after work + nap before shift)**: simulation shows this can reduce total sleepy time during the shift without demanding excessive awake endurance.

The specific optimal split depends on the individual's recent sleep history and schedule — hence the need for the SleepWake model.

> *요약: **야간 교대 근무자의 분할 수면**. 일주기가 근무와 어긋난 경우 — **전략 1(퇴근 직후 수면)**: 일주기 비최적 구간에 자고 재출근 → 근무 절반이 "졸린 구간". **전략 2(오후 늦게까지 깨어 있다가 자기)**: 근무에는 유리하나 힘든 각성 구간을 견뎌야 함. **전략 3(분할: 퇴근 후 일부 + 출근 전 낮잠)**: 시뮬레이션상 졸린 근무 시간을 줄이면서 과도한 각성 인내 불요. 최적 분할은 개인의 최근 수면 이력에 달려 있으므로 SleepWake 모델이 필요.*

## Clinical significance

- Explains why **"get 8 hours"** is inadequate as advice.
- Explains why **shift workers suffer** despite adequate total sleep.
- Explains why **jet lag** is predictable by direction (east > west in difficulty).
- Supports the importance of **circadian regularity** over sheer duration.
- Provides a principled target for interventions.

> *요약: **임상 함의** — **"8시간 자라"는 부적절**하다는 이유 설명. 교대 근무자가 총 수면 충분해도 고통받는 이유. 시차가 방향에 따라 어려움 예측 가능(동쪽이 서쪽보다 힘듦). **총 시간보다 일주기 정기성**이 중요. 개입의 원칙적 표적 제공.*

## Limitations

- The model assumes a functional [[circadian-rhythm]] and homeostatic system — both can be disturbed by disease, medication, [[insomnia]], or shift work history.
- Short sleepers and long sleepers (genetic) don't fit average parameters; requires individual calibration.
- Underlying assumptions about adenosine kinetics are simplifications of messy biology.

> *요약: **한계** — (1) 모델은 정상적 [[circadian-rhythm|일주기]]·항상성 시스템을 가정. 병·약·[[insomnia|불면]]·교대 근무 이력에 의해 흐트림. (2) 유전적 short/long sleeper는 평균 모수에 안 맞음 → 개별 보정 필요. (3) 아데노신 동역학 가정은 복잡한 생물학을 단순화한 것.*

> [!tip]+ 핵심 정리
> 1. **2-process 모델(Borbély 1982)** = 수면/각성의 표준 모델. **Process S(수면압) + Process C(일주기 각성)**.
> 2. **수면압은 아데노신 누적**: 깨어 있을수록 증가, 깊은 NREM에서 급속히 해소.
> 3. **일주기 각성**: 낮에 높아 수면압 상쇄, 밤에 낮아 잠듦 허용.
> 4. **SleepWake 앱**(KAIST 김재경·송윤민) = 이 모델을 개인화한 기술. 삼성헬스 "취침 시간 가이드"로 통합.
> 5. **핵심 발견**: **이행도가 개운함을 예측**, 총 수면 시간은 아님. **정기성 > 총 시간**.
> 6. **함의**: "8시간" 조언 부적절. 교대 근무자 분할 수면 시뮬레이션. 시차의 방향성 설명.

## Related pages

- [[circadian-rhythm]]
- [[sleep-architecture]]
- [[melatonin]]
- [[insomnia]]
- [[sleep-hygiene-protocol]]
