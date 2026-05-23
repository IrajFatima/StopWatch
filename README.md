# ⏱️ StopWatch

> A high-precision stopwatch web application built with **React 19 + Vite**. Track time with millisecond accuracy using a clean, modern dark-themed interface.

🔗 **Live Demo:** https://irajfatima.github.io/StopWatch/

---

## ✨ Features

| Feature | Details |
|---------|---------|
| ⏪ **Start** | Begin timing from the current elapsed time |
| ⏸️ **Stop** | Pause the timer at any moment |
| 🔄 **Reset** | Clear the timer back to `00:00:00:00` |
| ⏱️ **Precision** | 10ms interval updates for accurate timing |
| 🎨 **Dark Theme** | Modern gradient background with glassmorphism UI |
| 📱 **Responsive** | Fully mobile-friendly with stacked controls on small screens |
| 🚀 **Fast** | Built with Vite for instant HMR and optimized builds |

---

## 🎯 Time Format

Display shows: **HH:MM:SS:MS**
- **HH** - Hours (00-23)
- **MM** - Minutes (00-59)
- **SS** - Seconds (00-59)
- **MS** - Centiseconds (00-99) - *updates every 10 milliseconds*

Example: `00:01:30:45` = 1 minute, 30 seconds, and 45 centiseconds

---

## 🏗️ Project Structure

```
StopWatch/
├── index.html                 # Entry point with custom fonts
├── package.json              # Dependencies & npm scripts
├── vite.config.js            # Vite configuration
├── eslint.config.js          # ESLint rules
├── src/
│   ├── main.jsx              # React app bootstrap
│   ├── App.jsx               # Root component (title + StopWatch)
│   ├── StopWatch.jsx         # Main stopwatch logic & UI
│   └── index.css             # Styling (dark theme, animations)
├── package-lock.json         # Locked dependencies
└── .gitignore               # Git ignore rules
```

---

## 🛠️ Tech Stack

| Layer | Technology | Version |
|-------|-----------|---------|
| **UI Framework** | React | 19.2.0 |
| **Build Tool** | Vite | 7.2.4 |
| **Styling** | Vanilla CSS | - |
| **Fonts** | JetBrains Mono, Inter | - |
| **Deployment** | GitHub Pages | - |
| **Linting** | ESLint | 9.39.1 |

---

## 🚀 Quick Start

### Prerequisites

- [Node.js](https://nodejs.org/) **v18 or higher**
- npm (comes with Node.js)

### Installation & Development

```bash
# 1. Clone the repository
git clone https://github.com/IrajFatima/StopWatch.git
cd StopWatch

# 2. Install dependencies
npm install

# 3. Start development server
npm run dev
```

Then open your browser to **http://localhost:5173**

---

## 📦 Available Scripts

```bash
npm run dev       # Start Vite dev server with HMR
npm run build     # Create optimized production build (→ dist/)
npm run preview   # Preview the production build locally
npm run lint      # Run ESLint on all files
npm run deploy    # Build & deploy to GitHub Pages
```

---

## 🔧 Build for Production

```bash
npm run build       # Generates optimized files in /dist
npm run preview     # View production build locally
npm run deploy      # Deploy to GitHub Pages
```

---

## 💡 How It Works

### State Management (React Hooks)

```javascript
const [isRunning, setIsRunning] = useState(false);      // Timer state
const [elapsedTime, setElapsedTime] = useState(0);      // Time in ms
const intervalIdRef = useRef(null);                      // Interval reference
const startTimeRef = useRef(0);                          // Start timestamp
```

### Core Functions

**`start()`** - Begin or resume timing
- Calculates start time minus elapsed time for seamless resume

**`stop()`** - Pause the timer
- Preserves elapsed time for resume functionality

**`reset()`** - Clear timer
- Resets both elapsed time and running state

**`formatTime()`** - Convert milliseconds to HH:MM:SS:MS format
- Calculates hours, minutes, seconds, and centiseconds
- Pads all values to 2 digits for consistent display

### Update Interval

- Updates every **10 milliseconds** via `setInterval()`
- Uses `Date.now()` for accurate time tracking
- Automatically clears interval when stopping timer

---

## 🎨 Design Details

### Color Scheme (Dark Theme)
- **Background Gradient:** `#0f0f10` to `#1a1a1c` (very dark gray/black)
- **Card Gradient:** `#1c1c1e` to `#111113` (slightly lighter)
- **Text Color:** `#f5f5f7` (off-white)
- **Button Base:** `#2c2c2e` (dark gray)
- **Button Hover:** `#3a3a3c` (lighter on interaction)

### Typography
- **Font Family:** JetBrains Mono (monospace) + Inter (fallback)
- **Display Size:** Responsive `clamp(2.2rem, 6vw, 4.6rem)`
- **Button Size:** Responsive `clamp(1rem, 2.5vw, 2rem)`

### Responsive Breakpoint
- **Mobile (≤480px):** Buttons stack vertically, full width
- **Desktop (>480px):** Buttons displayed in a row

---

## 🔌 Browser Support

Works in all modern browsers that support:
- ES6+ JavaScript (modules)
- CSS Grid & Flexbox
- React 19 & Vite
- CSS custom properties

---

## 📄 License

This project is open source and available for educational purposes.

---

**⏰ Start timing now!** ✨
