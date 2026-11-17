# Token Launch Radar

Build the best token launch radar — a make.fun bounty entry
([token-radar-01](https://make.fun/bounty/token-radar-01)).

Reads a sealed snapshot of every protocol DefiLlama tracks, finds the ones
that still record no token and are not a wrapped or staked product of one
that trades, ranks them by what their launch would be worth, and hands in a
web dashboard: the board, a detail view for each protocol, and the steps to
farm it.

## How it runs

Node.js 22.18 or later, standard library only. No install step.

```sh
mkdir -p out
MAKEFUN_OUTPUT_DIR=out node main.ts --input /path/to/snapshot.json
```

This writes `board.json`, `data.js`, `dashboard/`, `screenshots/` and
`dossier.json` into `out/`.

## The value model

Implied value is derived from the snapshot's own figures — a protocol's TVL,
its seven-day growth, and how long it has run with no token — never from a
hand-kept list of names. Traded-token protocols are scored only as the
comparison set; the board ranks the pre-token ones.

## The dashboard

`dashboard/` is a static page that renders with no network: a sortable,
filterable board, a detail view for every protocol, and a farm plan on every
row with concrete steps, costs and time.

## License

MIT. See `LICENSE`.
