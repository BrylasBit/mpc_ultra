# 🎹 BRYLA$ ULTRA v8.3 - Web-Based Creative Engine

## 🚀 Overview
A high-performance, mobile-responsive Digital Audio Workstation (DAW) built with vanilla JavaScript and the Web Audio API. This project bridges the gap between classic music hardware workflow and modern web technology, delivering a professional-grade sampler and sequencer directly in your browser.

## 🛠 Technical Highlights
- **Real-time DSP:** Custom implementation of ADSR envelopes, filters (Low-pass/High-pass), and spatial effects (Reverb/Delay).
- **Advanced Buffer Management:** Efficient loading and triggering of high-fidelity audio samples with near-zero latency.
- **Dynamic Visualization:** Real-time waveform rendering using HTML5 Canvas API.
- **Mobile-First Design:** Fully responsive UI with custom touch-event handling for musical performance.

## 🤖 The AI & Industrial Connection
Inspired by 10 years of experience in high-stakes industrial environments (Pharmaceutical Manufacturing / Werum PAS-X), this project applies the principles of **Data Integrity** and **System Precision** to audio production. Every sample is handled with the same rigor as a GMP-regulated manufacturing process.

*Planned Update:* Integration of a Neural Network-based "Groove Suggestion" engine using Magenta.js.

## 💻 Tech Stack
- **Languages:** JavaScript (ES6+), HTML5, CSS3
- **APIs:** Web Audio API, Canvas API, Web MIDI API
- **Deployment:** Netlify
- **License:** MIT

> **Professional Browser-Based Audio Production Controller**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Built with Web Audio API](https://img.shields.io/badge/Built%20with-Web%20Audio%20API-brightgreen)](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow?logo=javascript)
![Chrome Compatible](https://img.shields.io/badge/Chrome%2FEdge-Compatible-4285f4?logo=googlechrome)

---

## 🎯 What is BRYLA$ ULTRA?

**BRYLA$ ULTRA v8** is a fully-featured, browser-based music production controller. Build beats, program drum sequences, and play synth sounds directly in your browser—no plugins, no installation, no subscriptions. Pure audio creation.

### Key Features

✨ **Pad Bank System**
- 16 individual pads for drum samples and sounds
- 4 banks for 64 total sound slots
- Real-time pad triggering with visual feedback
- Customizable pad colors and labeling

🥁 **Beat Sequencer**
- 16-step pattern sequencer
- Multiple drum channels (Kick, Snare, Hi-Hat + more)
- BPM control (adjustable tempo: 60-180 BPM)
- Play/Pause/Stop transport controls
- Visual step indicator

🎛️ **Sound Design**
- Polyphonic synth engine with Moog-style oscillator
- Load custom WAV samples via drag-and-drop
- Sample assignment to individual pads
- Sample Manager for organizing thousands of sounds
- Real-time sample preview

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
- Multiple drum kits (808, 909, TRAP, HIP-HOP, Custom)
- Real-time BPM synchronization
- Professional-grade audio processing

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
- Akai Launchkey Mini MK2 (tested & optimized)
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
- **ADSR controls** for sound shaping

### Kit Selection
Choose from multiple drum kits:
- **808**: Classic TR-808 sounds
- **909**: Classic TR-909 sounds
- **TRAP**: Modern trap drums
- **HIP-HOP**: Classic hip-hop breaks
- **CUSTOM**: Load your own samples

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
| Touch controls unresponsive | Check browser touch event support; tap screen to activate |

---

## 💻 System Requirements

- **Browser**: Chrome, Edge, Firefox, or Safari (latest versions)
- **OS**: Windows, macOS, Linux, iOS, Android
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
├── QUICK-START.md          # Quick start guide
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

A portfolio project demonstrating:
- Advanced Web Audio API implementation
- Real-time DSP (Digital Signal Processing)
- Complex state management in vanilla JavaScript
- Mobile-first responsive design
- Professional-grade audio software engineering

### Contributing
Contributions are welcome! Feel free to:
- Report bugs
- Suggest features
- Submit pull requests
- Share improvements

---

## 🎵 Inspiration & Credits

**BRYLA$ ULTRA** is built with passion for music production technology and modern web capabilities. Inspired by legendary music hardware and the democratization of music creation tools.

**Influences:**
- Akai MPC series (legendary samplers & sequencers)
- Native Instruments Maschine (modern production workflow)
- The spirit of hip-hop production and beat-making culture

---

## 📞 Support & Feedback

Have questions or feedback? 
- Create an issue on [GitHub](https://github.com/BrylasBit/mpc_ultra)
- Check the QUICK-START.md file for detailed usage instructions
- Review code comments for implementation details

---

## 🔮 Roadmap & Future Features

Under active development:

**v8.4 (Coming Soon)**
- 🎚️ Advanced mixer with volume/pan/EQ controls
- 💾 Save/load projects (local storage)
- 🎬 Recording & playback functionality

**Future Releases**
- 🎹 Drum kit editor/designer
- 🤖 Neural network-based "Groove Suggestion" engine (Magenta.js)
- 🌐 Cloud sync & project sharing
- 📱 Dedicated mobile app version
- 🎵 VST/AU plugin version for DAWs

---

## 📊 Project Stats

| Metric | Value |
|--------|-------|
| **Language** | JavaScript (ES6+) |
| **Lines of Code** | ~3000+ |
| **File Size** | ~120 KB |
| **Load Time** | <500ms |
| **Target FPS** | 60 |
| **MIDI Support** | ✅ Full |
| **Mobile Support** | ✅ Full |
| **Offline Capable** | ✅ Yes |

---

**Make beats like a professional. Code like an engineer. Create with BRYLA$ ULTRA. 🎶**

*Last Updated: April 2026*
