# Android Dice Game

A strategic dice game Android application built with **Kotlin** and **Jetpack Compose** where players compete against an intelligent computer opponent to reach a target score of 101 points (or custom target) using 5 dice.

## Game Overview

This is a turn-based dice game where a human player competes against the computer. Both players throw 5 dice simultaneously, with the objective of being the first to reach 101 points (or a custom target score). The game features strategic decision-making with optional re-rolls and an intelligent computer opponent.

## Game Rules

### Basic Gameplay
- Both players throw 5 dice simultaneously
- Score is calculated as the sum of all 5 dice faces
- First player to reach 101 points (or custom target) wins
- Each turn consists of up to 3 rolls (1 initial + 2 optional re-rolls)

### Turn Mechanics
1. **Initial Roll**: Both players roll all 5 dice
2. **Optional Re-rolls**: Players can choose to:
   - Score the current roll (end turn)
   - Re-roll selected dice (up to 2 more times)
   - Keep specific dice and re-roll others
3. **Forced Scoring**: After 3 total rolls, players must score

### Winning Conditions
- **Standard Win**: First player to reach target score
- **Tie Scenario**: If both players reach target in same number of attempts:
  - Player with higher score wins
  - If scores are equal: sudden death rounds until tie is broken
  - No re-rolls allowed in sudden death rounds

## Features

### Core Functionality
- **Intuitive UI**: Clean, user-friendly interface built with Jetpack Compose
- **Dice Animation**: Visual dice rolling with random outcomes (1-6)
- **Strategic Re-rolls**: Select which dice to keep/re-roll
- **Score Tracking**: Real-time score display for both players
- **Win/Loss Detection**: Automatic game termination with colored victory messages

### Advanced Features
- **Custom Target Score**: Set winning score (default: 101)
- **Win Counter**: Track total wins (Human:X / Computer:Y)
- **Intelligent AI**: Advanced computer strategy with decision-making algorithms
- **Tie Breaking**: Complete implementation of sudden death rules
- **Orientation Support**: Full portrait/landscape mode compatibility

### Technical Features
- **State Preservation**: Game state maintained through device rotations
- **No Third-party Libraries**: Built using only standard Android APIs
- **Jetpack Compose**: Modern UI toolkit (no XML layouts)
- **Activity Recreation Handling**: Proper lifecycle management

## Technology Stack

- **Language**: Kotlin
- **UI Framework**: Jetpack Compose
- **Platform**: Android
- **Minimum SDK**: API level specified in app configuration
- **Architecture**: MVVM pattern with Compose state management

## Installation & Setup

### Prerequisites
- Android Studio Arctic Fox or later
- Android SDK with minimum API level support
- Kotlin plugin enabled
- Device or emulator for testing

### Setup Instructions

1. **Clone the Repository**
```bash
git clone https://github.com/rehangodakumbura/MovieApp.git
cd android-dice-game
```

2. **Open in Android Studio**
- Launch Android Studio
- Select "Open an Existing Project"
- Navigate to the cloned directory
- Wait for Gradle sync to complete

3. **Build and Run**
- Connect an Android device or start an emulator
- Click "Run" button or use `Shift + F10`
- Install and launch the application

## How to Play

### Starting a Game
1. Launch the application
2. Tap **"New Game"** to start playing
3. Optionally set a custom target score
4. Begin rolling dice!

### During Gameplay
1. **Throw Dice**: Tap "Throw" to roll all 5 dice
2. **Select Dice**: Choose which dice to keep for re-rolls
3. **Re-roll**: Tap "Throw" again to re-roll unselected dice
4. **Score**: Tap "Score" to end turn and add points
5. **Strategy**: Decide whether to risk re-rolls for higher scores

### Game Controls
- **Throw Button**: Roll dice (initial or re-roll)
- **Score Button**: End turn and record current score
- **Dice Selection**: Tap dice images to select/deselect for keeping
- **Back Button**: Return to main menu after game ends

## Computer AI Strategy

The computer opponent uses an advanced decision-making algorithm that considers:

### Strategy Components
- **Risk Assessment**: Evaluates current roll value vs. potential improvements
- **Game State Analysis**: Considers current scores and remaining gap to target
- **Probability Calculations**: Estimates likelihood of improvement with re-rolls
- **Adaptive Difficulty**: Adjusts strategy based on game progression

### Decision Factors
1. **Current Roll Value**: Higher values less likely to be re-rolled
2. **Score Gap**: Trailing players take more risks
3. **Remaining Attempts**: End-game pressure influences decisions
4. **Dice Distribution**: Considers which specific dice to re-roll

The AI cannot see the human player's current dice but is aware of both players' total scores, creating realistic competitive gameplay.

## Project Structure

```
app/
├── src/main/java/com/yourpackage/dicegame/
│   ├── MainActivity.kt              # Main activity and navigation
│   ├── GameScreen.kt               # Main game interface
│   ├── GameViewModel.kt            # Game logic and state management
│   ├── DiceGame.kt                 # Core game mechanics
│   ├── ComputerStrategy.kt         # AI decision algorithms
│   ├── GameState.kt                # Game state data classes
│   └── ui/
│       ├── components/             # Reusable UI components
│       └── theme/                  # App theming
└── src/main/res/
    └── drawable/                   # Dice images and other assets
```

## Key Classes

### GameViewModel
- Manages game state and business logic
- Handles dice rolling and scoring
- Implements computer AI strategy
- Preserves state during configuration changes

### DiceGame
- Core game mechanics implementation
- Score calculations and win condition checking
- Turn management and re-roll logic

### ComputerStrategy
- Advanced AI decision-making algorithms
- Risk assessment and probability calculations
- Adaptive gameplay based on current game state

## Development Features

### State Management
- Proper handling of device rotations
- Activity recreation without data loss
- Compose state preservation techniques

### UI/UX Design
- Material Design principles
- Responsive layouts for different screen sizes
- Smooth animations and transitions
- Accessibility considerations

### Code Quality
- Clean architecture patterns
- Comprehensive code documentation
- Meaningful variable and function naming
- Modular component structure

## Testing

The application has been tested for:
- Various device orientations
- Different screen sizes and densities
- Game logic correctness
- AI strategy effectiveness
- State preservation scenarios
- Edge cases and error conditions

## Known Limitations

- Dice images require internet connection if using external resources
- AI strategy may be computationally intensive on older devices
- Win counter resets when app is completely closed

## Future Enhancements

Potential improvements for future versions:
- **Multiplayer Mode**: Network play between devices
- **Statistics Tracking**: Detailed game history and analytics
- **Custom Dice Themes**: Different visual styles for dice
- **Sound Effects**: Audio feedback for rolls and victories
- **Difficulty Levels**: Adjustable AI intelligence
- **Tournament Mode**: Best-of-X games series

### Development Guidelines
- Follow Kotlin coding conventions
- Use Jetpack Compose best practices
- Maintain compatibility with minimum SDK version
- Test on multiple device configurations
- Document any new AI strategy modifications

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

**[Rehan Godakumbura]**
- GitHub: [@rehangodakumbura](https://github.com/rehangodakumbura)
- Email: rehangod2003@gmail.com
