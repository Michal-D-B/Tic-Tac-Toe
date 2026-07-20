# Changelog

All notable changes to this project are documented here.

## v3 — Final
- Collapsed the two separate turn blocks into a single move-handling block, flipping turns with `p_order = not p_order`.
- Fixed win detection: moved the diagonal checks out of the row/column loop so they're checked once per player, and added an explicit `return False`.
- Added a grid-style board display with row and column separators.
- Cleaned up leftover dead code and simplified X/O assignment.

## v2
- Added draw detection so a full board ends the game instead of looping.
- Fixed the X/O choice bug where Player 1 was always forced to X.
- Switched the second mark from Y to the correct O.

## v1
- Initial working version: two-player turns, board display, win detection, and a replay loop.
- Introduced the number-to-coordinate mapping for selecting squares.
