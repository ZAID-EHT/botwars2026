# BotWars 2026 — AEGIS

Qualifier submission for **Team AEGIS**.

The German Whist bot is located at:

```text
qualifiers/aegis.py
```

It provides the required function:

```python
def nextMove(gameState):
    ...
```

## Repository Structure

```text
botwars2026/
├── qualifiers/
│   └── aegis.py
└── README.md
```

The GitHub repository must be named **`botwars2026`** and should be created under the team leader's GitHub account.

> Important: The bot filename must match the exact name assigned to the team in the official Excel sheet. For Team AEGIS, the current filename is `aegis.py`.

## About the Bot

AEGIS is a deterministic German Whist bot developed for the BotWars 2026 qualifier.

Main features:

- legal-move protection;
- correct follow-suit handling;
- separate strategies for the recruitment and scoring phases;
- trump-aware move selection;
- public-card tracking;
- guaranteed-winner checks;
- safe emergency fallback;
- no external Python package requirements.

The bot uses only the information provided through the official `gameState` interface.

## Requirements

Install:

- Python 3.10 or newer;
- Git.

Check Python:

```bash
python --version
```

On some systems:

```bash
python3 --version
```

No third-party Python packages are required by `aegis.py`.

## Download the Official Game Engine

Clone the official BotWars repository:

```bash
git clone https://github.com/ua16/botwars-games.git
cd botwars-games
```

The German Whist engine is located in:

```text
germanwhist/
├── engine.py
├── main.py
└── players/
```

## Connect AEGIS to the Engine

Copy `qualifiers/aegis.py` into the engine's player folder.

### Windows Command Prompt

```bat
copy path\to\botwars2026\qualifiers\aegis.py germanwhist\players\aegis.py
```

### Windows PowerShell

```powershell
Copy-Item "path\to\botwars2026\qualifiers\aegis.py" "germanwhist\players\aegis.py"
```

### Linux or macOS

```bash
cp path/to/botwars2026/qualifiers/aegis.py germanwhist/players/aegis.py
```

After copying, the folder should look similar to:

```text
germanwhist/players/
├── aegis.py
├── basic_player.py
└── example_player.py
```

## Run the Game Engine

Move into the German Whist folder:

```bash
cd germanwhist
```

Run:

```bash
python main.py
```

On some systems:

```bash
python3 main.py
```

The engine loads compatible Python bot files from the `players` folder and runs games between them.

## Test AEGIS Against Other Bots

To test against another bot:

1. Place the other bot's `.py` file inside:

```text
botwars-games/germanwhist/players/
```

2. Make sure every bot contains:

```python
def nextMove(gameState):
    ...
```

3. Run:

```bash
python main.py
```

Example:

```text
players/
├── aegis.py
├── basic_player.py
├── example_player.py
└── another_test_bot.py
```

Only use bots that follow the official interface and game rules.

## Basic Compatibility Check

Check that the bot compiles:

```bash
python -m py_compile qualifiers/aegis.py
```

When testing from the official engine folder:

```bash
python -m py_compile players/aegis.py
```

A successful compilation normally produces no output.

## Testing Checklist

Confirm that:

- the bot imports successfully;
- `nextMove(gameState)` is available;
- every returned card belongs to the bot's hand;
- the bot follows the leading suit whenever possible;
- no crashes, exceptions, or forfeits occur;
- repeated games finish successfully;
- internal state resets correctly between games.

For fair comparisons, run many games and swap which bot starts first.

## Final Submission Instructions

Create a GitHub repository named:

```text
botwars2026
```

Upload only:

```text
README.md
qualifiers/aegis.py
```

Do not include:

- test bots;
- copied engine files;
- `__pycache__` folders;
- virtual environments;
- logs;
- benchmark scripts;
- development notes;
- extra Python modules.

## Upload Using Git

From inside the final `botwars2026` folder:

```bash
git init
git add README.md qualifiers/aegis.py
git commit -m "Final AEGIS BotWars 2026 qualifier submission"
git branch -M main
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/botwars2026.git
git push -u origin main
```

Replace `YOUR_GITHUB_USERNAME` with the team leader's GitHub username.

## Final Checklist

- [ ] Repository is named `botwars2026`
- [ ] Repository belongs to the team leader
- [ ] `README.md` is in the repository root
- [ ] Bot is located at `qualifiers/aegis.py`
- [ ] Filename matches the official Excel sheet exactly
- [ ] `nextMove(gameState)` exists
- [ ] Bot follows suit correctly
- [ ] Bot returns only legal cards
- [ ] Bot uses no external dependencies
- [ ] No test or development files are included
- [ ] Repository visibility follows the organizer's instructions

## Official References

- BotWars game repository: `https://github.com/ua16/botwars-games`
- Participant reference repository: `https://github.com/ua16/botwars-participant-ref`
