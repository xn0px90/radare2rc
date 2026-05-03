# .radare2rc

A small collection of **radare2** configuration settings for a nicer default experience in both command-line and visual mode.

This repository is essentially a curated `~/.radare2rc` you can copy into place (and then tweak to taste).

## What is this?

radare2 loads an rc file at startup (commonly `~/.radare2rc`). The commands in that file are executed automatically and can:

- change UI/visual defaults
- enable ESIL emulation helpers
- adjust disassembly output (comments, pseudocode, descriptions)
- set theme/UTF-8 options
- tweak sandbox settings

## Included settings (high level)

This rc enables:

- Right-side disassembly comments (`asm.cmtright`)
- Pseudocode-like operand formatting (`asm.pseudo`)
- ESIL + emulation (`asm.emu`, `asm.esil`)
- Stack/register display in visual mode (`cmd.stack`)
- Dark colorscheme (`eco dark`)
- UTF-8 UI glyphs (`scr.utf8`)
- Instruction/operand descriptions (`asm.describe`)
- Disables sandboxing (`cfg.sandbox=false`) — see notes below

## Install

1. Clone the repo:

   ```sh
   git clone https://github.com/xn0px90/radare2rc.git
   cd radare2rc
   ```

2. Copy the rc file into place.

   If this repo contains a file named `.radare2rc`, copy it to your home directory:

   ```sh
   cp .radare2rc ~/.radare2rc
   ```

   If the configuration is stored in another file in this repo, copy that file instead.

3. Start radare2 and verify the settings loaded:

   ```sh
   r2 -q -c 'e asm.cmtright' /bin/ls
   ```

## Usage

radare2 automatically reads `~/.radare2rc` at startup.

If you want to load the config manually inside an existing session, you can:

```sh
r2 -c '. ~/.radare2rc' /path/to/binary
```

Or from inside r2:

```r2
. ~/.radare2rc
```

## Security notes (sandbox)

This configuration sets:

```r2
e cfg.sandbox=false
```

Disabling the sandbox can make radare2 more permissive/convenient, but it can also increase risk when opening untrusted files or using external commands/scripts.

If you commonly reverse unknown/untrusted samples, consider keeping sandbox enabled (or remove that line).

## Contributing

PRs/issues are welcome:

- improvements to defaults
- architecture-specific tweaks
- visual mode quality-of-life settings

## License

No license file is currently included. If you want this to be explicitly reusable, consider adding a license (e.g., MIT/Unlicense/CC0).
