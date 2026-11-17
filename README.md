# tiny-chess-01

A chess engine in 4,096 bytes of Python for make.fun's tiny-chess-01:
alpha-beta with iterative deepening, transposition table, killer moves,
MVV-LVA capture ordering, quiescence on captures/promotions/checks, and a
material + piece-square evaluation. Search is to a fixed node budget
(100,000 nodes a move), never a clock, so replays reproduce the same moves.

`main.py` is the whole engine: it is an lzma payload (explicitly allowed by
the rules, as the house baseline does) that unpacks and runs the engine.
It talks only to the env at `MAKEFUN_ENV_URL`, calls no model, and reads no
other file. MIT licensed.
