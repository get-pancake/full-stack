<p align="center">
  <img src="assets/hero.svg" alt="Pancake Tower. We promised a world record. Here's the recipe." width="100%">
</p>

<p align="center">
  <img alt="Oct 29: taller than the record, fell before 5 s" src="https://img.shields.io/badge/Oct%2029-taller%2C%20fell%20before%205%20s-E33A6A?style=flat-square&labelColor=2C002A">
  <img alt="Record to beat: 42.6 in" src="https://img.shields.io/badge/record%20to%20beat-42.6%20in-FF7AA0?style=flat-square&labelColor=2C002A">
  <img alt="Stop line: 45 in" src="https://img.shields.io/badge/stop%20line-45%20in-BA8BFF?style=flat-square&labelColor=2C002A">
  <img alt="Attempt: Oct 29, 2026" src="https://img.shields.io/badge/attempt-Oct%2029%2C%202026-FFBD7A?style=flat-square&labelColor=2C002A">
  <img alt="Python 3.11+, no dependencies" src="https://img.shields.io/badge/python-3.11%2B%20%C2%B7%20no%20deps-68CEA7?style=flat-square&labelColor=2C002A">
  <a href="../../actions/workflows/spec-check.yml"><img alt="Spec check" src="../../actions/workflows/spec-check.yml/badge.svg"></a>
</p>

<p align="center">
  <a href="https://get-pancake.github.io/full-stack/"><b>The page</b></a> ·
  <a href="RECIPE.md">Recipe</a> ·
  <a href="STACKING.md">Build protocol</a> ·
  <a href="#calculator">Calculator</a> ·
  <a href="RULES.md">Rules</a> ·
  <a href="TESTLOG.md">Test log</a>
</p>

## The promise

Pancake hit #1 Product of the Day on Product Hunt on Oct 14, 2026. We'd promised a world record if it did.

So we open-sourced our full stack. On Oct 29 we stacked pancakes in San Francisco, live: the recipe, the build protocol, the math, all here. Copy it. Beat us.

> [!IMPORTANT]
> **We didn't get the record.** On Oct 29 our tower got about 1.5 cm (0.6 in) past the 42.6 in record, two or three pancakes higher. It was leaning, someone had to steady it, and once we let go it fell within a second. Taller than the record, but a record has to stand on its own. One attempt, and not a single pancake hit the floor. What went wrong and what we'd change is in [TESTLOG.md](TESTLOG.md). The recipe below is exactly what we cooked.

## The numbers

| | |
|---|---|
| Height to beat | **42.6 in** · 108.3 cm · 230 pancakes · Sydney, 2025 |
| We stop at | **45 in**, then hands off |
| Must stand | **5 s**, freestanding |
| Pancakes in the tower | **~255** to the stop line, in two sizes: 9 in, then 7 in |
| Each pancake | **~0.18 in** (4.5 mm) in the stack. The rule allows 0.39 in |
| To cook | **296** pancakes, 72 batches, 13.8 gal of batter |

## The tower

<p align="center">
  <img src="assets/tower.svg" alt="Elevation and plan of the tower, to scale: 145 pancakes at 9 in, then 7 in pancakes up to 45 in" width="100%">
</p>

Drawn to scale from [`recipe.toml`](recipe.toml) by [`tools/render.py`](tools/render.py). Change a number, re-run it, and the drawing follows.

## How we stack it

- **Thin and dense.** No leavening. Fluffy pancakes compress unpredictably. Ours carry weight.
- **Same cup, same ring, every time.** One batch makes 3 big or 7 small pancakes, so the dose is fixed.
- **A two-step pyramid.** 9 in at the bottom, 7 in on top. Less load low down, more room for a shaky hand.
- **Nothing touches the tower but pancakes.** No rings, no rods, no syrup between layers. Lasers and a freestanding gauge read plumb and height.
- **Stop on height, not on count.** Thickness drifts. The 45 in line doesn't.

## From batter to plate

<p align="center">
  <img src="assets/process.svg" alt="Batter, ring and dose, flip once, cool flat, stack-of-10 check, sort, stack a quarter turn each, stop at 45 in, hold 5 s and measure, eat or donate" width="100%">
</p>

## Calculator

```bash
python3 calc.py                  # the chef's plan: one tower + extras, whole batches
python3 calc.py --attempts 2     # cook for a second attempt
python3 calc.py --thickness 0.17 # re-plan with your measured thickness
python3 calc.py --check          # fail if the spec breaks a rule
```

<details>
<summary>Sample output</summary>

| Size | Ring | In tower | Per batch | Batches | To cook | Batter per pancake |
|---|---|---|---|---|---|---|
| base | 9 in | 145 | 3 | 52 | 156 | 1.02 cup (241 ml) |
| top | 7 in | 125 | 7 | 20 | 140 | 0.44 cup (103 ml) |
| **total** | | **270** | | **72** | **296** | |

Shopping list for one attempt: 18 kg (39.7 lb) all-purpose flour, 72 eggs, 216 tsp sugar, 6.75 gal whole milk, 2.25 gal water, 6 cans of cooking spray. Buy 9 × 5 lb of flour, 7 dozen eggs and 8 gal of milk.

</details>

The [page](https://get-pancake.github.io/full-stack/) runs the same math in your browser.

## The record so far

<p align="center">
  <img src="assets/records.svg" alt="Record heights in inches: 29.9 in 2012, 34.3, 34.4 and 35.9 in 2014, 40.1 in 2016, 42.6 in 2025. Our target: 45 in on Oct 29, 2026" width="100%">
</p>

## What's in here

```
recipe.toml        the spec. Every number lives here
calc.py            cooking plan, shopping list, height check
RECIPE.md          batter, cooking, quality control
STACKING.md        geometry, roles, build protocol
RULES.md           the record rules, and what we're confirming
TESTLOG.md         measured numbers that replace our guesses
data/records.toml  record history, with sources
tools/render.py    draws assets/*.svg and the page from the spec
docs/              the page
```

## Run your own attempt

Fork it, cook it, measure it. Then [report your attempt](../../issues/new?template=attempt-report.yml) or [suggest a recipe variant](../../issues/new?template=recipe-variant.yml). Better numbers win.

`git push --syrup`

## About Pancake

<img src="assets/brand/pancake-monster.svg" alt="" width="64" align="left">

**Pancake gives your agent the brain, the data and the tools to run your go-to-market.**
[pancake.ai](https://pancake.ai)

<br clear="left">

## License

Code: MIT. Docs and recipe: CC BY 4.0. The Pancake name, logo and mascot belong to Pancake and aren't covered by either license. See [LICENSE](LICENSE).
