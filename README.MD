# PDFOSC

<img src="public/PDFOSC_Logo.png" width="120" alt="PDFOSC Logo" />

PDFOSC is a PDF viewer and presenter with **Open Sound Control (OSC)**.
It is a short interface for a live show, a class, or an installation:
remote control from another device, and real-time page feedback while a presentation is running.

**Version 3.0.0** is one native desktop program (Rust, Pdfium). There is no browser inside it.
Version 1 was an Electron app that drew the PDF with PDF.js. That code is not this tree.
The OSC addresses are the same, so a controller from version 1 does not have to be rewritten.

With PDFOSC, you can:

- Control the presentation remotely with OSC commands
- Send real-time updates of the current page, the page count, and the presentation state
- Jump to the first page, the last page, or a typed page
- Use the common presentation shortcuts
- Show thumbnails, and zoom the page
- Go fullscreen on one monitor, or open a borderless projector on a second monitor
- Use a presenter view (current page and next page) on the main display
- Preview a page with Cue, and skip hidden pages
- Switch the theme, and check for a newer release without installing it from inside the app

Downloads: [Releases](https://github.com/chilibytesdotcom/pdfosc/releases) · guide: [HELP.MD](HELP.MD)

---

## Requirements

- **Windows 10** or later, **macOS 13** or later (Apple Silicon and Intel), or a recent **Linux** desktop
- A local network or loopback, if you use OSC
- An OSC controller. The Companion module is in stable: [companion-module-chilibytes-pdfosc](https://github.com/bitfocus/companion-module-chilibytes-pdfosc). 
  In Companion: Connections → Add Connection → search for “PDFOSC”.

---

## 💬 Support

- **[GitHub Issues](https://github.com/chilibytesdotcom/pdfosc/issues)** — report a bug or request a feature
- **[HELP.MD](HELP.MD)** — keys, OSC, configuration, and problems in the room
- **[Releases](https://github.com/chilibytesdotcom/pdfosc/releases)** — download Latest

With an issue, include the OS, the PDFOSC version, and the steps.

---

## 📋 Version history

### v3.0.0

- Native app. Pdfium renders the page. The OSC addresses are unchanged
- One monitor, projector, Presenter, Cue, and hidden pages
- Thumbnails, zoom, theme, and a manual update check
- Companion module already in Companion stable

### v1.0.0

- First public release
- OSC control and page feedback
- PDF.js rendering inside Electron

---

**Help → Check Update** compares this version with GitHub Latest and opens the release page. It does not download and it does not install. A useful answer needs Latest to be a `v3.x.y` tag. Until then the check reports failure. That is expected while the public Latest is still a version 1 tag.

---

## 📄 License

PDFOSC is licensed under the **[ISC License](LICENSE)**. Copyright ChiliBytes.

Third-party notices, including Pdfium (Apache-2.0) and the Ubuntu fonts: **[THIRD_PARTY.md](THIRD_PARTY.md)** · Apache text in [`licenses/Apache-2.0.txt`](licenses/Apache-2.0.txt) · Ubuntu fonts in [`assets/fonts/LICENCE.txt`](assets/fonts/LICENCE.txt).

---

## 🙏 Acknowledgements

- **Developed and maintained by** [ChiliBytes](https://chilibytes.com)
- **PDF rendering by** [Pdfium](https://pdfium.googlesource.com/pdfium/) (Apache-2.0)
- **Interface by** [egui](https://github.com/emilk/egui) / [eframe](https://github.com/emilk/egui/tree/master/crates/eframe)
- **Version 1.0.0** used PDF.js and Electron. Those are not part of this program
