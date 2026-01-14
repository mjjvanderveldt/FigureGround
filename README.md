
# Figure Ground Perception Trainer

A browser-based visual training tool designed to improve figure-ground discrimination skills, sustained attention, and visual sequencing. It is often used to aid recovery from post-concussion syndrome or to train visual processing speed.

It generates a chaotic, procedurally generated background using the HTML5 Canvas API to "camouflage" targets (text or objects). The user must visually isolate the targets from the moving noise.

## 🚀 Features

### Core Mechanics

-   **Procedural Chaos:** Three distinct noise modes (Geometric Shapes, Digital Rain, Chaotic Lines).
    
-   **Collision-Free Scattering:** Algorithms ensure targets are randomly placed but **never overlap** with each other.
    
-   **Smart Layout:** "Safe zones" prevent targets from being hidden behind UI controls or the timer.
    
-   **Responsive Design:** Adapts to window resizing dynamically.
    

### Game Modes

1.  **Sequential Search (Alphabet & Numbers):** - Find targets in order (e.g., A → B → C or 1 → 2 → 3).
    
    -   Includes a visual **Target Display** ("FIND: a") to guide the user.
        
    -   **Audio Feedback:** Plays a musical tone for every correct click, building a scale as you progress, with a victory chime at the end.
        
    -   **Toggleable Sets:** Switch between the Alphabet (a-z) and Numbers (1-26).
        
2.  **Bouncing Ball (Sustained Attention):**
    
    -   Track a single moving ball amidst the chaos.
        
    -   Click the ball **only** when it turns **RED**.
        
    -   Tests impulse control and tracking ability.
        

### Difficulty Modifiers

-   **Wandering Targets:** An optional setting where letters/numbers float around the screen and bounce off edges, requiring tracking rather than just scanning.
    
-   **Randomize Colors:** Randomizes the color of the text targets to increase visual noise and difficulty.
    
-   **Adjustable Chaos:** Sliders to control the speed and density of the background distractions.
    

### Progress Tracking

-   **Stopwatch:** Integrated timer to track performance.
    
-   **Leaderboard:** Automatically saves completion times to Firebase Firestore, allowing history to persist across sessions (per user).
    
-   **Local History:** Caches recent times locally for immediate feedback.
    

## 🎮 How to Use

### Mode 1: Alphabet / Numbers

1.  **Select Sequence:** Use the settings to choose between "Alphabet" or "Use Numbers (1-26)".
    
2.  **Start:** Click `▶ Start`. The background noise will begin.
    
3.  **The Task:** Look at the **FIND:** display at the bottom center. Scan the screen for that specific character.
    
4.  **Interact:** Click the correct character. You will hear a tone, and the target will change to the next in the sequence.
    
5.  **Complete:** Once you reach the end (z or 26), the timer stops automatically, and your time is logged.
    

### Mode 2: Bouncing Ball

1.  **Select Mode:** Open Settings and click "Ball".
    
2.  **Start:** Click `▶ Start`. A white ball will begin bouncing around the screen.
    
3.  **The Task:** Follow the ball with your eyes. Ignore the background noise.
    
4.  **Interact:** Wait for the ball to flash **RED**. Click it quickly before it turns white again.
    
5.  **Win:** Successfully catch the red ball 26 times to complete the session.
    

## ⚙️ Settings & Controls

Click `⚙️ Settings` to open the control panel:

-   **Game Mode:** Switch between _Alphabet_ and _Ball_.
    
-   **Chaos Speed:** Controls how fast the background distractors move.
    
-   **Pattern Density:** Controls how many background objects appear.
    
-   **Wandering Letters:** (Checkbox) Makes the text targets move around the screen.
    
-   **Randomize Colors:** (Checkbox) Changes text targets from white to random bright colors.
    
-   **Use Numbers:** (Checkbox) Switches the target set from a-z to 1-26.
    
-   **Randomize Positions:** Instantly reshuffles the targets (Spacebar shortcut).
    
-   **Change Pattern:** Cycles through the 3 background visual styles.
    

## 🛠️ Technical Setup

### Running the Application

This is a **Single-File Application** containing HTML, CSS, and JavaScript.

1.  **Browser:** Open `index.html` in any modern web browser (Chrome, Edge, Firefox, Safari).
    
2.  **Internet:** An internet connection is required to load the Firebase SDK and save/load history data.
    

### Architecture Details

-   **Frontend:** Vanilla JavaScript (ES6 Modules).
    
-   **Rendering:** HTML5 Canvas (2D Context) for noise; DOM elements for interaction.
    
-   **Audio:** Web Audio API for generating synthesized tones (no external assets required).
    
-   **Data:** Firebase Firestore.
    
    -   **Collection Path:** `artifacts/{appId}/users/{uid}/leaderboard`
        
-   **Auth:** Firebase Anonymous Auth.
    

## ⚠️ Disclaimer

**I am not a doctor or medical professional.** This software is provided for educational and entertainment purposes only. It is not intended to diagnose, treat, cure, or prevent any disease or medical condition, including post-concussion syndrome. Always seek the advice of your physician or other qualified health provider with any questions you may have regarding a medical condition or visual therapy regimen.

**Seizure Warning:** This application contains flashing lights and high-contrast moving patterns.

## 📄 License

This project is open source and free to use for personal or educational purposes.
