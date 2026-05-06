# beacon-tool-pack-scope

`beacon-tool-pack-scope` keeps a focused Python implementation around cli tools. The project goal is to package a Python local lab for pack analysis with log and snapshot fixtures, replay consistency checks, and documented operating limits.

## Purpose

The point is to make a small domain rule concrete enough that a reader can change it and immediately see what broke.

## Beacon Tool Pack Scope Review Notes

Start with `file span` and `terminal width`. Those cases create the widest score spread in this repo, so they are the best quick check when the model changes.

## What Is Covered

- `fixtures/domain_review.csv` adds cases for file span and terminal width.
- `metadata/domain-review.json` records the same cases in structured form.
- `config/review-profile.json` captures the read order and the two review questions.
- `examples/beacon-tool-pack-walkthrough.md` walks through the case spread.
- The Python code includes a review path for `file span` and `terminal width`.
- `docs/field-notes.md` explains the strongest and weakest cases.

## Implementation Notes

The repository has two validation layers: the original compact policy fixture and the domain review fixture. They are separate so one can change without hiding failures in the other.

The Python implementation avoids hidden state so fixture changes are easy to reason about.

## Command

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File scripts/verify.ps1
```

## Audit Path

The same command runs the local verification path. The highest-scoring domain case is `stale` at 260, which lands in `ship`. The most cautious case is `stress` at 151, which lands in `ship`.

## Limits

The fixture set is small enough to audit by hand. The next useful expansion is malformed input coverage, not extra surface area.
