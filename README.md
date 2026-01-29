# Vision Training Games

A browser-based visual training tool designed to improve various aspects of visual processing, including figure-ground discrimination, smooth pursuits, peripheral awareness, and gaze stability. These exercises are commonly used in vision therapy programs and may aid recovery from conditions like post-concussion syndrome.

The application generates procedural visual "noise" using the HTML5 Canvas API, creating challenging environments where users must isolate and respond to specific targets.

## Game Modes

### 1. Scattered Alphabet (Figure-Ground Perception)

Letters or numbers are scattered across the screen, camouflaged against a chaotic background of random shapes, lines, or static. The user must find and click each character in sequential order (A→Z or 1→26).

**Vision Therapy Benefits:**
- **Figure-Ground Perception:** Trains the brain to filter out irrelevant visual noise and focus on specific targets.
- **Saccades:** Requires rapid, accurate eye movements to scan the screen efficiently.
- **Sequential Processing:** Builds the cognitive skill of ordering visual information.

**Options:**
- Toggle between letters (a-z) and numbers (1-26)
- Enable "Wandering Letters" to make targets drift and bounce around the screen
- Randomize target colors for increased difficulty

### 2. Bouncing Ball (Pursuits & Attention)

A white ball moves continuously across the screen, bouncing off edges and UI elements. The user must visually track the ball but only click when it flashes red.

**Vision Therapy Benefits:**
- **Smooth Pursuits:** Trains the eyes to follow a moving target without jerky movements.
- **Visual Discrimination:** Requires identifying a change in color while the object is in motion.
- **Impulse Control (Go/No-Go):** Trains the user to inhibit responses until a specific visual condition is met.

**Options:**
- Adjustable ball speed
- Adjustable ball size

### 3. Key Ball (Dynamic Visual Acuity)

A ball containing a letter moves across the screen. The user must type the corresponding letter on their keyboard before it changes.

**Vision Therapy Benefits:**
- **Dynamic Visual Acuity:** Trains the ability to resolve fine detail while an object is in motion.
- **Visual-Motor Integration:** Connects visual processing directly to motor output (typing) under time pressure.
- **Accommodation:** Helps maintain focus on a moving target.

**Options:**
- Adjustable ball speed
- Adjustable ball size

### 4. Peripheral Awareness (Visual Field Training)

A fixation cross appears at the center of the screen. Letters flash briefly in the peripheral areas (left or right sides), and the user must identify them by typing the corresponding key without moving their eyes from the center cross.

**Vision Therapy Benefits:**
- **Peripheral Expansion:** Encourages widening the "attentional spotlight" beyond central vision.
- **Central-Peripheral Integration:** Trains the brain to process peripheral information while maintaining central fixation.
- **Visual Reaction Speed:** Ephemeral targets require rapid processing of peripheral stimuli.

### 5. OKN (Optokinetic Stimulation)

High-contrast vertical stripes or a checkerboard pattern scrolls continuously across the screen. Users can track a red target box or identify letters that appear within it.

**Vision Therapy Benefits:**
- **Optokinetic Reflex:** Stimulates involuntary eye movements triggered by large moving fields, often used to treat motion sensitivity or balance issues.
- **Anti-Suppression:** The high-contrast moving background provides strong binocular stimulation.
- **Gaze Stability:** Tracking the red target against the moving background trains fixation stability despite visual distractions.

**Options:**
- Adjustable scroll speed
- Adjustable stripe width
- Scroll direction (left-to-right or right-to-left)
- Toggle checkerboard pattern
- Target tracking mode (follow the red box)
- Letter stream mode (type letters as they appear in the target)

## Shared Features

### Progress Tracking
- **Stopwatch:** Integrated timer measures completion time for each session.
- **Personal History:** Completion times are saved to Firebase Firestore and persist across sessions.
- **Local Caching:** Recent times are cached locally for immediate feedback.

### Background Customization
- **Chaos Speed:** Controls how frequently the background distractors update.
- **Pattern Density:** Controls how many background objects appear.
- **Pattern Types:** Three distinct noise styles (geometric shapes, vertical lines, chaotic strokes).

### Audio Feedback
Each correct response plays a musical tone that ascends chromatically as you progress. Completing all 26 targets triggers a victory chime.

## Setup Instructions

### Running the Application

This is a single-file application containing all HTML, CSS, and JavaScript.

1. Open `index.html` in any modern web browser (Chrome, Edge, Firefox, Safari).
2. An internet connection is required to load the Firebase SDK for saving and loading history data.

### Technical Details

- **Frontend:** Vanilla JavaScript (ES6 Modules)
- **Rendering:** HTML5 Canvas (2D Context) for background noise; DOM elements for interactive targets
- **Audio:** Web Audio API for synthesized tones (no external assets required)
- **Data Storage:** Firebase Firestore
  - Collection path: `artifacts/{appId}/users/{uid}/leaderboard`
- **Authentication:** Firebase Anonymous Auth

## Controls

| Action | Control |
|--------|---------|
| Open Settings | Click ⚙️ Settings button |
| View History | Click 🏆 History button |
| Start/Stop Timer | Click ▶ Start / ⏹ Stop button |
| Randomize Positions | Press Spacebar (Alphabet mode) |
| Identify Target | Click target (Alphabet/Ball) or type letter (Key Ball/Peripheral/OKN) |

## Legal Disclaimer

**This software is not a medical device.** It is provided for educational, recreational, and general wellness purposes only. It is not intended to diagnose, treat, cure, or prevent any disease or medical condition, including (but not limited to) post-concussion syndrome, amblyopia, or other visual disorders.

Always consult with a qualified healthcare provider, optometrist, or vision therapist before beginning any vision training program. Do not use this application as a substitute for professional medical advice, diagnosis, or treatment.

**Seizure Warning:** This application contains flashing lights, high-contrast patterns, and rapidly changing images. If you have a history of photosensitive epilepsy or are sensitive to flashing or strobing lights, do not use this application.

## License

This project is open source and free to use for personal or educational purposes.
