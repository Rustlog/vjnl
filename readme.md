# vjournal

## Single-file journal CLI written in pure Bash.

### Features
- dated daily logs (`vjournal edit-journal` -> today's entry)
- evergreen "specials" (`vjournal edit thoughts`)
- basic file-level encryption (substitution chipher)
- template support with `-t`
- smart inference: `vjournal edit foo` / `vjournal show foo`
- external pager (bat or less), pretty colors, verbose/debug logging
- minimal dependencies

### Security note
The 'encryption' is a dead simple monoalphabetic substitution cipher (tr with shuffled alphabets).
Obsecures the plaintext at first glance but offers zero cryptographic encryption.
Fine for non-sensitive journaling, not for secrets.

### Install

```bash
curl -f#SL https://raw.githubusercontent.com/Rustlog/vjnl/main/vjournal -o ~/.bin/vjournal
chmod +x ~/.bin/vjournal
```

### Examples
```bash
vjournal edit-journal          # today's log (blank template)
vjournal edit-journal -t blank # explicit blank
vjournal edit-journal -t default # default template (opiniated maybe)
vjournal edit linux            # evergreen note "linux"
vjournal show linux            # pretty view with pager
vjournal --no-pager show linux # pretty print without pager
```

### Full usage
```bash
vjournal --help # or `vjournal --full-help` with examples
```

