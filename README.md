# passwd// strength_audit

A real-time password strength checker — pure HTML/CSS/JS, no build step, no backend, no data ever leaves the browser.

**[Live demo →](#)** *(add your GitHub Pages link here once deployed)*

![strength checker preview](preview.png)

## Features

- **Real-time evaluation** as you type
- **Show/hide toggle** for the password field
- **5-level strength meter** (Very Weak → Very Strong) with color-coded gauge
- **Rule-based checklist**: length, uppercase, lowercase, numbers, special characters, common patterns, repeated/sequential characters
- **Entropy-based scoring** (bits of entropy from character pool size × length)
- **Estimated time to crack**, based on a fast offline-attack reference point (~10¹⁰ guesses/sec)
- **Actionable suggestions** — tells you exactly what's missing
- **Strong password generator** with one-click copy to clipboard
- Fully client-side — safe to type a real password into, nothing is transmitted or stored

## Tech

Vanilla HTML, CSS, and JavaScript. No frameworks, no dependencies, no build tools.

## Run it locally

Clone the repo and open `index.html` in a browser — that's it.

```bash
git clone https://github.com/YOUR_USERNAME/password-strength-checker.git
cd password-strength-checker
open index.html   # or just double-click the file
```

## How scoring works

1. Each password is checked against 7 criteria (length, character classes, common patterns, repeats/sequences).
2. A weighted score (0–100) is computed from which criteria pass, with penalties for common passwords, repeated characters, and keyboard sequences.
3. The score maps to one of 5 strength levels.
4. Separately, **entropy** is calculated as `length × log2(character pool size)`, and used to estimate a worst-case crack time assuming a fast offline attack.

## Possible extensions

- Check against a live breached-password list (e.g. the [Have I Been Pwned API](https://haveibeenpwned.com/API/v3))
- Package the scoring logic as a standalone npm module
- Add a Node/Python backend for server-side validation on signup forms

## License

MIT — free to use, modify, and learn from.
