# 🎵 32,768 Rhythm Pattern Dataset & Analytics

A complete interactive rhythm pattern library with pattern matching, usage analytics, and musical notation.

## 🎹 Features

- **32,768 Complete Pattern Library** - Every possible 16-step rhythm (2^15)
- **Interactive Grid** - Click to create rhythms
- **VexFlow Notation** - Professional music notation rendering
- **Audio Playback** - Hear your patterns with Tone.js
- **Pattern Matching** - Automatic classification system
- **Usage Analytics** - Track and rank pattern popularity
# 🎵 32,768 Rhythm Pattern Dataset & Analytics System

[![GitHub Pages](https://img.shields.io/badge/demo-live-success)](https://linlin1451.github.io/Rhythm-Pattern-Library/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![GitHub Stars](https://img.shields.io/github/stars/linlin1451/Rhythm-Pattern-Library?style=social)](https://github.com/linlin1451/Rhythm-Pattern-Library)

> A comprehensive interactive rhythm pattern library featuring all 32,768 possible 16-step rhythm combinations with pattern matching, usage analytics, musical notation rendering, and collaborative annotation system.

## 🔗 Live Demo

**[Try it here →](https://linlin1451.github.io/Rhythm-Pattern-Library/)**

---

## 📋 Table of Contents

- [Features](#-features)
- [How It Works](#-how-it-works)
- [Getting Started](#-getting-started)
- [Technologies](#-technologies)
- [Use Cases](#-use-cases)
- [Screenshots](#-screenshots)
- [Project Structure](#-project-structure)
- [Research Applications](#-research-applications)
- [Future Enhancements](#-future-enhancements)
- [Contributing](#-contributing)
- [License](#-license)
- [Author](#-author)
- [Acknowledgments](#-acknowledgments)

---

## ✨ Features

### 🎹 **Complete Pattern Library**
- **32,768 unique rhythm patterns** (2^15 combinations)
- Mathematical enumeration of all possible 16-step rhythms in 4/4 time
- Each pattern assigned a permanent, unique Pattern ID (0-32767)
- Binary representation system for efficient storage and retrieval

### 🎨 **Interactive Pattern Generator**
- Visual 16-step grid interface
- Click-to-create rhythm patterns
- First step always begins with a hit (no empty patterns)
- Real-time visual feedback

### 🎼 **Professional Music Notation**
- VexFlow integration for standard music notation
- Automatic note duration calculation (quarter, eighth, sixteenth notes)
- Percussion clef with 4/4 time signature
- Dynamic rendering based on pattern input

### 🔊 **Audio Playback**
- Tone.js synthesizer for realistic drum sounds
- Real-time pattern playback with visual step highlighting
- Play/stop controls
- Accurate 16th-note timing

### 🔍 **Pattern Matching & Classification**
- Automatic binary pattern conversion
- Instant pattern ID lookup from 32,768-pattern database
- Hamming distance similarity matching
- Find rhythmically related patterns

### 📊 **Usage Analytics Dashboard**
- Track pattern upload frequency
- Rank patterns by popularity (most used → least used)
- Secondary ranking by recency (most recent → oldest)
- Visual statistics: total patterns, unique uploads, coverage percentage
- Gold/Silver/Bronze badges for top 3 patterns

### 📝 **Collaborative Annotation System**
- Add notes to document musical context
- Record which songs use specific patterns
- Genre tagging and performance tips
- Timestamp tracking for all annotations
- Note management (add/delete)

### 💾 **Persistent Data Storage**
- LocalStorage-based data persistence
- No backend required - runs 100% in browser
- Dataset survives page refreshes
- Export capabilities for data backup

---

## 🧮 How It Works

### Pattern Space Mathematics

The system generates all possible rhythm patterns in a 16-step grid:

```
Total Patterns = 2^15 = 32,768

Why 2^15?
- 16 steps total in 4/4 time (sixteenth notes)
- First step is always a hit (X)
- Remaining 15 steps can be hit (X) or sustain (-)
- Binary representation: 1 = hit, 0 = sustain
```

### Pattern ID System

Each pattern has a unique ID based on its binary representation:

```javascript
Pattern Structure: [X][-][-][-][-][-][-][-][-][-][-][-][-][-][-][-]
                    ↑  ←────────── 15 variable positions ──────────→
                    Always 1

Example:
Pattern ID 0:     X---X---X---X---  (quarter notes)
Pattern ID 21845: X-X-X-X-X-X-X-X-  (eighth notes)
Pattern ID 32767: XXXXXXXXXXXXXXXX  (sixteenth notes)
```

### Upload & Ranking Algorithm

When a user uploads a pattern:

1. **Convert** rhythm grid to binary string
2. **Match** against RHYTHM_PATTERN_LIBRARY (32,768 patterns)
3. **Retrieve** unique pattern_id
4. **Update** dataset:
   - If pattern exists: increment `upload_count`, update `last_uploaded_timestamp`
   - If new pattern: create entry with `upload_count = 1`
5. **Persist** to localStorage

**Ranking Logic:**
- Primary sort: Upload count (descending)
- Secondary sort: Last uploaded timestamp (descending)

---

## 🚀 Getting Started

### Prerequisites

- Modern web browser (Chrome, Firefox, Safari, Edge)
- No installation required!

### Quick Start

**Option 1: Use Online (Recommended)**

Simply visit: **[https://linlin1451.github.io/Rhythm-Pattern-Library/](https://linlin1451.github.io/Rhythm-Pattern-Library/)**

**Option 2: Run Locally**

```bash
# Clone the repository
git clone https://github.com/linlin1451/Rhythm-Pattern-Library.git

# Navigate to directory
cd Rhythm-Pattern-Library

# Open index.html in your browser
open index.html  # Mac
start index.html # Windows
```

### Basic Usage

1. **Create Pattern**: Click grid squares to toggle steps (first step always active)
2. **Play Pattern**: Click ▶️ Play to hear your rhythm
3. **Upload Pattern**: Click 📤 Upload to add to dataset
4. **Add Notes**: Document songs that use this rhythm pattern
5. **View Analytics**: Click 📋 View Dataset to see rankings

---

## 🛠️ Technologies

### Core Libraries

| Technology | Version | Purpose |
|------------|---------|---------|
| **VexFlow** | 4.2.2 | Music notation rendering |
| **Tone.js** | 14.8.49 | Audio synthesis and playback |
| **Vanilla JavaScript** | ES6+ | Core application logic |
| **LocalStorage API** | HTML5 | Data persistence |

### Architecture

```
Frontend Only Architecture
│
├── VexFlow Renderer
│   └── Dynamic notation generation
│
├── Tone.js Audio Engine
│   ├── MembraneSynth (drum sounds)
│   └── Transport (timing control)
│
├── Pattern Library (32,768 patterns)
│   ├── Binary → ID mapping
│   └── Hamming distance matching
│
└── LocalStorage Database
    ├── user_uploaded_rhythm_dataset
    └── Pattern metadata & annotations
```

---

## 💡 Use Cases

### 🎓 **Music Education**
- Learn rhythm pattern theory
- Study common rhythmic structures
- Practice pattern recognition
- Understand note duration relationships

### 🔬 **Research Applications**
- Rhythm pattern popularity studies
- Cross-cultural rhythm analysis
- Music theory research
- Pattern frequency distribution analysis

### 🎼 **Composition & Production**
- Discover new rhythm ideas
- Find variations of existing patterns
- Build rhythm pattern database
- Document rhythm usage in songs

### 📚 **Academic Projects**
- Data analytics demonstrations
- Algorithm visualization
- Music information retrieval
- Pattern matching research

---

## 📸 Screenshots

### Main Interface
```
┌─────────────────────────────────────────────────┐
│  🎵 Rhythm Pattern Dataset & Analytics         │
│  32,768 Rhythm Pattern Library                 │
├─────────────────────────────────────────────────┤
│                                                 │
│  🎹 Rhythm Generator                           │
│  ┌─┬─┬─┬─┬─┬─┬─┬─┬─┬─┬─┬─┬─┬─┬─┬─┐            │
│  │X│-│-│-│X│-│-│-│X│-│-│-│X│-│-│-│            │
│  └─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┘            │
│                                                 │
│  ▶️ Play  ⏹️ Stop  📤 Upload  🗑️ Clear         │
│                                                 │
│  Pattern ID: 0                                 │
│  Binary: 1000100010001000                      │
│                                                 │
│  🎼 [VexFlow Notation Display]                 │
│                                                 │
│  📝 Pattern Notes:                             │
│  "Classic four-on-the-floor kick drum"         │
│                                                 │
├─────────────────────────────────────────────────┤
│                                                 │
│  📊 Rhythm Pattern Dataset                     │
│                                                 │
│  Rank | ID    | Pattern    | Uploads | Notes   │
│  🥇   | 21845 | X-X-X-X... | 127    | 5 notes │
│  🥈   | 0     | X---X---.. | 89     | 3 notes │
│  🥉   | 32767 | XXXXXXX... | 56     | 2 notes │
│                                                 │
└─────────────────────────────────────────────────┘
```

---

## 📁 Project Structure

```
Rhythm-Pattern-Library/
│
├── index.html                 # Main application file
├── README.md                  # This file
├── LICENSE                    # MIT License
│
└── assets/                    # (optional - for screenshots)
    ├── demo.gif
    └── screenshot.png
```

### Key Components in index.html

```javascript
// Core Systems
├── RHYTHM_PATTERN_LIBRARY      // 32,768 pattern database
├── Pattern Conversion          // Binary ↔ Pattern ID
├── Dataset Management          // Upload, track, rank
├── VexFlow Renderer            // Music notation
├── Tone.js Player              // Audio playback
└── Notes System                // Annotations & context
```

---

## 🔬 Research Applications

This tool is particularly useful for:

### Academic Research
- **Music Theory**: Study rhythm pattern distributions
- **Ethnomusicology**: Compare rhythmic structures across cultures
- **Music Information Retrieval**: Pattern matching algorithms
- **Data Analytics**: Usage statistics and popularity trends

### Industry Applications
- **Music Production**: Pattern discovery and inspiration
- **Education Software**: Interactive rhythm learning
- **Music Technology**: Algorithmic composition tools
- **AI Training**: Generate datasets for rhythm prediction models

### Potential Research Questions
- Which rhythm patterns are most commonly used in popular music?
- How do rhythm patterns vary across musical genres?
- What is the relationship between pattern complexity and popularity?
- Can we predict which patterns will be used together?

---

## 🚧 Future Enhancements

### Planned Features
- [ ] Export dataset as JSON/CSV
- [ ] Import patterns from MIDI files
- [ ] Multi-bar pattern support (8, 16, 32 bars)
- [ ] Time signature variations (3/4, 5/4, 7/8)
- [ ] Pattern visualization (heat maps, dendrograms)
- [ ] Collaborative filtering recommendations
- [ ] Cloud sync across devices
- [ ] Pattern audio export (WAV/MP3)
- [ ] Genre classification system
- [ ] Social sharing features

### Technical Improvements
- [ ] Service Worker for offline support
- [ ] IndexedDB for larger datasets
- [ ] WebAssembly for performance
- [ ] Progressive Web App (PWA)
- [ ] Responsive mobile design
- [ ] Accessibility (ARIA labels, keyboard navigation)
- [ ] i18n (internationalization)

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

### Ways to Contribute
- 🐛 Report bugs
- 💡 Suggest new features
- 📝 Improve documentation
- 🎨 Enhance UI/UX
- 🧪 Add test patterns
- 🌍 Translate to other languages

### Development Setup

```bash
# Fork the repository
# Clone your fork
git clone https://github.com/YOUR_USERNAME/Rhythm-Pattern-Library.git

# Create a feature branch
git checkout -b feature/amazing-feature

# Make your changes
# Test thoroughly

# Commit your changes
git commit -m "Add amazing feature"

# Push to your fork
git push origin feature/amazing-feature

# Open a Pull Request
```

### Code Style
- Use clear, descriptive variable names
- Comment complex logic
- Follow existing code structure
- Test in multiple browsers

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

### MIT License Summary
```
✅ Commercial use
✅ Modification
✅ Distribution
✅ Private use
❌ Liability
❌ Warranty
```

---

## 👨‍💻 Author

**Chenwei Lin**

- 🎓 Data Analytics Engineering Graduate Student @ Northeastern University
- 🔬 Research Focus: Music Technology, AI/ML Hardware, Rhythm Pattern Analysis
- 📧 Email: lcw201777@gmail.com
- 🐙 GitHub: [@linlin1451](https://github.com/linlin1451)
- 💼 LinkedIn: [Connect with me](https://www.linkedin.com/in/chenwei-lin) _(update with your LinkedIn URL)_

### About the Project

This project was developed as part of music technology research exploring algorithmic pattern classification, usage analytics, and interactive visualization systems. It demonstrates expertise in:

- Algorithm design and optimization
- Data structures and pattern matching
- Interactive UI/UX development
- Audio processing and synthesis
- Music theory and notation
- Full-stack web development

---

## 🙏 Acknowledgments

### Libraries & Tools
- [VexFlow](https://www.vexflow.com/) - Music notation rendering engine
- [Tone.js](https://tonejs.github.io/) - Web Audio framework
- [GitHub Pages](https://pages.github.com/) - Free hosting platform

### Inspiration
- "The 65,536 Rhythm Patterns" - Mathematical rhythm enumeration concept
- Drum machine and rhythm sequencer interfaces
- Music theory pattern analysis research

### Special Thanks
- Northeastern University Data Analytics Engineering Program
- Open source community
- All contributors and users

---

## 📊 Project Stats

![Repository Size](https://img.shields.io/github/repo-size/linlin1451/Rhythm-Pattern-Library)
![Code Size](https://img.shields.io/github/languages/code-size/linlin1451/Rhythm-Pattern-Library)
![Last Commit](https://img.shields.io/github/last-commit/linlin1451/Rhythm-Pattern-Library)

---

## 📚 Additional Resources

### Related Projects
- [32,768 Rhythm Patterns Python Library](https://github.com/linlin1451/rhythm-patterns-python) _(create this!)_
- Pattern Analysis Notebooks
- Research Papers & Documentation

### Learn More
- [Music Theory: Rhythm](https://www.musictheory.net/lessons/12)
- [Web Audio API Documentation](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)
- [VexFlow Tutorial](https://github.com/0xfe/vexflow/wiki/Tutorial)

---

## 💬 Feedback & Support

### Get Help
- 📖 Check the [documentation](#-how-it-works)
- 🐛 [Report a bug](https://github.com/linlin1451/Rhythm-Pattern-Library/issues)
- 💡 [Request a feature](https://github.com/linlin1451/Rhythm-Pattern-Library/issues)
- 💬 Start a [discussion](https://github.com/linlin1451/Rhythm-Pattern-Library/discussions)

### Stay Updated
- ⭐ Star this repository to follow updates
- 👀 Watch for new releases
- 🔔 Enable notifications for issues you're interested in

---

## 🎯 Project Goals

1. **Educational**: Make rhythm theory accessible and interactive
2. **Research**: Provide tools for music analytics and pattern analysis
3. **Community**: Build a collaborative rhythm pattern knowledge base
4. **Innovation**: Push boundaries of web-based music technology

---

<div align="center">

**Made with ❤️ and JavaScript**

If you find this project useful, please consider:

⭐ **Starring the repository**  
🐛 **Reporting issues**  
🤝 **Contributing code**  
📢 **Sharing with others**

---

### [🚀 Try the Live Demo](https://linlin1451.github.io/Rhythm-Pattern-Library/)

---

© 2024 Chenwei Lin. All rights reserved.

</div>