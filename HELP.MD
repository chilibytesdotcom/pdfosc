# PDFOSC Help Guide

<div>
<h2>Welcome to PDFOSC</h2>
<img src="https://github.com/chilibytesdotcom/pdfosc/blob/main/public/img/PDFOSC_Logo.png?raw=true" width="100" alt="PDFOSC Logo" align="left"/>

</br>
This comprehensive guide will help you get the most out of PDFOSC, the PDF viewer with Open Sound Control (OSC) integration. </br>
Whether you're using it for live performances, educational presentations, or interactive installations, 
this guide covers everything you need to know.</br>
</div>

</br>

---

## 🚀 Getting Started

### System Requirements
- Modern operating system (Windows 10+, macOS 13+ (ARM/Intel), Linux Ubuntu 23.04+)
- Network connectivity for OSC communication
- An OSC capable device (A Companion Module has been submitted and is currently pending approval)


### Installation & First Launch
1. **Download** the latest release for your platform
2. **Launch** PDFOSC from your applications menu
3. **Open** your first PDF file through the File menu or drag-and-drop
<b>Due to the architecture of Electron, the initial launch of PDFOSC may take some time. Please be patient.
A full refactor using Tauri is currently in progress, which will significantly improve performance and reduce application size. 

### Opening PDF Files
- **File Menu**: Use File → Open to browse and select PDF files
- **Drag & Drop**: Simply drag PDF files onto the application window
- **Recent Files**: Quick access to recently opened documents via File → Recent
- **Command Line**: Launch with a specific PDF: `pdfosc path/to/your/file.pdf`

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

### Advanced Navigation
- **Cmd/Ctrl + Up Arrow**: Jump to first page
- **Cmd/Ctrl + Down Arrow**: Jump to last page
- **Numbers + Enter**: Type page number and press Enter to jump directly
- **J/K**: Alternative next/previous page navigation
- **N/P**: Alternative next/previous page navigation

### Presentation Mode
- **Cmd/Ctrl + L**: Enter presentation mode (fullscreen)
- **Escape**: Exit presentation mode
- **Up/Down Arrows**: Navigate pages in presentation mode
- **F**: Enter fullscreen (alternative)

### Special Features
- **Direct Page Input**: Type any number followed by Enter to jump to that page
- **UI Page Field**: Click the page input field, enter page number, and press Enter

---

## 🎮 OSC Remote Control

Control PDFOSC remotely using Open Sound Control (OSC) messages:

### Available Commands
- `/pdfosc/next` - Go to next page
- `/pdfosc/prev` - Go to previous page  
- `/pdfosc/firstpage` - Jump to first page
- `/pdfosc/lastpage` - Jump to last page
- `/pdfosc/presentation` - Enter presentation mode
- `/pdfosc/exitpresentation` - Exit presentation mode
- `/pdfosc/goto [page_number]` - Jump to specific page

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
- **Enable OSC**: Toggle OSC functionality on/off
- **Auto-reconnect**: Automatically reconnect on connection loss

### Application Preferences
- **Remember Last Page**: Automatically return to the last viewed page when reopening files
- **Always Start from First Page**: Alternative behavior for consistent presentation starts
- **Window Settings**: Customize window size and position
- **Presentation Mode**: Configure auto-start and display preferences

### Network Configuration
- **Firewall**: Ensure OSC ports are not blocked by your firewall
- **Network Interface**: Select the appropriate network interface for OSC communication
- **Port Conflicts**: Verify that OSC ports are not used by other applications

---

## 🎯 Use Cases & Examples

### Live Performances
**Scenario**: Controlling slides during a musical performance
- Use OSC commands from your performance software
- Map MIDI controllers to OSC messages
- Synchronize slide changes with audio cues
- Monitor current page via OSC feedback

### Educational Presentations
**Scenario**: Remote teaching or interactive lectures
- Control presentations from anywhere in the room
- Use tablet or smartphone with OSC apps
- Enable "Remember Last Page" for session continuity
- Quick navigation with direct page jumping

### Installations & Exhibitions
**Scenario**: Automated or interactive displays
- Network multiple PDFOSC instances
- Create automated presentation sequences
- Integrate with motion sensors or timers
- Remote monitoring and control capabilities

### Conference Presentations
**Scenario**: Professional presentations with backup control
- Primary control via keyboard shortcuts
- Backup OSC control from mobile device
- Quick page jumping for Q&A sessions
- Fullscreen presentation mode

---

## 🔗 External Links

PDFOSC now features smart external link handling:
- **Automatic Browser Opening**: Links in PDF files automatically open in your default system browser
- **Security**: Safe handling of external URLs with user control
- **Supported Protocols**: HTTP, HTTPS, and file:// protocols
- **No Interruption**: Links open externally without affecting your presentation

---

## 🛠️ Troubleshooting

### Application Issues

**PDFOSC Won't Start**
- Verify system requirements are met
- Check file permissions in installation directory
- Try running as administrator (Windows) or with appropriate permissions
- Restart your computer and try again

**PDF Files Won't Open**
- Verify the PDF file is not corrupted (try opening in another PDF viewer)
- Check file permissions and ensure you have read access
- Ensure the PDF is not password-protected or encrypted
- Try copying the file to a different location

**Performance Issues**
- Close other resource-intensive applications
- Use optimized PDF files when possible
- Increase system memory if available
- Clear application cache through Settings menu

### OSC Connection Problems

**OSC Commands Not Working**
- Verify OSC is enabled in Settings
- Check port settings match your OSC controller
- Ensure firewall is not blocking OSC ports
- Test with OSC monitor software to verify message sending
- Confirm network connectivity between devices

**OSC Feedback Issues**
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

**External Links Not Opening**
- Verify default browser is properly configured
- Check system security settings and permissions
- Ensure PDF contains valid, properly formatted URLs
- Test browser functionality independently

---

## 💡 Tips & Best Practices

### Preparation
- **Test Before Use**: Always test your setup before important presentations
- **Backup Plan**: Prepare alternative control methods (keyboard + OSC)
- **File Organization**: Keep PDF files in easily accessible locations
- **Network Testing**: Verify OSC connectivity before live use

### Performance Optimization
- **File Size**: Use compressed PDF files for better performance
- **Memory Management**: Close unused applications before presentations
- **Hardware Acceleration**: Enable if available in system settings
- **Display Settings**: Use appropriate resolution for your display setup

### Presentation Tips
- **Practice Navigation**: Familiarize yourself with keyboard shortcuts
- **Page Numbers**: Know your key page numbers for quick navigation
- **Backup Control**: Set up multiple control methods (keyboard + OSC)
- **Monitor Feedback**: Use OSC feedback to track presentation progress

### OSC Integration
- **Message Timing**: Allow time between rapid OSC commands
- **Error Handling**: Implement retry logic in your OSC controller
- **Network Stability**: Use wired connections when possible for reliability
- **Monitoring**: Set up OSC message monitoring for debugging

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
   To facilitate accurate reporting and resolution, please help determine whether a problem stems from PDFOSC-specific modifications or from PDF.js itself. 
   If the issue is related to PDF.js, consider reporting it directly to the PDF.js team via **[PDF.JS GitHub Issues](https://github.com/mozilla/pdf.js/issues)**.


---

## 🔄 Version Information

This help guide is updated regularly to reflect new features and improvements. For the latest information about PDFOSC features and updates, visit the [official repository](https://github.com/chilibytesdotcom/pdfosc).

### Current Features
- Smart external link handling
- Enhanced keyboard shortcuts  
- Intelligent state management
- Robust OSC integration
- Cross-platform compatibility

---

<div align="center">
<b>📚 Happy presenting with PDFOSC!</b>
</div> 
