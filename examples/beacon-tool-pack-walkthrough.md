# Beacon Tool Pack Scope Walkthrough

This note is the quickest way to read the extra review model in `beacon-tool-pack-scope`.

| Case | Focus | Score | Lane |
| --- | --- | ---: | --- |
| baseline | file span | 191 | ship |
| stress | terminal width | 151 | ship |
| edge | argument risk | 175 | ship |
| recovery | report density | 230 | ship |
| stale | file span | 260 | ship |

Start with `stale` and `stress`. They create the widest contrast in this repository's fixture set, which makes them better review anchors than the middle cases.

The next useful expansion would be a malformed fixture around terminal width and report density.
