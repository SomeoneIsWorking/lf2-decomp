# Little Fighter 2 decomp

Reverse engineering of **Little Fighter 2 v2.0a** for PC (`lf2.exe`). It holds the pinned image, a
symbol map from our own reverse engineering, the RE tools and the RE notes. No source is matched
yet.

The native port [lf2-port](https://github.com/SomeoneIsWorking/lf2-port) consumes this repository as a
submodule and reads its guest addresses from the symbol map.

## Bring your own install

No game bytes are ever committed here. Point the tools at your own installed copy:

```
uv run --frozen python tools/verify.py "<install dir>"
```

`config/images.toml` pins `lf2.exe` by size and SHA-256 and records its section table. The verifier
refuses an image that differs.

## Layout

| path | what |
|---|---|
| `config/images.toml` | the image: file, size, SHA-256, image base, sections, symbol file |
| `config/symbols/lf2.txt` | the symbol map, splat `symbol_addrs` format (`name = 0xADDR; // type:func`) |
| `docs/notes/` | behaviour notes on guest routines, data and the platform surface |
| `docs/re-frontier.md` | the ordered RE evidence chain (`re_frontier.py` from re-harness) |
| `docs/prior-art.md` | other work on this build, licences and what we take |
| `docs/our-names.md` | addresses the port names more than once |
| `tools/verify.py` | the image check above |
| `tools/re/` | data-file decryption, `.data` dump diffing and Ghidra automation |

Notes cite lf2-port paths (`runtime/...`, `docs/issues/...`) where a port owner or an issue holds
the evidence.

## Licence

MIT (`LICENSE`), covering this repository's own files only. Little Fighter 2 is © Marti Wong and
Starsky Wong; nothing of it is distributed here.

Built with AI assistance (Claude and other LLMs).
