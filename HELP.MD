# PDFOSC Help Guide

<div>
<h2>Welcome to PDFOSC</h2>
<img src="public/PDFOSC_Logo.png" width="100" alt="PDFOSC Logo" align="left"/>

</br>
This guide is for PDFOSC <b>version 3.0.0</b>, the native PDF viewer with Open Sound Control.</br>
Use it for a live show, a class, or an installation.</br>
Version 1 was an Electron app with PDF.js. The OSC addresses below are the same ones.</br>
Downloads: <a href="https://github.com/chilibytesdotcom/pdfosc/releases">Releases</a>.
</div>

</br>

---

## Getting Started

### System requirements

- Windows 10 or later, macOS 13 or later (Apple Silicon and Intel), or a recent Linux desktop
- A local network or loopback, if you use OSC
- An OSC controller. The Companion module is in stable: [companion-module-chilibytes-pdfosc](https://github.com/bitfocus/companion-module-chilibytes-pdfosc). In Companion, add a connection and search for “PDFOSC”.

### Installation and first launch

1. **Download** the [latest release](https://github.com/chilibytesdotcom/pdfosc/releases) for your machine
2. **Launch** PDFOSC
3. **Open** a PDF

A launch with no file shows a short welcome, then an empty canvas. You can also pass a `.pdf` path as the first argument (“Open with”).

**Note:** Password-protected PDFs are refused with “Password-protected PDF: remove the protection before using it.” On macOS, AppleDouble names (`._….pdf`) are hidden in the open panel and are not opened from the command line either.

### Opening PDF files

| How | Action |
|-----|--------|
| **File menu** | File → Open PDF… |
| **Toolbar** | Open button |
| **Keyboard** | `O` or `Ctrl/Cmd+O`, including while a presentation is running |
| **Drag and drop** | Drop a PDF onto the window |

---

## Keyboard navigation

### Basic navigation

| Key | Action |
|-----|--------|
| **Space** | Next page |
| **Backspace** | Previous page |
| **←** / **Page Up** | Previous page |
| **→** / **Page Down** | Next page |
| **↑** / **↓** | Previous page / next page |
| **Home** | First page |
| **End** | Last page |
| **Digits + Enter** | Jump to that page. Ignored while OSC Config, Help, About, or Check Update is open |

### Advanced

| Key | Action |
|-----|--------|
| **Ctrl/Cmd + ↑** | First page |
| **Ctrl/Cmd + ↓** | Last page |
| **+** / **=** | Zoom in, 10% steps. Off during single-screen presentation and in the presenter view |
| **-** | Zoom out, same limit |
| **O** / **Ctrl/Cmd+O** | Open a PDF |
| **H** | Help |
| **Ctrl/Cmd+Q** | Quit |

### Presentation keys

| Key | Action |
|-----|--------|
| **P** or **Ctrl/Cmd+L** | Enter presentation. **P** also leaves single-screen presentation |
| **Esc** | Leave single-screen presentation, close the projector, or close a modal |

---

## Presentation

| Setup | Behavior |
|-------|----------------|
| **One screen** | The main window goes fullscreen and shows the page only. **Config → Mode → Presenter/Operator** does not change this path |
| **Second screen, Presenter off** | A borderless **PDFOSC — Projector** window opens on the other display. The main window stays windowed so you can run the show |
| **Second screen, Presenter on** | The preference is **Config → Mode → Presenter** and it is remembered. The projector still shows the current page only. The main display shows the current page and the next page, with `current / total` above. On the last page the next slot is empty |

The main window stays a normal window for as long as the projector exists.

| Control | Behavior |
|---------|----------|
| **Cue** | Under Operator, on a dual screen. The window stays the Operator window. A thumbnail click previews a page on this screen. Enter puts that page on the projector. The check is off while Presenter is selected, and the stored value stays |
| **Hidden pages** | The button beside Thumbnails. On, next and previous skip hidden pages, and a right-click on a thumbnail hides or shows that page. The counter stays the real PDF number. Turning it off shows every page and leaves the saved data in place |
| **Thumbnails** | They follow the page on air. After you scroll the list, it returns to the current page about 3 seconds after you stop |

---

## OSC remote control

The listener binds `0.0.0.0`. Any device that can reach the machine can send a command. There is no password. Use a dedicated show network or a firewall when the LAN is not yours alone.

**Press only:** a command runs when the message has no arguments, or when the first argument is a press (an integer or float greater than 0, or `true`). `0` and `false` (button release) are ignored, so a press-and-release controller advances one page.

### Commands

| Address | Action |
|---------|--------|
| `/pdfosc/next` | Next page |
| `/pdfosc/prev` | Previous page |
| `/pdfosc/firstpage` | First page |
| `/pdfosc/lastpage` | Last page |
| `/pdfosc/presentation` | Enter presentation |
| `/pdfosc/exitpresentation` | Leave presentation |
| `/pdfosc/version` | The app replies with its version string |

### Feedback

Sent while presenting. At rest the values are current 0, total 0, state `1`. UDP can drop packets. They leave the app in order.

| Address | Value |
|---------|--------|
| `/pdfosc/current` | Current page |
| `/pdfosc/total` | Page count |
| `/pdfosc/state` | `1` idle, `3` presentation |

---

## Configuration

**Config** stays open while you change a row.

| Row | What it does |
|-----|----------------|
| **Theme: Dark** or **Theme: Light** | The theme that is on. Click to flip. With no settings file the theme is light |
| **Mode** | **Operator** or **Presenter**. Operator is the window with the controls. Presenter, with a second monitor, shows the current page and the next page |
| **Cue** | Under Operator. See Presentation above |
| **Purge Data → Clear this data** | Deletes the saved hidden-page data for the open file |
| **Clear All Data** | Deletes it for every opened file, including this one. The Hide Pages switch stays as it is |

The lists are in `hidden-pages.json`, next to `config.json`, in the OS config directory for `com.pdfosc.pdfosc`, outside the app. Replacing the app leaves that file in place.

### OSC settings

**Config → OSC…**

| Setting | What it does |
|---------|----------------|
| **Target IP** | Where feedback goes (IPv4). Default `127.0.0.1`. An unreadable address falls back to loopback |
| **Output port** | Feedback destination. Default `55551` |
| **Listen port** | UDP port for commands. Default `55550`. On a first run, if the chosen port is busy, the app tries **55550–55560** |
| **Test** | Sends current `99`, total `99`, state `3`, so you can see the receiver move |
| **Save** | Applies the new settings only after the new listen port is actually bound. If the bind fails, the previous listener and the previous settings stay |

The listen port must be non-zero and different from the output port.

---

## Check Update and About

**Help → Check Update** asks GitHub for the Latest release and compares it with this build. It does not run at startup, and it does not run during a presentation. It does not download and it does not install.

| Notice | Meaning |
|--------|---------|
| **Checking** | The request is in flight |
| **Up to date** | Latest is this version or older. The notice hides itself after a few seconds |
| **A newer tag** | Shown as a link to the release page. The notice stays until you dismiss it |
| **Failed** | The network fails, the body cannot be read, or the Latest tag is not a version number (`3.0.1` or `v3.0.1`). A pre-release suffix is ignored (`v3.0.1-beta` counts as `3.0.1`) |

Until the public Latest is a `v3.x.y` tag of this app, the result is Failed. A version 1 tag is not offered as an update.

**Help → About PDFOSC** exists on Windows and shows the version plus the build id. On macOS that text is in the system About menu.

---

## Troubleshooting

### Application

**PDFOSC will not start**  
Use a build for your machine (macOS universal, Windows x64). Check that the OS is in the range above.

**A PDF will not open**  
Try another viewer, and check that you can read the file. Remove a password. The message is “Password-protected PDF: remove the protection before using it.” Copy the file onto a local disk. Names that start with `._` are skipped on purpose.

**The window freezes on a heavy page**  
The page is drawn on the interface thread. After that page is on screen, the neighbors are prepared on later frames.

### OSC

**OSC commands do nothing**  
Open **Config → OSC…** and confirm the listen port. Confirm the firewall, and that the controller is aimed at this machine. A release value (`0` or `false`) is ignored.

**There is no feedback**  
Feedback for the live page is sent in presentation (`state` 3). Press **Test**. It sends `99 / 99 / 3`. Check the target IP and the output port.

### Presentation

**The projector is missing or on the wrong screen**  
The app looks for a display that is not the primary one. One monitor uses fullscreen on the main window instead. On Windows, two monitors with different scaling can still place the projector window badly: reconnect the display or restart the app.

**You cannot leave presentation**  
**Esc** on the main window or on the projector. **P** in single-screen mode. OSC `/pdfosc/exitpresentation`.

---

## Getting help

- **[Repository](https://github.com/chilibytesdotcom/pdfosc)** — this program
- **[Releases](https://github.com/chilibytesdotcom/pdfosc/releases)** — downloads
- **[Issues](https://github.com/chilibytesdotcom/pdfosc/issues)** — bugs and requests

Before opening an issue: read this guide, note the OS and the PDFOSC version, write the steps that show the problem, and try another PDF to see whether the file is the cause.

---

## Version information

This guide describes **PDFOSC 3.0.0**.
Version 1.0.0 was the Electron and PDF.js release. Its OSC addresses are still the ones in this guide.

For the latest builds, visit the [repository](https://github.com/chilibytesdotcom/pdfosc) and [Releases](https://github.com/chilibytesdotcom/pdfosc/releases).

PDFOSC is licensed under the [ISC License](LICENSE). Third-party notices: [THIRD_PARTY.md](THIRD_PARTY.md).

<div align="center">
  <b>© <a href="https://chilibytes.com" target="_blank">ChiliBytes.com</a></b>
</div>
