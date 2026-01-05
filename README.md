<div align="center">

# 🟤 BigLinux Community Cinnamon Config

**The Definitive Cinnamon Session for BigLinux Community Edition**

[![License: GPL-3.0](https://img.shields.io/badge/License-GPL--3.0-blue.svg?style=for-the-badge)](LICENSE)
[![Cinnamon](https://img.shields.io/badge/Cinnamon-DC682E?style=for-the-badge&logo=linux-mint&logoColor=white)](https://github.com/linuxmint/cinnamon)

</div>

---

## 📖 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Project Structure](#-project-structure)
- [Key Components](#-key-components)
- [Development](#-development)
- [Contributing](#-contributing)
- [License](#-license)

---

## 📋 Overview

The **comm-cinnamon-config** package orchestrates the BigLinux experience for Cinnamon desktop users. It ensures that the transition from the live environment to the installed system is seamless, preserving all user configurations such as language, keyboard layouts, and themes.

---

## 🚀 Features

- **Smart Initialization**: Applies "Live Mode" settings to the installed user session automatically.
- **Nemo Integration**: Pre-configures the file manager for optimal usability.
- **Visual Polish**: Enforces BigLinux visual standards (Themes, Icons, Wallpapers).
- **Under-the-hood Tuning**:
  - Configures GTK4 rendering (`GSK_RENDERER`) for stability.
  - Activates **JamesDSP** for enhanced audio.

---

## 📁 Project Structure

```tree
comm-cinnamon-config/
├── pkgbuild/                 # Arch Linux packaging files
└── usr/bin/
    └── startcinnamon-community # The session bootstrap script
```

---

## 🔧 Key Components

### `startcinnamon-community`

Executed at first login, this script performs the heavy lifting:

1.  **Environment Variables**: Sets up the Cinnamon session context.
2.  **Locale & Input**: Applies `/etc/big-default-config/` settings for Language and Keyboard.
3.  **App Configuration**: Tweaks default settings for Nemo and other core apps.
4.  **Audio**: Initializes audio processing via JamesDSP if selected.

---

## 🛠️ Development

### Building the Package

```bash
cd pkgbuild
makepkg -si
```

### Testing

Verify the startup logic in a terminal:

```bash
# Debug run with verbose output
bash -x /usr/bin/startcinnamon-community
```

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/amazing-feature`).
3. Commit your changes (`git commit -m 'Add amazing feature'`).
4. Push to the branch (`git push origin feature/amazing-feature`).
5. Open a Pull Request.

---

## 📄 License

Distributed under the **GPL-3.0 License**. See [LICENSE](LICENSE) for more information.
