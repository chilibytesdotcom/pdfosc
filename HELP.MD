# PDFOSC Help Guide

<div>
<h2>Welcome to PDFOSC</h2>
<img src="https://github.com/chilibytesdotcom/pdfosc/blob/main/public/img/PDFOSC_Logo.png?raw=true" width="100" alt="PDFOSC Logo" align="left"/>

</br>
This guide will help you get the most out of PDFOSC, the PDF viewer with Open Sound Control (OSC) integration.</br>
Whether you're using it for live performances, educational presentations, or interactive installations, 
this guide covers everything you need to know.</br>
</div>

</br>

---

## 🚀 Getting Started

### System Requirements
- Modern operating system (Windows 10+, macOS 11+ (ARM/Intel), Linux (Ubuntu 18.04+, Fedora 32+, Debian 10+))
- Network connectivity for OSC communication
- An OSC capable device (A Companion Module has been submitted and is currently pending approval)


### Installation & First Launch
1. **Download** the latest release for your platform
2. **Launch** PDFOSC from your applications menu
3. **Open** your first PDF file through the File menu or drag-and-drop</br>
**Note:** Due to the architecture of Electron, **the initial launch of PDFOSC may take some time.** Please be patient.</br>
A full refactor using Tauri is currently in progress: this will significantly improve performance and reduce application size.

### Opening PDF Files
- **File Menu**: Use File → Open to browse and select PDF file
- **PDFOSC UI**: Click on the OPEN button to browse and select PDF file
- **Drag & Drop**: Simply drag PDF files onto the application window

---

## ⌨️ Keyboard Navigation

PDFOSC offers optimized keyboard shortcuts designed specifically for presentation environments:

### Basic Navigation
- **Space**: Go to next page
- **Backspace**: Go to previous page
- **Left Arrow** / **Page Up**: Previous page
- **Right Arrow** / **Page Down**: Next page
- **Home**: Jump to first page
- **End**: Jump to last page
- **Direct Page Input**: Type any number followed by Enter to jump to that page

### Advanced Navigation
- **Cmd/Ctrl + Up Arrow**: Jump to first page
- **Cmd/Ctrl + Down Arrow**: Jump to last page
- **Numbers + Enter**: Type page number and press Enter to jump directly
- **J/K**: Alternative next/previous page navigation
- **N/P**: Alternative next/previous page navigation

### Presentation Mode
- **P. MODE**: Click on the P. Mode to enter presentation mode
- **Cmd/Ctrl + L**: Enter presentation mode
- **Escape**: Exit presentation mode
- **Up/Down Arrows**: Navigate pages in presentation mode
- **Direct Page Input**: Type any number followed by Enter to jump to that page

---

## 🎛️ OSC Remote Control

A Companion module is currently pending approval. Once it’s included in the stable release, you’ll find help available [here](https://github.com/chilibytesdotcom/companion-module-chilibytes-pdfosc).

Control PDFOSC remotely using Open Sound Control (OSC) messages:

### Available Commands
- `/pdfosc/next` - Go to next page
- `/pdfosc/prev` - Go to previous page  
- `/pdfosc/firstpage` - Jump to first page
- `/pdfosc/lastpage` - Jump to last page
- `/pdfosc/presentation` - Enter presentation mode
- `/pdfosc/exitpresentation` - Exit presentation mode

### Real-time Feedback
When in presentation mode, PDFOSC sends OSC feedback:
- `/pdfosc/current [page]` - Current page number
- `/pdfosc/total [pages]` - Total number of pages
- `/pdfosc/state [status]` - Presentation mode status

---

## ⚙️ Configuration

### OSC Settings
Access the OSC configuration through the Settings menu:

- **Listen Port**: Port for receiving OSC commands (default: 55550)
- **Send Port**: Port for sending OSC feedback (default: 55551)
- **Target IP**: IP address for OSC feedback (default: 127.0.0.1)

### Network Configuration
- **Firewall**: Ensure OSC ports are not blocked by your firewall
- **Network Interface**: Select the appropriate network interface for OSC communication
- **Port Conflicts**: Verify that OSC ports are not used by other applications

---

## 🛠️ Troubleshooting

### Application Issues

**PDFOSC Won't Start**
- Verify system requirements are met
- If it's first run, **wait**.
- Check file permissions in installation directory
- Try running as administrator (Windows) or with appropriate permissions
- Restart your computer and try again

**PDF Files Won't Open**
- Verify the PDF file is not corrupted (try opening in another PDF viewer)
- Check file permissions and ensure you have read access
- Ensure the PDF is not password-protected or encrypted
- Try copying the file to a different location

### OSC Connection Problems

**OSC Commands Not Working**
- Verify OSC is configured in Settings
- Check port settings
- Ensure firewall is not blocking OSC ports
- Test with OSC monitor software to verify message sending
- Confirm network connectivity between devices

**OSC Feedback Issues**
- To avoid confusion during the show, feedbacks work only in Presentatione Mode
- Press TEST button in **OSC > Conf OSC**, it will send 99/99 as Current/Total
- Check that target IP address is correct
- Verify send port settings
- Ensure receiving application is listening on correct port
- Test network connection between devices

**Network Connectivity**
- Verify both devices are on the same network
- Check for network firewall restrictions
- Test basic network connectivity (ping)
- Try different network interface if available

### Presentation Issues

**Keyboard Shortcuts Not Working**
- Ensure PDFOSC window has focus
- Check if another application is capturing key events
- Try clicking in the PDFOSC window first
- Verify you're not in a text input field

**Presentation Mode Problems**
- Press Escape to ensure you're not already in presentation mode
- Check display settings if using multiple monitors
- Try Cmd/Ctrl+L keyboard shortcut
- Restart application if presentation mode becomes unresponsive


---

## 📞 Getting Help

### Documentation Resources
- **[Official Repository](https://github.com/chilibytesdotcom/pdfosc)** - Latest updates
- **[GitHub Issues](https://github.com/chilibytesdotcom/pdfosc/issues)** - Report bugs or request features

### Community Support
- Search existing GitHub issues for similar problems
- Post detailed bug reports with system information
- Share feature requests and use case scenarios

### Before Contacting Support
1. **Check this guide** for common solutions
2. **Update to latest version** if available
3. **Gather system information** (OS version, PDFOSC version, etc.)
4. **Document the issue** with specific steps to reproduce
5. **Test with different files** to isolate the problem
6. **PDFOSC is a customized version of PDF.js,** and some issues may originate from the underlying PDF.js engine. 
   To facilitate accurate reporting and resolution, please help determine whether a problem stems from PDFOSC-specific modifications or from PDF.js itself.</br>
   If the issue is related to PDF.js, consider reporting it directly to the PDF.js team via **[PDF.JS GitHub Issues](https://github.com/mozilla/pdf.js/issues)**.


---

## 🔄 Version Information

This help guide is updated regularly to reflect new features and improvements.</br>
For the latest information about PDFOSC features and updates, visit the [official repository](https://github.com/chilibytesdotcom/pdfosc).


<div align="center">
  <b>© 2025 <a href="https://chilibytes.com" target="_blank">ChiliBytes.com</a></b>
</div>
