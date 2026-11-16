---
name: pantarhei-challenge
description: >-
  Critical thinking and red-teaming for an existing idea, plan, claim, study, pitch or decision. Use when the user asks to poke holes, play devil's advocate, stress test, red team, run a pre-mortem, find blind spots, check whether something is credible, steelman the other side, or asks what they are missing in a plan or argument. Runs the Red Team: steelman the idea first, then numbered attacks each tagged with the bias or audit that produced it (incentives, base rates, survivorship, sampling, confirmation, narrative, key assumptions, competing hypotheses) and a severity, then a survival score out of 10 and the single weakest link. Ends with the strongest surviving version, not a pile of criticism. Not for generating new ideas (use pantarhei-brainstorm), framing a vague situation (use pantarhei-reframe), or making the final choice between options (use pantarhei-decide). Not for code review or proofreading.
---

# Panta Rhei Challenge — The Red Team

Attack the user's idea as a capable adversary would, fairly. The output is not a list of
objections; it is a verdict on what survives and the stronger version that remains.

Load before starting:
- `references/catalog.json`: red-team methods.
- `references/models.json`: all 59 audit models from the shared library, plus inversion,
  second-order thinking and falsification.
- `references/shared-rules.md`.

## 1. Steelman

Restate the idea in its strongest form, in three to five lines (`challenge.steelman`). Include the
best evidence for it. If you cannot state it better than the user did, you do not understand it
yet: ask nothing, re-read, and try again. The user should recognise their idea, improved.

## 2. Pick the attack set

Map the object to the audits (from the shared protocol):

| Object | Attack with |
|---|---|
| A claim, study, report or statistic | mm.bias-from-incentives, mm.sampling, mm.failure-to-account-for-base-rates, mm.survivorship-bias, challenge.lateral-reading, challenge.extraordinary-claims, challenge.quality-of-information, challenge.sift-check |
| A plan or project | decide.premortem (shared), challenge.key-assumptions, mm.second-order-thinking, mm.inversion, challenge.chestertons-fence, challenge.robustness-stress-test, challenge.scenario-planning |
| A decision the user favours | mm.confirmation-bias-and-falsification, mm.first-conclusion-bias, mm.commitment-and-consistency-bias, challenge.consider-opposite |
| A judgment about a person | mm.overestimate-consistency-of-behavior, mm.hanlons-razor, mm.relativity |
| An explanation of an outcome | mm.hindsight-bias, mm.randomness, mm.narrative-instinct, challenge.ach |
| A consensus or trend | mm.social-proof, mm.bubbles, challenge.dialectical-inquiry, challenge.paradigm-audit, challenge.research-programme-audit |
| An argument, essay or pitch (a text) | challenge.toulmin-audit, challenge.argument-mapping, challenge.fallacy-sweep, challenge.principle-of-charity |
| A forecast, projection or timeline | challenge.estimative-language, challenge.reference-class-forecasting, challenge.calibration-scoring, mm.planning-fallacy |
| A group or team decision | mm.groupthink, mm.abilene-paradox, mm.pluralistic-ignorance, challenge.noise-audit |
| Advice or a recommendation | challenge.skin-in-the-game, challenge.adler-teleology, mm.bias-from-incentives |
| A plan driven by a metric or target | challenge.goodhart-audit, challenge.campbell-audit, challenge.cobra-effect |
| A person's stated reasons or motives | challenge.adler-private-logic, challenge.adler-compensation, challenge.adler-mistaken-goals, challenge.misperception-audit |
| A bet, stake or irreversible commitment | challenge.ergodicity-audit, challenge.reversibility-check, challenge.kelly-sizing, challenge.margin-of-safety |
| The user's own certainty | challenge.crux, challenge.update-triggers, mm.denial |

Run four to eight attacks. Fewer if one is fatal.

## 3. Attack

```
RED TEAM · "Move the team to a four-day week to fix burnout"
──────────────────────────────────────────────────────────────
STEELMAN  Burnout is driven by sustained load without recovery; a structural day off…

#  ATTACK                                        AUDIT                    SEVERITY
1  Pilots that report success self-select keen teams   Survivorship bias   serious
2  Same deadlines in 4 days raises daily load         Second-order         FATAL unless scope drops
3  Partner SLAs assume 5-day coverage                  Key assumptions      serious
4  "Everyone loves it" is the first-month effect       Regression to mean   cosmetic

SURVIVAL   3/10  (one fatal flaw caps at 3)
WEAKEST LINK  #2: the plan holds only if scope falls with the hours.
STRONGER VERSION  Four-day week paired with a 20% scope cut and a rotating Friday on-call.
```

Rules for attacks:
- Each attack is a specific, checkable claim, not a mood ("this seems risky").
- Each names the audit or method that produced it. **Naming a bias is not an attack**; the attack
  is the concrete way the bias would distort this case.
- Severity: **fatal** (the idea fails if true), **serious** (needs a fix), **cosmetic**.
- Score with `challenge.survival-score`: one fatal flaw caps the score at 3.

## 4. Rebuild

End with the **stronger version**: the smallest change that survives the fatal and serious attacks.
If nothing survives, say so plainly.

## 5. Hand off

- A stronger version exists and must be chosen against alternatives → "Next step: choose between the stronger version and the alternatives (Panta Rhei Decide does this)."
- Nothing survives → "Next step: generate alternatives (Panta Rhei Brainstorm does this)."
- The attacks show the problem itself was misframed → "Next step: reframe the problem (Panta Rhei Reframe does this)."

## Rules specific to Challenge

- **Steelman first, always.** Attacking a weak version is worthless.
- **Fair, not contrarian.** If the idea is good, say so and score it high. A red team that always
  finds fatal flaws is noise.
- **Attack the idea, not the person.** Judgments about people use the person audits, and the user's
  motives are not a target.
- **Evidence ceilings apply to attacks too.** An analogical attack ("like Blockbuster") is a
  hypothesis, not a finding.
