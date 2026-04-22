# 🎹 MPC ULTRA v8

> **Professional Browser-Based MPC Music Production Controller**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Built with Web Audio API](https://img.shields.io/badge/Built%20with-Web%20Audio%20API-brightgreen)](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow?logo=javascript)
![Chrome Compatible](https://img.shields.io/badge/Chrome%2FEdge-Compatible-4285f4?logo=googlechrome)

---

## 🎯 Overview

**MPC ULTRA v8** is a fully-featured, browser-based music production controller inspired by the legendary MPC series. Build beats, program drum sequences, and play synth sounds directly in your browser—no installation required.

### Key Features

✨ **Pad Bank System**
- 16 individual pads for drum samples and sounds
- 4 banks for 64 total sound slots
- Real-time pad triggering with visual feedback

🥁 **Beat Sequencer**
- 16-step pattern sequencer
- Multiple drum channels (Kick, Snare, Hi-Hat + more)
- BPM control (adjustable tempo)
- Play/Pause/Stop transport controls

🎛️ **Sound Design**
- Polyphonic synth engine with Moog-style oscillator
- Load custom WAV samples via drag-and-drop
- Sample assignment to individual pads
- Sample Manager for organizing sounds

⌨️ **Hardware Control**
- Full MIDI support (Launchkey Mini MK2 compatible)
- Keyboard shortcuts (keys 1-8 for pads, Z-M for piano)
- Octave switching (Q-U for upper, Z-M for lower)
- Space bar for play/pause
- ESC panic button to stop all voices
- Metronome with visual beat indicator

🎵 **Audio Features**
- Web Audio API integration
- Low-latency sound synthesis
- Multiple drum kits (808, 909, TRAP, etc.)
- Real-time BPM synchronization

---

## 🚀 Quick Start

### 1. Open the Application
Simply open `index.html` in a modern browser (Chrome, Edge, Firefox, Safari)

```bash
# Clone or download this repository
git clone https://github.com/BrylasBit/mpc_ultra.git
cd mpc_ultra

# Open in your default browser
open index.html  # macOS
# or
xdg-open index.html  # Linux
# or double-click index.html in Windows
```

### 2. Load Samples (Optional but Recommended)
To get the best experience with drum sounds:

1. Prepare WAV files organized by category:
   - **KICKS**: `WKK1.wav`, `WKK2.wav`, `WKK3.wav`, `WKK4.wav`
   - **SNARES**: `WSP1.wav`, `WSP2.wav`, `WSP3.wav`, `WSP5.wav`
   - **HI-HATS**: `WHT1.wav`, `WHT2.wav`, `WHT3.wav`, `WHT4.wav`, `WHT5.wav`

2. **Method A - Drag & Drop (Fastest)**
   - Drag WAV files onto the "DRAG WAV FILES HERE" zone
   
3. **Method B - Direct Pad Assignment**
   - Drag individual WAV files directly onto pads

4. **Method C - Sample Manager**
   - Use the Sample Manager interface to browse and assign samples

### 3. Test It Out
- Press **1** → Play assigned kick sample
- Press **Q** → Play synth (Moog oscillator)
- Press **SPACE** → Play sequencer
- See [Keyboard Controls](#-keyboard-controls) below

---

## ⌨️ Keyboard Controls

| Key(s) | Function |
|--------|----------|
| **1-8** | Trigger pads 1-8 |
| **Q-U** | Piano upper octave (synth) |
| **Z-M** | Piano lower octave (synth) |
| **SPACE** | Play/Pause sequencer |
| **M** | Toggle metronome ON/OFF |
| **ESC** | PANIC - kill all voices immediately |

---

## 🎮 MIDI Support

Connect a MIDI controller (e.g., **Launchkey Mini MK2**) for enhanced control:

1. Click the **MIDI** button (top right of interface)
2. Select your controller from the dropdown
3. **Pads 1-8** → Trigger drum samples
4. **Piano keys** → Play synth notes
5. **Faders/Knobs** → Control parameters in real-time

### Supported Controllers
- Native Web MIDI support (works with most USB MIDI controllers)
- Akai Launchkey Mini MK2 (tested)
- Any standard MIDI device with proper drivers

---

## 📚 Features in Depth

### Beat Sequencer
- Program 16-step patterns
- Each row represents a different drum element (Kick, Snare, etc.)
- Click steps to toggle sound on/off
- Visual grid shows active steps
- Adjustable BPM from ~60 to ~180 BPM

### Sample Loading
- **Drag & Drop**: Simply drag WAV files onto the application
- **Sample Manager**: Browse and organize thousands of sounds
- **Per-Pad Assignment**: Assign any sample to any pad
- **Format**: WAV files recommended (MP3 support depends on browser)

### Synth Engine
- **Moog-style oscillator** for bass and melody
- **Polyphonic** - play multiple notes simultaneously
- **2 Octaves** - full range for musical expression
- **Real-time playback** with low latency

### Kit Selection
Choose from multiple drum kits:
- **808**: Classic TR-808 sounds
- **909**: Classic TR-909 sounds
- **TRAP**: Modern trap drums
- **HIP-HOP**: Classic hip-hop breaks
- **Custom**: Load your own samples

---

## 🔧 Troubleshooting

### Problems & Solutions

| Problem | Solution |
|---------|----------|
| Sounds loop infinitely | Press **ESC** (panic button) or refresh page |
| Samples don't play | Ensure WAV files are loaded; use Sample Manager to assign to pad |
| Keyboard shortcuts don't work | Click outside text input fields to regain focus |
| MIDI not detected | Check hardware connection; restart browser; refresh page |
| Audio is silent | Check browser volume; verify Web Audio is enabled |
| Samples load slowly | Use smaller WAV files (<5MB each) |

---

## 💻 System Requirements

- **Browser**: Chrome, Edge, Firefox, or Safari (latest versions)
- **OS**: Windows, macOS, Linux
- **Internet**: Not required (runs locally in browser)
- **Audio**: System speakers or headphones
- **Storage**: None required (samples kept in browser memory)

---

## 🛠️ Build & Development

This is a **standalone HTML file** with embedded CSS and JavaScript. No build process needed!

### To modify:
1. Open `index.html` in your code editor
2. Edit the CSS in the `<style>` section
3. Edit JavaScript in the `<script>` section
4. Save and refresh your browser

### Dependencies
- **Web Audio API** (built-in browser API)
- **Web MIDI API** (built-in browser API)
- **Google Fonts** (Orbitron, Share Tech Mono, Inter)

---

## 📋 File Structure

```
mpc_ultra/
├── index.html              # Main application (HTML + CSS + JS)
├── README.md               # This file
├── QUICK-START             # Polish quick-start guide
├── LICENSE                 # MIT License
└── .gitignore              # Git configuration
```

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

You are free to:
- ✅ Use commercially
- ✅ Modify the code
- ✅ Distribute
- ✅ Use privately

---

## 👨‍💻 Author

**BrylasBit** - Music Production Tools & Web Audio Experiments

### Contributing
Contributions are welcome! Feel free to:
- Report bugs
- Suggest features
- Submit pull requests
- Share improvements

---

## 🎵 Inspiration & Credits

Built with passion for the MPC legacy and modern web technology.
Inspired by: Akai MPC, Native Instruments Maschine, and the spirit of hip-hop production.

---

## 📞 Support & Feedback

Have questions or feedback? Create an issue on GitHub or check the QUICK-START file for detailed usage instructions.

---

## 🔮 Roadmap

Future features under consideration:
- 🎚️ Advanced mixer with volume/pan controls
- 🎹 Drum kit editor/designer
- 💾 Save/load projects
- 🎬 Recording & playback
- 🌐 Cloud sync
- 📱 Mobile app version

---

**Enjoy making beats! 🎶**
