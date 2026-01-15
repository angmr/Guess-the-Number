# Guess-The-Number

A Python-based number guessing game that subverts player expectations through interactive personality and behavioral tracking. Built before the AI era as a demonstration of creative game design and GUI programming.

## The Twist

Unlike traditional number-guessing games, this implementation doesn't simply end when the game is over. The program actively tracks player behavior and responds with escalating personality—rewarding winners while expressing frustration at players who refuse to stop clicking. The game loop intentionally allows interaction beyond the stated rules, transforming the experience from "guess the number" to "interact with an increasingly exasperated program."

## Technical Highlights

### Core Architecture
- **Event-driven GUI**: Custom Tkinter interface with modal dialogs for feedback
- **State management**: Global variables tracking attempts, win conditions, and post-game interactions
- **Input validation**: Exception handling for non-integer inputs with graceful fallback
- **Dynamic UI updates**: Progressive label creation and widget destruction based on game state

### Implementation Features

**Multimedia Integration**
- PIL (Pillow) for custom image rendering (donut reward graphic)
- playsound module for audio feedback on user interactions
- Custom cursor implementation via `.cur` file

**Behavioral Programming**
```python
# Tracks attempts beyond max_tries, enabling post-game interactions
elif attempts == max_tries + 5:
    submit_button.state = DISABLED
    exit_button.grid()
```

**ASCII Art UI Elements**
- Animated bunny character that changes expression based on player behavior
- Visual reward system (clickable donut for winners)

**Progressive Feedback System**
- Modal windows (Toplevel) for immediate guess feedback
- Contextual messages that adapt to player persistence
- Button state management (enabling/disabling based on game flow)

### Code Structure

```
guess_the_number.py
├── Game State Variables (attempts, found, secret_number)
├── UI Callbacks
│   ├── submit()          # Main game loop with behavioral tracking
│   ├── game_won()        # Victory state with reward
│   ├── show_hint()       # Optional hint system
│   └── open_message_box()# Modal feedback dialogs
├── Multimedia Functions
│   ├── donut_destroy()   # Reward interaction
│   └── close_window()    # Exit with audio
└── Tkinter Setup
    ├── Custom cursor/icon
    ├── Startup screen with instructions
    └── Dynamic widget generation
```

## Features

- **Limited Attempts**: 3 tries to guess a number between 0-10
- **Intelligent Feedback**: "Too high" / "Too low" guidance via popup windows
- **Hint System**: Optional button revealing the number range
- **Reward Mechanism**: Interactive donut graphic for successful players
- **Easter Eggs**: Hidden responses to unconventional gameplay patterns
- **Sound Design**: Audio feedback for all major interactions
- **Custom Theming**: Icon, cursor, and visual personality

## Installation

### Requirements
```bash
pip install pillow playsound
```

### Dependencies
- Python 3.x
- tkinter (included with Python)
- PIL/Pillow
- playsound

### Assets Required
The following files must be in the same directory as `guess_the_number.py`:
- `icon.ico` - Window icon
- `cursor.cur` - Custom mouse cursor
- `donut.png` - Reward image
- `click.mp3` - Button click sound
- `donut.mp3` - Reward collection sound
- `exit.mp3` - Exit sound

## Usage

```bash
python guess_the_number.py
```

1. Click "Next" on the startup screen
2. Enter your guess (0-10) in the text field
3. Click "Submit my guess!" to check your answer
4. Use "Get Hint" if needed (reveals range)
5. Try to find the number in 3 attempts

**Pro tip**: See what happens if you keep clicking after the game ends...

## Design Philosophy

This project demonstrates that small programs can have personality. By anticipating and responding to player behavior that goes beyond the "intended" gameplay, the program creates memorable interactions that feel more like conversing with an entity than executing a script.

The implementation showcases:
- **User experience design**: Anticipating edge cases and turning them into features
- **State machine logic**: Managing multiple game states and transitions
- **Multimedia programming**: Integrating audio and graphics into Python applications
- **Creative problem-solving**: Using game mechanics to explore human-computer interaction

## Technical Decisions

**Why Global Variables?**
For a single-session game with one concurrent state, global state management is appropriate and keeps the code readable.

**Why Tkinter?**
Lightweight, cross-platform, batteries-included GUI framework that requires no additional installation.

**Why Modal Dialogs for Feedback?**
Toplevel windows force player acknowledgment of feedback, creating deliberate pacing.

## License

Free to use, modify, and learn from.

## Author Note

Handcoded before AI existed—demonstrating that creativity in software engineering comes from human intuition about how users think and behave.

---

*Live demo available at: [https://angmi.gr/html/guess-the-number.html](https://angmi.gr/html/guess-the-number.html)*
