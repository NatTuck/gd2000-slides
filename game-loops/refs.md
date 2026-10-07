---
title: "Game Loops"
subtitle: "Reference Notes"
author: "GD 2000 — Game Design"
date: today
format:
  revealjs:
    theme: [default, custom.scss]
    slide-number: true
    incremental: false
    controls: true
    progress: true
    hash: true
    center: false
    code-line-numbers: true
    chalkboard: true
    footer: "GD 2000 · Game Loops — Reference"
    preview-links: auto
    fig-align: center
    width: 1280
    height: 800
    margin: 0.08
---

## Roadmap {.smaller}

**The Loop**

1. The core loop: action → feedback → reward → motivation
2. The engine loop (the code sense)
3. Loops nest; tight vs loose

**Mechanics That Modify the Loop**

4. Decisions & agency
5. Chance & information
6. Skill & mastery
7. Resources, risk & economy
8. Progression & escalation
9. Feedback loops & balance
10. Time, juice, people & story

**Application**

11. The seven games side by side
12. Reading, balancing, and designing a loop

::: {.notes}
A condensed handout version of the lecture. One slide per mechanic family.
:::

## The Core Loop {.smaller}

**Action → Feedback → Reward → Motivation → repeat**

| Stage | Meaning | Fails when… |
|---|---|---|
| **Action** | the core *verb* the player performs | the verb is unclear |
| **Feedback** | what the game shows / sounds / feels back | it is slow or illegible |
| **Reward** | what the player gains (power, progress, information, story) | it feels unearned |
| **Motivation** | why they go again (curiosity, mastery, goal) | there is no reason |

The **decision** is what turns a loop into a game. Ask of every pass: *what did
the player decide?*

::: {.notes}
Everything else is a mechanic wrapped around these four stages.
:::

## The Engine Loop {.smaller}

The loop in the code — a *different* sense of "game loop":

```c
while (running) {
  poll_input();
  update(dt);
  render();
}
```

| | Design loop | Engine loop |
|---|---|---|
| Who runs it | the player | the computer |
| Timescale | seconds → hours | milliseconds |
| Failure | boredom, confusion | lag, jank, bugs |

The engine loop is the **substrate**; the design loop is the **point**. Feedback
later than ~**100 ms** feels disconnected. Non-digital games have no engine loop
at all — only the design loop.

::: {.notes}
The name "game loop" refers to both; keep them distinct. Everything else is the
design loop.
:::

## Loops Nest; Tight vs Loose {.smaller}

| Loop | Timescale | Digital example | Tabletop example |
|---|---|---|---|
| **Micro** | seconds | aim → shoot → the enemy reacts | move a piece → see the reply |
| **Meso** | minutes | clear a room → reach a checkpoint | win a hand of poker |
| **Macro** | hours | level up → finish the campaign | win the tournament |

- **Tight** loops — short, immediate (*Tetris*, *Jenga*, a poker hand).
- **Loose** loops — long, deferred (*chess*, *Monopoly*, a *D&D* campaign).

Each loop **feeds** the next; designers tune the handoff. "One more turn" and
"one more hand" are loose loops that *feel* tight.

::: {.notes}
Flat-feeling games usually have only one timescale designed.
:::

## Decisions & Agency {.smaller}

| | *Chess* | *Snakes and Ladders* |
|---|---|---|
| Decisions per loop | every move | **none** |
| Skill | deep | none |
| Chance | none | pure |

A loop with no decisions **repeats but isn't played**. Design test: for each
pass, *what did the player decide?*

::: {.notes}
Snakes and Ladders is the baseline control; Uno is the same simplicity plus
choices.
:::

## Chance & Information {.smaller}

- **Input randomness** — dealt *before* you decide; you plan around it
  (*Tetris*, *Hold'em* hole cards, *Uno* draw).
- **Output randomness** — settles the outcome *after* you decide (*Snakes and
  Ladders*). This is where "that's unfair!" comes from.
- **Perfect information** (*Chess*) — the loop is calculation.
- **Hidden information** (*Hold'em*) — the loop is inference and deception;
  bluffing and reading live *between players*.

::: {.notes}
Push randomness toward the input side to give players control.
:::

## Skill & Mastery {.smaller}

- **Execution** — precise, under pressure (*Tetris*, *TF2*).
- **Knowledge / calculation** — the right move (*Chess*).
- **Judgment under uncertainty** — (*Hold'em*, *TF2* positioning).

A loop is only as interesting as the **skill it tests**. Low floor, high
ceiling: easy to start (*Tetris*, *Uno*), hard to master (*Chess*, *Hold'em*,
*TF2*). Mastery keeps the macro loop alive.

::: {.notes}
If a machine or spreadsheet can solve it, the loop is over.
:::

## Resources, Risk & Economy {.smaller}

- **Economy** — a currency with **sources** and **sinks** (chips, material,
  cards, metal, time). No sink → meaningless; no source → frustrating.
- **Risk** — the loop can *cost* you (*Hold'em* bets, chess sacrifices, *TF2*
  pushes). **Push-your-luck**: reward and danger scale together.

Without risk, decisions are just optimizations.

::: {.notes}
The loop is the pump that moves value between sources and sinks.
:::

## Progression & Escalation {.smaller}

- **Progression** — a second loop that changes *you* (*BG3* levels, *TF2*
  unlocks; chess rating = *player* progression). It gives the loop a **memory**.
- **Escalation** — raise the **stakes**, not the **rules** (*Tetris* speed,
  rising poker blinds, *TF2* sudden-death).
- **Session vs career** loops: minutes–hours vs days–years. Align them.

::: {.notes}
Difficulty is the shape of the escalation curve.
:::

## Feedback Loops & Balance {.smaller}

- **Positive feedback** — rewards the leader, so advantage compounds (*Chess*
  material, *Hold'em* big stack, *Monopoly* rent, *TF2* snowball). Risk:
  runaway leader.
- **Negative feedback** — helps the loser (*Uno* Draw Two, *Mario Kart* items,
  rising blinds). Risk: the lead stops mattering.
- **Balance** — no **dominant strategy**, or the decision disappears and you're
  back to *Snakes and Ladders*.

::: {.notes}
Balance is the mixture of the two — momentum plus hope.
:::

## Time, Juice, People & Story {.smaller}

- **Time** — turn-based (*Chess*, *Hold'em*, *Uno*) vs real-time (*Tetris*,
  *TF2*).
- **Juice** — feedback bigger than it needs to be; makes the loop legible and
  satisfying (~100 ms rule).
- **People** — a social loop where players are each other's feedback; often the
  strongest retention mechanic.
- **Story** — reward as *meaning*; the slowest and often stickiest loop
  (*Baldur's Gate 3*).

::: {.notes}
Narrative turns the loop's reward into story rather than numbers.
:::

## The Seven Games Side by Side {.smaller}

::: {.games-table}
| Game | Core verb | Key mechanics | Loop length |
|---|---|---|---|
| **Chess** | move | perfect information, skill, no chance | long |
| **Snakes & Ladders** | roll | pure chance, no decisions | short |
| **Tetris** | place | real-time, execution, escalation | tight |
| **Texas Hold'em** | bet | hidden information, risk, resources, social | medium |
| **Uno** | play a card | chance, take-that, catch-up | short |
| **TF2** | shoot | real-time, team, roles, economy | medium |
| **Baldur's Gate 3** | choose | narrative, progression, exploration | long |
:::

Same four stages in every row. What differs is *which mechanics* surround them.

::: {.notes}
Seven very different games, one shared skeleton.
:::

## Reading, Balancing & Designing {.smaller}

**Read — five steps:** the verb; the feedback and reward; the motivation; the
mechanics (which stage each touches); the nested loops.

**Balance — keep every pass worth playing:** a goal in view; skill matched to
challenge; positive *and* negative feedback; a real choice each pass; escalation
that tightens.

**Common failures:** no decisions (*Snakes and Ladders* trap); dominant
strategy; runaway leader; illegible feedback; stale loop.

**Design — five questions:** the core verb; what they get; why they return;
which mechanics modify the loop; where it could feel stale, unfair, or slow.

::: {.notes}
Every failure is a mechanic problem — cheap to fix early, expensive to fix late.
:::
