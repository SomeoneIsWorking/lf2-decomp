# AGENTS.md

Facts about this repository; the working rules are the global instructions and the skills.

- Python runs through `uv run --frozen` (`pyproject.toml`, `uv.lock`); no dependencies.
- Check: `uv run --frozen python tools/verify.py "<install dir>"` (the pinned image). Run it in
  every change to `config/images.toml`.
- The symbol map is checked by x86port's `tools/symbol_constants.py` (format, duplicates, sections
  and executable code), which generates the port's constants on every port build:
  `python <x86port>/tools/symbol_constants.py --images config/images.toml --namespace x --output <tmp dir>`.
- A new name goes into `config/symbols/lf2.txt` at its address, in address order, typed `func`
  (an entry), `label` (inside code) or untyped (data), named for the guest concept
  (`FrontEnd_Menu`, `g_ModeMenuSelection`, `s_DateFormat`), not the port file that uses it; the
  port bumps this submodule in the change that uses it.
- `tools/re/` reads the game's own files or the port's dumps: `decrypt_dat.py` (data files),
  `diff_data.py` (two `.data` dumps), `derive_entries.py` and `ghidra_scripts/DecompDump.py`
  (Ghidra). Ghidra projects and decompiler output stay under the gitignored `env-assets/`.
- The frontier: `uv run --frozen python <re-harness>/tools/re_frontier.py <cmd>` from this root.
- Game files never enter git.
