# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/ilyiyam1/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/ilyiyam1/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in 4,096 bytes of Python for make.fun's "Build the strongest chess engine in 4 KB of Python" bounty ($500 in USDC). Alpha-beta with iterative deepening, transposition table, killer moves, MVV-LVA capture ordering, null-move pruning, and quiescence on good captures, promotions, and check replies, over a material + piece-square evaluation. Search is to a fixed node budget (150,000 nodes a move, 70,000 after fullmove 60), never a clock, so replays reproduce the same moves. Practice Elo 1,219 mean (1,099 / 1,279 / 1,279), above the 1,154 floor; determinism replay of trial 0 is state-identical.

`main.py` is the whole engine: it is an lzma payload (explicitly allowed by the rules, as the house baseline does) that unpacks and runs the engine. It talks only to the env at `MAKEFUN_ENV_URL`, calls no model, and reads no other file. MIT licensed.

## Run it

```sh
MAKEFUN_ENV_URL=http://localhost:1 python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
