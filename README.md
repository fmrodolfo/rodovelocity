# RODOVELOCITY — TopVelocity Fusion Training App

A progressive web app for baseball pitchers to calculate strength training weights, track workouts, and sync across devices using the TopVelocity Fusion System methodology.

## Features

- 📊 **5 Complete Training Plans**: Level 1, 2, 3, Pre-Season, In-Season
- 💪 **Weight Calculation Engine**: Auto-calculates percentages from reference lifts (Power Clean, Back Squat, Bench Press)
- 🧠 **Intelligent Coach System**: Adjusts weights based on RPE (Rate of Perceived Exertion) feedback
- ☁️ **Cloud Sync**: 4-digit code system for multi-device synchronization (Firebase)
- 📱 **Offline-First**: Works completely offline; cloud is optional
- 🏋️ **kg/lb Conversion**: Real-time unit conversion with proper rounding
- 📈 **Progress Tracking**: Charts for maxes evolution, volume, and feeling/effort
- 🎯 **Movilidad + Tiro + Gimnasio Structure**: Dynamic warmup → throwing drills → strength training

## Quick Start

### Option 1: Use the App Now

1. Go to your Netlify domain (once deployed)
2. Create or select a profile
3. Enter your 1RM (one-rep-max) reference lifts:
   - Power Clean (or Snatch)
   - Back Squat
   - Bench Press
4. Select a training plan (Level 1-3, Pre-Season, or In-Season)
5. Start working out!

### Option 2: Deploy to Netlify (Recommended)

1. Fork or clone this repo to your GitHub account
2. Go to [netlify.com](https://netlify.com) and sign up (free)
3. Click "New site from Git"
4. Select this repository
5. **Build settings**: Leave blank (it's a static site)
6. Deploy!

Every time you push changes to GitHub, Netlify will auto-deploy in seconds.

## Local Development

```bash
# Clone the repo
git clone https://github.com/fmrodolfo/rodovelocity.git
cd rodovelocity

# Open in browser
# On Mac:
open index.html
# On Linux:
xdg-open index.html
# On Windows:
start index.html

# Or run a simple server:
python3 -m http.server 8000
# Then visit http://localhost:8000
```

## Cloud Sync Setup (Optional)

To enable multi-device sync with Firebase:

1. Create a Firebase project at [firebase.google.com](https://firebase.google.com)
2. Enable **Anonymous Authentication**:
   - Go to Authentication → Sign-in method
   - Enable "Anonymous"
3. Copy your Firebase config from Project Settings
4. In the app: Settings → "API de IA" section → paste your config
5. The app will generate a 4-digit code
6. Share the code with anyone who should sync (same family, team, etc.)

## File Structure

```
rodovelocity/
├── index.html           # Main app (all-in-one file)
├── manifest.json        # PWA metadata
├── service-worker.js    # Offline caching
├── .gitignore          # Git ignore rules
└── README.md           # This file
```

## Features Breakdown

### Training Plans

| Plan | Duration | Focus | Volume |
|------|----------|-------|--------|
| Level 1 | 8 weeks | Foundation | Moderate |
| Level 2 | 8 weeks | Progression | Higher |
| Level 3 | 8 weeks | Peak Strength | High |
| Pre-Season | 4 weeks | Sport-Specific | High |
| In-Season | 3 weeks | Maintenance | Low |

### Coach System

After each main lift, the app asks: "¿Cómo te sentiste?" (How did you feel?)

- 🪶 **Muy fácil** (Very easy) → +3% next time
- 💪 **Bien** (Good) → No change
- 🥵 **Duro** (Hard) → −2% next time
- 🧨 **Al fallo** (To failure) → −5% next time
- ⚠️ **Molestia/dolor** (Pain/discomfort) → −10% + shoulder alert

The coach learns from your feedback and auto-adjusts weights for that same exercise on its next occurrence (not the next exercise in the day).

## Deployment

### Netlify (Recommended)

1. Push to GitHub
2. Netlify auto-deploys
3. Share your live link: `https://your-domain.netlify.app`

### Other Hosts

This is a static site—works on any host:
- Vercel
- GitHub Pages
- AWS S3
- Any web server

## PWA Features

- Install as app on home screen (Android + iOS)
- Works offline with cached data
- Auto-updates when you push new code
- Full-screen experience (no browser chrome)

## Support

For bugs or questions:
- Check localStorage in DevTools for data
- Clear site data and restart if issues
- Make sure Firebase rules are set up (if using cloud)

## License

Built with ⚡ for Rodo's pitching velocity journey.
