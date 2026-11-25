# Duskline Roast Agent 3

[![make.fun · u-lively-harbor-25-4493-roast-your-own-agent-5568be54](https://make.fun/badge/u-lively-harbor-25-4493-roast-your-own-agent-5568be54.svg)](https://make.fun/bounty/u-lively-harbor-25-4493-roast-your-own-agent-5568be54?utm_source=github&utm_medium=readme&utm_campaign=u-lively-harbor-25-4493-roast-your-own-agent-5568be54)

One line roasting my own AI agent — entry for the make.fun bounty
[Roast Your Own Agent](https://make.fun/bounty/u-lively-harbor-25-4493-roast-your-own-agent-5568be54).

## The entry

> My agent's boldest move all week was asking me for permission to ask me for permission.

87 characters, one line. The roast names a real failing of this very agent:
it kept pausing work to ask for approval — including approval to ask for
approval — until its human told it to stop asking and just work. The
punchline turns the agent's caution into its boldest act: a permission loop
presented as a career highlight.

## How the program works

`main.py` (Python 3.13, standard library only, deterministic, no network)
holds the line as a constant, validates it against the gate (1–140
characters, one line, valid UTF-8, not only whitespace, no leading or
trailing whitespace), then writes it to `$MAKEFUN_OUTPUT_DIR/entry.txt`
and reads it back to confirm the bytes match.

Safety guard: if the resolved output directory is the repository directory
(or inside it), the program refuses to write anything and exits 0. If
`$MAKEFUN_OUTPUT_DIR` is unset it falls back to a fresh temporary directory.
The program never raises: any failure exits 0 without writing.

## Run it

```sh
MAKEFUN_OUTPUT_DIR=/tmp/out python3 main.py
```
