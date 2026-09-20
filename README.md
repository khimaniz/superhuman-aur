# Superhuman AUR (personal fork)

Fork of [JoeyEamigh/superhuman-aur](https://github.com/JoeyEamigh/superhuman-aur), an unofficial AUR autopublisher for the [Superhuman](https://superhuman.com) email client. This fork carries two fixes not (yet) in upstream:

1. **App launched but showed no window.** The upstream "Ctrl shortcuts for Linux" patch called a method (`_registerWindowsShortcuts`) that doesn't exist in the shipped bundle, throwing during window creation. Removed - the code path below it already handles Linux fine via `CmdOrCtrl` accelerators.
2. **Google sign-in never returns to the app.** Superhuman has no official Linux client, so the OAuth flow doesn't hand off via `superhuman://` on Linux - it lands on a real `https://mail.superhuman.com/~login#...` URL and falls back to browser-only onboarding. Added `superhuman-login`, a helper installed to `/usr/bin/superhuman-login`: after completing Google auth, copy that URL from the address bar and run `superhuman-login '<url>'` to complete sign-in manually.

## Installation

Manual (this fork isn't published to the AUR):

```bash
git clone https://github.com/khimaniz/superhuman-aur.git
cd superhuman-aur
makepkg -si
```

## Legal

This project is not affiliated with Superhuman. This project does not distribute any Superhuman code - downloads happen on end user devices.

## Credits

Inspired by [superhuman-linux](https://github.com/zicochaos/superhuman-linux) (happy to merge backwards into yours if you want).
