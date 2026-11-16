# Tiny Chess 4K — draft

Private, unsubmitted draft for Make.fun's `tiny-chess-01` bounty. `main.py` is a standalone Python 3.13 standard-library engine; it sends UCI moves to the supplied `MAKEFUN_ENV_URL` and makes no model calls.

The engine uses a 0x88 board, legal-move generation, alpha-beta negamax with capture quiescence, material/positional evaluation, and a fixed 60,000-node budget. Search is deterministic and does not depend on wall-clock time or randomness.

`main.py` packs the complete implementation with base85 + zlib to stay within the 4,096-byte entrypoint cap; it unpacks and runs only the bytes embedded in that file. A human-readable review copy is supplied separately, not as a runtime dependency.

Local check: `node cli/makefun.mjs grade-local --kit . --bot <repo> --driver docker` (requires Docker).