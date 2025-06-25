# `phvm` - PHP Version Manager for macOS

A lightweight Bash-based PHP version manager for macOS using Homebrew. Easily list, switch and manage multiple PHP versions installed via Homebrew or custom paths.

---

## 🚀 Features
- 🔍 List installed PHP versions
- 🔄 Switch between PHP versions (brew link-based)
- 🛠️ Configure custom PHP installation paths via ~/.phvm/.phvmrc
- 📄 View current PHP version
- 🧩 Works with php@<version> formulas (e.g., php@8.2)

## Requirements
- VIM (For editing the config)
- PHP versions installed with [Homebrew](https://brew.sh/)
- macOS`


## 📦 Installation
**1.** Save the script to a file (e.g. `phvm`) somewhere in your `$PATH`, such as:
```sh
mkdir -p ~/.phvm/bin
cp phvm ~/.phvm/bin/phvm
chmod +x ~/.phvm/bin/phvm
```

**2.** Add it to your shell config:
```sh
# ~/.zshrc or ~/.bashrc
export PATH="$HOME/.phvm/bin:$PATH"
```

**3.** Reload your shell:
```sh
source ~/.zshrc
# or
exec zsh
```

---

## 🛠️ First-time Setup
Run:
```sh
phvm init
```

This creates the default config file at `~/.phvm/.phvmrc`, with common PHP installation paths like:
```sh
PHP_DIRS=(
  "/opt/homebrew/opt"
  "/usr/local/opt"
)
```

You can edit it anytime with:
```
phvm config
```

---

## 💡 Usage
```sh
phvm list           # List all detected PHP versions
phvm use 8.2        # Switch to PHP 8.2 (via Homebrew's php@8.2)
phvm current        # Show currently active PHP version
phvm init           # Initialize a default .phvmrc config
phvm config         # Open the config file in vi
phvm help           # Show help
```

---

## 🧠  Notes
- PHP versions must be installed with Homebrew using versioned formulas like php@8.1, php@8.2, etc.
- `phvm use <version>` runs `brew unlink` on all other PHP versions and `brew link` on the target one.
- You can customize your `PHP_DIRS` in `~/.phvm/.phvmrc` if your PHP installs live somewhere else.

## 📬 Feedback
Feel free to fork, modify, and contribute. This is a simple and extensible tool for PHP developers managing multiple versions on macOS.