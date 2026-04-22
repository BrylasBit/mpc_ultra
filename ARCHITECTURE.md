# Architecture & Code Structure

This document describes the internal architecture of MPC ULTRA v8 for developers who want to understand or contribute to the codebase.

---

## 📋 Overview

MPC ULTRA is a **standalone single-file HTML application** combining:
- HTML structure
- CSS styling (embedded)
- JavaScript logic (vanilla ES6+)
- No external dependencies

```
index.html (complete self-contained application)
├── HTML Structure
├── CSS Styling (1600+ lines)
└── JavaScript Logic (1000+ lines)
```

---

## 🏗️ High-Level Architecture

```
┌─────────────────────────────────────────┐
│        USER INTERFACE (DOM)             │
│  - Transport Controls                   │
│  - Pad Bank (16 pads × 4 banks)        │
│  - Sequencer Grid                       │
│  - Sample Manager                       │
│  - Synth Controls                       │
└────────┬────────────────────────────────┘
         │
    ┌────▼─────────────────────────────┐
    │   EVENT HANDLERS & STATE         │
    │  - Keyboard/Mouse Input          │
    │  - MIDI Input                    │
    │  - Beat Animation Loop           │
    └────┬────────────────────────────┘
         │
    ┌────▼──────────────────────────────────────┐
    │     AUDIO ENGINE (Web Audio API)          │
    │  - Sample Player Node                     │
    │  - Synth Oscillator (Moog-style)         │
    │  - Audio Context & Graph                 │
    └────┬──────────────────────────────────────┘
         │
    ┌────▼─────────────────────┐
    │  SPEAKERS/HEADPHONES     │
    │  (System Audio Output)    │
    └──────────────────────────┘
```

---

## 📁 File Structure

```
index.html
├─ HEAD
│  ├─ Meta Tags (viewport, description, OG tags)
│  ├─ Title
│  └─ Style (CSS embedded)
│
├─ BODY
│  ├─ .mpc (main container)
│  │  ├─ .topbar (logo, LCD, MIDI status)
│  │  │  ├─ .brand (MPC ULTRA v8 logo)
│  │  │  ├─ .lcd (display screen)
│  │  │  ├─ .dots (status indicators)
│  │  │  ├─ .midi-bar (MIDI status)
│  │  │  └─ .hbtn (header buttons)
│  │  │
│  │  └─ .body (main content grid)
│  │     ├─ .lc (left column)
│  │     │  ├─ Transport controls
│  │     │  ├─ BPM control
│  │     │  ├─ Sequencer grid
│  │     │  └─ Sample manager
│  │     │
│  │     └─ .rc (right column)
│  │        ├─ Pad bank
│  │        ├─ Kit selector
│  │        ├─ Synth keyboard
│  │        └─ Settings
│  │
│  └─ SCRIPT (JavaScript logic)
```

---

## 🎮 Main Components

### 1. **Transport Controls**
```javascript
// Play/Pause/Stop buttons
// BPM slider
// Metronome toggle
// Connected to sequencer state
```

### 2. **Pad Bank System**
```javascript
// 16 pads × 4 banks = 64 sound slots
// Each pad:
//   - Can play samples
//   - Supports MIDI trigger
//   - Shows visual feedback
//   - Maps to keyboard numbers 1-8
```

### 3. **Sequencer**
```javascript
// 16-step grid
// Multiple rows (Kick, Snare, HiHat, etc.)
// Click-to-toggle pattern programming
// Runs at specified BPM
// Synced with Web Audio context
```

### 4. **Audio Engine**
```javascript
// Web Audio API Context
// Sample playback nodes
// Synth oscillator (sine/square/triangle)
// Gain nodes for volume control
// Connected to system output
```

### 5. **MIDI System**
```javascript
// Web MIDI API integration
// Device detection
// Note On/Off handling
// CC (Control Change) mapping
// Status indicator feedback
```

### 6. **Synth Engine**
```javascript
// Oscillator (Moog-style)
// ADSR envelope (simplified)
// Keyboard input mapping
// Polyphonic playback
// Two keyboard octaves
```

---

## 🔄 Data Flow

```
┌─ Keyboard Press (Key 1-8)
│         ↓
│  [Handle Keydown Event]
│         ↓
│  [Retrieve Sample from Pad]
│         ↓
│  [Create Audio Buffer Source]
│         ↓
│  [Connect to Audio Context]
│         ↓
│  [Play Sound]
│         ↓
└─ Sound Output → Speakers
```

```
┌─ Sequencer Play (SPACE)
│         ↓
│  [Start Animation Loop @ BPM]
│         ↓
│  [Calculate Current Step]
│         ↓
│  [Check Which Pads Active]
│         ↓
│  [Trigger Active Pads]
│         ↓
│  [Update Visual Indicators]
│         ↓
└─ Loop Until Stop/Pause
```

---

## 🎛️ State Management

The application maintains several state objects:

```javascript
// Transport State
state.playing = false       // Is sequencer running?
state.currentStep = 0       // Current step (0-15)
state.bpm = 120             // Tempo (60-180)

// Sequencer State
state.patterns = {          // Grid data
  kick: [1,0,0,0,1,0,0,0,...],
  snare: [0,0,1,0,0,0,1,0,...],
  ...
}

// Pad Bank State
state.currentBank = 1       // Bank number (1-4)
state.pads = {}             // Pad data & samples

// Audio State
audioContext               // Web Audio API context
oscillator               // Synth oscillator node
```

---

## ⌨️ Event Handling

### Keyboard Events
```javascript
// Keyboard down
keydown → {
  if (key 1-8) → trigger pad
  if (key Q-U) → play synth upper octave
  if (key Z-M) → play synth lower octave
  if (key space) → play/pause sequencer
  if (key M) → toggle metronome
  if (key ESC) → panic (kill all voices)
}

// Keyboard up
keyup → {
  stop synth note
}
```

### Mouse Events
```javascript
// Pad clicks
pad.click → trigger sound

// Sequencer grid clicks
step.click → toggle pattern

// Slider/Knob changes
slider.change → update parameter
```

### MIDI Events
```javascript
// Note On
noteon → trigger pad or synth note

// Note Off
noteoff → release synth note

// CC (Control Change)
cc → map to parameter (volume, BPM, etc.)
```

---

## 🎵 Audio Processing

### Sample Playback
```javascript
// When pad triggered:
1. Get sample data (AudioBuffer)
2. Create BufferSource node
3. Set playback rate
4. Connect to gain node
5. Connect to destination (speakers)
6. Start playback
7. Clean up node when done
```

### Synth Engine
```javascript
// When synth key pressed:
1. Create oscillator node
2. Set frequency (from note)
3. Set wave type (sine, square, etc.)
4. Create envelope (ADSR)
5. Connect through gain
6. Connect to destination
7. Start oscillator
// When key released:
8. Stop oscillator
9. Clean up node
```

---

## 🔧 Key Functions (Examples)

```javascript
// Trigger a pad sound
triggerPad(padNumber) {
  const sample = getSampleForPad(padNumber);
  playSound(sample);
  updatePadVisuals(padNumber);
}

// Play sequencer step
playStep(stepNumber) {
  const activePads = getActivePadsForStep(stepNumber);
  activePads.forEach(pad => triggerPad(pad));
  updateSequencerVisuals(stepNumber);
}

// Handle BPM change
setBpm(newBpm) {
  state.bpm = newBpm;
  updateSequencerTiming();
}

// Load sample file
loadSample(file, padNumber) {
  audioContext.decodeAudioData(file, (decoded) => {
    storeSample(padNumber, decoded);
    updatePadVisuals(padNumber);
  });
}
```

---

## 🎨 Visual Feedback

```javascript
// Pad activation
pad.classList.add('active')
setTimeout(() => pad.classList.remove('active'), 150ms)

// Step highlighting
steps[currentStep].classList.add('current')
steps[previousStep].classList.remove('current')

// Status indicator animations
dot.classList.add('on-g')  // Green for active
```

---

## 🔌 Web APIs Used

### Web Audio API
- `AudioContext` - main audio engine
- `AudioBuffer` - sample data storage
- `BufferSource` - sample playback
- `OscillatorNode` - synth engine
- `GainNode` - volume control
- `AnalyserNode` - potential for future visualization

### Web MIDI API
- `navigator.requestMIDIAccess()` - request MIDI
- `MIDIInput.onmidimessage` - handle MIDI events
- Status/note parsing

### Web APIs
- `File API` - sample file handling
- `Fetch API` - potential for sample loading from URLs
- `LocalStorage` - potential for settings persistence

---

## 🚀 Performance Considerations

### Current Optimizations
- Single AnimationFrame loop instead of setInterval
- Event delegation for DOM efficiency
- Reuse audio nodes where possible
- Efficient CSS animations with GPU acceleration

### Potential Improvements
- Use AudioWorklet for custom processing
- Implement ring buffers for sample playback
- Use Web Workers for heavy computations
- Optimize DOM updates with virtual DOM approach

---

## 🛠️ Development Tips

### Debugging
```python
// Open browser DevTools
F12 or Right-click → Inspect

// Check Audio Context
console.log(audioContext.state)  // "running", "suspended", etc.

// Monitor MIDI
console.log(midiInputs)          // Connected devices

// Check Web Audio Graph
console.log(audioContext)        // Audio graph visualization
```

### Common Modifications

**Change Accent Color:**
```css
:root {
  --acc: #ff6a00;      /* Change to desired color */
}
```

**Add New Synth Wave Type:**
```javascript
// In synth setup
oscillator.type = 'sawtooth';  // Add new option
```

**Modify BPM Range:**
```javascript
// Find BPM slider limits
slider.min = 60;   // Minimum BPM
slider.max = 200;  // Maximum BPM
```

---

## 📚 Resources for Contributors

- [Web Audio API MDN](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)
- [Web MIDI API MDN](https://developer.mozilla.org/en-US/docs/Web/API/Web_MIDI_API)
- [JavaScript Audio Synthesis](https://www.html5rocks.com/en/tutorials/webaudio/intro/)
- [MPC Production Workflow](https://en.wikipedia.org/wiki/Akai_MPC)

---

## 📝 Contributing Code

When modifying the code:

1. **Keep it organized** - group related functions
2. **Add comments** - especially for complex logic
3. **Test thoroughly** - multiple browsers/devices
4. **Update docs** - explain significant changes
5. **Follow conventions** - match existing code style
6. **Performance first** - test impact on responsiveness

---

## 🐛 Known Limitations

- Single HTML file (not modular architecture)
- No persistent storage (state lost on refresh)
- Limited effect chain
- Basic envelope (no complex ADSR)
- Polyphony limited by browser resources
- Mobile touch support limited

---

## 🔮 Future Architecture Improvements

- Modular ES6 modules (eventually)
- Service Worker for offline support
- IndexedDB for sample storage
- Audio Worklet for advanced DSP
- Web Components for UI
- Testing framework integration

---

**Questions or suggestions?** Open an issue or discussion on GitHub!

