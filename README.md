# Gambit-4K

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Tenguu0/gambit-4k/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Tenguu0/gambit-4k/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in 4,096 bytes of Python, written from scratch for the
[make.fun](https://make.fun/bounty/tiny-chess-01) tiny-chess-01 bounty.
It plays the house gauntlet through the env at `MAKEFUN_ENV_URL`.

## Engine

`main.py` (at most 4,096 bytes) is the whole engine: an lzma-compressed,
self-contained program using only the standard library. It implements:

- 0x88 board and fully legal move generation (castling, en passant,
  promotion, check, stalemate, insufficient material, repetition,
  fifty-move)
- Negamax alpha-beta with iterative deepening to a fixed node budget
  per move (deterministic: no clock, no unseeded randomness)
- Quiescence search (captures, promotions, check evasions) with
  delta pruning, transposition table, MVV-LVA and killer move ordering
- Evaluation: material + piece-square tables (including an endgame
  king table) + bishop pair

## License

MIT — see [LICENSE](LICENSE).
