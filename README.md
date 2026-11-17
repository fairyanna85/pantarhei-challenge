<p align="center"><img src="assets/banner.svg" alt="Panta Rhei Challenge: red-team an idea, plan or claim before it costs you" width="100%"></p>

# Panta Rhei Challenge

A red-team and critical-thinking skill for Claude, Claude Code and Hermes: steelman first, then attack a plan, idea or claim.

<p align="center">
  <a href="#install"><img alt="Install" src="https://img.shields.io/badge/install-1%20command-C0391F"></a>
  <img alt="Methods" src="https://img.shields.io/badge/methods-89-14161A">
  <img alt="Works with" src="https://img.shields.io/badge/works%20with-Claude%20·%20Claude%20Code%20·%20Hermes-5B6270">
  <img alt="License" src="https://img.shields.io/badge/license-MIT%20%2B%20CC%20BY%204.0-5B6270">
</p>

## What it does

Ask an AI what it thinks of your plan and it will mostly agree. Panta Rhei Challenge steelmans the idea first, then runs four to eight named attacks chosen for what you brought (a plan, a claim, a decision you favour, a judgment about a person) and rebuilds the idea from what survives. You get the stronger version, its weakest link and a survival score where one fatal flaw caps the result.

## Try it

Say any of these after installing:

> Red-team my plan to move the team to a four-day week
> Poke holes in this study claiming remote work cuts productivity by 20%
> I'm sure my co-founder is sabotaging the launch. Challenge that.

## How it works: The Red Team

Every attack names the model behind it and lands or misses. The idea is then rebuilt to survive the attacks that landed, and scored from 0 to 10.

<p align="center"><img src="assets/hero-interaction.svg" alt="The Red Team: a worked example" width="90%"></p>

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

1. **Steelman:** the strongest version of the idea, before any attack.
2. **Pick the attack set:** matched to the object, from bias audits to pre-mortems.
3. **Attack:** four to eight, each landing or missing, fewer if one is fatal.
4. **Rebuild:** the stronger version, the weakest link, the survival score.

## Install

**Claude Code**
```
/plugin marketplace add fairyanna85/pantarhei-challenge
/plugin install pantarhei-challenge@pantarhei-challenge
```
Or install the whole family: `/plugin marketplace add fairyanna85/pantarhei`.

**Hermes Agent**
```
hermes skills install https://github.com/fairyanna85/pantarhei-challenge
```

**Claude apps (web, desktop, mobile)**
1. Download [`pantarhei-challenge.zip`](https://github.com/fairyanna85/pantarhei-challenge/releases/latest/download/pantarhei-challenge.zip).
2. Go to **Customize > Skills**, click **+**, then **+ Create skill**, then **Upload a skill**, and choose the ZIP.
3. Turn the skill on. Code execution and file creation must be enabled (Settings > Capabilities).

**Any Agent Skills client** (Codex, Cursor and others): copy `skills/pantarhei-challenge/` into your
client's skills folder.

## What's inside

| Group | Methods |
|---|---|
| **Be fair first** | Steelman first · Chesterton's fence |
| **Attack a plan** | Red team · Devil's advocate · Dialectical inquiry · Key assumptions check |
| **Weigh a claim** | Analysis of competing hypotheses · Consider the opposite · Extraordinary claims · Lateral reading |
| **Settle the disagreement** | Find the crux · Pre-commit update triggers · Survival score |

## How honest is it?

Every method carries an evidence class (`formal`, `empirical`, `heuristic`, `analogical`) and its
origin, and the skill caps its claims by them. Practitioner methods are labelled as such.
Challenge only corrects distortion; it never supplies an answer of its own. A survived attack is not evidence the idea is right.

## The Panta Rhei pack (optional)

Each module works on its own. The pack installs all five plus Panta Rhei, the hub that runs them
end to end.

| | Module | For |
|---|---|---|
| 🔵 | [Panta Rhei Reframe](https://github.com/fairyanna85/pantarhei-reframe) | Working out what the real problem is |
| 🟣 | [Panta Rhei Brainstorm](https://github.com/fairyanna85/pantarhei-brainstorm) | Brainstorming and idea generation |
| 🟢 | [Panta Rhei Solve](https://github.com/fairyanna85/pantarhei-solve) | Structuring and diagnosing problems |
| 🔴 | [Panta Rhei Challenge](https://github.com/fairyanna85/pantarhei-challenge) | Red-teaming ideas and claims |
| 🟡 | [Panta Rhei Decide](https://github.com/fairyanna85/pantarhei-decide) | Making the call |
| ⚫ | [Panta Rhei](https://github.com/fairyanna85/pantarhei) | The pack: all five, end to end |

## Credits and license

Methods are credited to their originators in `catalog.json` and on every card; all descriptions are
our own wording. Code: MIT. Method text: CC BY 4.0. Propose a method: see [CONTRIBUTING.md](CONTRIBUTING.md).
