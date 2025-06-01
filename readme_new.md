# PDFOSC - Companion Module

<div>
<h2>Overview</h2>
<img src="./img/PDFOSC_Logo.png" width="150" alt="PDFOSC Logo" align="left"/>

</br>
PDFOSC is an advanced PDF.JS based viewer application with comprehensive Open Sound Control (OSC) integration. </br>
This module enables seamless OSC communications between Companion and PDFOSC for professional presentation control.</br>
<b>Enhanced external link handling now opens PDF links in your system browser for better user experience.</br>
OSC feedbacks are intelligently restricted to Presentation Mode ON to prevent confusion during live events.</b></br>
</br>
</br>
With this enhanced module, you can:</br>
- Control PDF document navigation remotely with precision</br>
- Monitor current page and total page count in real-time</br>
- Visualize Presentation mode status with instant feedback</br>
- Experience improved external link handling</br>
- Benefit from enhanced keyboard shortcuts for presentations</br>
</div>

## ✨ New Features & Improvements

- **🔗 Smart External Link Handling**: PDF links now automatically open in your default system browser
- **⌨️ Enhanced Keyboard Shortcuts**: Optimized keyboard controls specifically designed for presentations
- **💾 Intelligent State Management**: Optional "Remember Last Page" functionality with fine-grained control
- **🎯 Improved OSC Integration**: More reliable feedback and control mechanisms
- **🚀 Performance Optimizations**: Faster loading and smoother navigation

## Requirements

- [Bitfocus Companion](https://bitfocus.io/companion) v3.0 or later
- [PDFOSC PDF Viewer](https://github.com/eMMeCodes/Symposium/tree/main/PDFOSC) (latest version)
- Network connectivity between Companion and the PDFOSC machine
- Modern operating system (Windows 10+, macOS 10.15+, Linux Ubuntu 18.04+)

## Installation

1. **Download & Setup**
   - In Companion, navigate to **Connections Tab**
   - In "Add Connection" search for **"PDFOSC"**
   - Click **"ADD"** to create an instance
   - Configure the PDFOSC module settings

2. **Network Configuration**
   - Ensure both machines are on the same network
   - Configure firewall settings if necessary
   - Test connectivity using the built-in connection test

## Configuration

Configure your module with these enhanced settings:

- **Remote IP**: Address of the PDFOSC machine (default: 127.0.0.1)
- **Remote Port**: Port PDFOSC listens for actions (default: 55550)  
- **Listen Port**: Port Companion listens for feedbacks from PDFOSC (default: 55551)
- **Connection Timeout**: Maximum time to wait for responses (default: 5000ms)
- **Auto-Reconnect**: Automatically reconnect on connection loss (default: enabled)

## Features

### 🎮 Actions

- **Navigation Controls**
  - Navigate to next/previous page
  - Jump to first/last page
  - Go to specific page number
  - Smooth page transitions

- **Presentation Management**
  - Enter/exit presentation mode
  - Toggle fullscreen view
  - Control document view state
  - Emergency exit commands

### 📊 Variables

- **Real-time Information**
  - Current page number
  - Total pages count
  - Document view state
  - Connection status
  - Last updated timestamp

### 🔄 Feedbacks

- **Visual Indicators**
  - Document view status indicator
  - Pages progression visualization
  - Connection health status
  - Presentation mode indicator
  - Error state notifications

### 🎨 Presets

The module includes an expanded set of professionally designed button presets:

- **Navigation Presets**: Next, Previous, First, Last page controls
- **Presentation Presets**: Enter/Exit presentation mode
- **Status Presets**: Page counter displays and connection status
- **Quick Access Presets**: Combined navigation and status buttons

## 🔧 Advanced Configuration

### External Link Behavior
- Links in PDFs automatically open in your system's default browser
- Configurable link handling policies
- Support for both HTTP/HTTPS and file:// protocols

### Keyboard Shortcuts
- Optimized for presentation environments
- Customizable key mappings
- Support for number pad navigation
- Multi-platform compatibility (Windows, macOS, Linux)

## 📚 Documentation

For comprehensive documentation:

- **[User Guide](./companion/HELP.md)** - Complete module usage and troubleshooting
- **[PDFOSC Application](https://github.com/eMMeCodes/Symposium/tree/main/PDFOSC)** - Main PDF viewer documentation
- **[API Reference](./docs/api.md)** - Technical integration details
- **[Configuration Examples](./examples/)** - Sample configurations and use cases

## 🛠️ Troubleshooting

### Common Issues

**Connection Problems**
- Verify network connectivity between devices
- Check firewall settings on both machines
- Ensure PDFOSC is running and listening on the correct port

**PDF Display Issues**
- Verify PDF file is not corrupted
- Check file permissions
- Ensure sufficient system memory

**External Links Not Working**
- Verify default browser is properly configured
- Check system security settings
- Ensure PDF contains valid URLs

## 💬 Support

Need help or have suggestions?

- **[GitHub Issues](https://github.com/eMMeCodes/Symposium/issues)** - Report bugs or request features
- **[HELP.md](./HELP.md)** - Comprehensive troubleshooting guide
- **[Community Forum](https://community.bitfocus.io)** - Connect with other users
- **[Email Support](mailto:support@chilibytes.com)** - Direct technical assistance

## 📋 Version History

### v1.1.0 (Latest)
- ✨ **NEW**: Smart external link handling opens URLs in system browser
- ✨ **NEW**: Enhanced keyboard shortcuts for presentation mode
- ✨ **NEW**: Improved state management with "Remember Last Page" option
- 🔧 **IMPROVED**: More reliable OSC communication protocol
- 🔧 **IMPROVED**: Better error handling and user feedback
- 🐛 **FIXED**: Various stability improvements and bug fixes

### v1.0.3
- Added support for current/total page variables
- Improved feedback mechanisms  
- Fixed logo and icons dimensions

### v1.0.1
- Fixed graphics for media control presets

### v1.0.0
- Initial release with core functionality

## 🏗️ Development

### Building from Source
```bash
git clone https://github.com/eMMeCodes/companion-module-emmecodes-pdfosc.git
cd companion-module-emmecodes-pdfosc
npm install
npm run build
```

### Testing
```bash
npm test
npm run test:coverage
```

## 📄 License

This project is licensed under the [MIT License](./LICENSE).

## 🙏 Acknowledgements

- **Developed and Maintained by** [ChiliBytes](https://chilibytes.com)
- **Built for** [Bitfocus Companion](https://bitfocus.io/companion)
- **Powered by** [PDF.js](https://mozilla.github.io/pdf.js/) and [Electron](https://electronjs.org)
- **Special thanks** to the Bitfocus community for continuous feedback and support

---

<div align="center">
<b>🚀 Ready to enhance your presentation workflow? Get started with PDFOSC today!</b>
</div> 