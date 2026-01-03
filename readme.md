# vjournal

## Single-file journal CLI written in pure Bash.

### Features
- dated daily logs (`vjournal edit-journal today` -> today's entry)
- evergreen "specials" (`vjournal edit thoughts`)
- full CRUD operation through cli (list, create, read, edit, delete, copy, and move)
- smart inference: `vjournal edit foo` / `vjournal show foo` / `vjournal edit day=-2`
- pager (bat or less), pretty colors, verbose/debug logging
- basic file-level encryption (substitution chipher)
- minimal dependencies

### Security note
The 'encryption' is a dead simple monoalphabetic substitution cipher (tr with shuffled alphabets).
Obsecures the plaintext at first glance but offers zero cryptographic encryption.
Fine for non-sensitive journaling, not for secrets.

### Install
```bash
# Just binary
curl -f#SL https://raw.githubusercontent.com/Rustlog/vjnl/main/vjournal -o ~/.bin/vjournal
chmod +x ~/.bin/vjournal

# or

# with a man page
git clone https://github.com/Rustlog/vjnl.git && cd vjnl
sudo make install
```

### Examples
```bash
vjournal edit-journal today -t default  # default template (opiniated maybe)
vjournal edit linux                     # evergreen note "linux"
vjournal edit-journal day=today         # today's log (blank template)
vjournal edit-journal -t blank          # explicit blank
vjournal show linux                     # pretty view with pager
vjournal --no-pager show linux          # pretty print without pager
vjournal list journals                  # list journal entires
vjournal delete soul                    # delete `soul` :(
```

### Full usage
```bash
vjournal --help # or `vjournal --full-help` with examples
```

