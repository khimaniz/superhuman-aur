# Superhuman AUR

Unofficial AUR autopublisher for the [Superhuman](https://superhuman.com) email client.

## Installation

AUR helpers:

```bash
paru -S superhuman

yay -S superhuman
```

Manual:

```bash
git clone https://aur.archlinux.org/superhuman.git
cd superhuman
makepkg -si
```

## Google sign-in on Linux

Superhuman's server-side OAuth flow doesn't hand off to the app via `superhuman://` on Linux (there's no official Linux client, so it isn't recognized) - it redirects to a real `https://mail.superhuman.com/~login#...` URL, and the page falls back to browser-only onboarding if nothing intercepts it. If "Sign in with Google" doesn't return you to the app, copy that URL from the address bar right after completing Google auth and run:

```bash
superhuman-login 'https://mail.superhuman.com/~login#...'
```

## Legal

This project is not affiliated with Superhuman. This project does not distribute any Superhuman code - downloads happen on end user devices.

## Credits

Inspired by [superhuman-linux](https://github.com/zicochaos/superhuman-linux) (happy to merge backwards into yours if you want).
