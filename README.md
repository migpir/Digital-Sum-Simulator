# Digital-Sum-Simulator
Practice tool understanding Digital Sums.
Digital Sum Simulation is an engaging, interactive web-based game that challenges players to test their luck and strategy with a 10x5 grid of tiles, each representing a U.S. state. The game combines elements of chance and probability, centered around the digital sum of randomly generated three-digit numbers.

How It Works
Game Setup: The game displays a 10x5 grid of tiles, each showing a state abbreviation (e.g., "NV" for Nevada) on the front. Behind each tile is a state name, a unique three-digit number (000–999) generated from a normal distribution (mean = 499.5, σ = 166), and its digital sum (the sum of its digits, ranging from 0 to 27).
Objective: Players select a "Flip Sum" value (0–27) and flip all tiles to reveal their numbers and digital sums. The goal is to match the chosen "Flip Sum" to earn higher winnings, displayed as "P/L" (Profit/Loss) on each tile.
Winnings Calculation:
If a tile’s digital sum matches the selected "Flip Sum," the winnings are 250 - cost_table[Flip Sum] (e.g., for "Flip Sum: 13," cost = 37.5, so P/L = 212.5), highlighted in bold, dark green (#008000), 14px font.
If the sums don’t match or no "Flip Sum" is selected, the winnings are cost_table[tile’s digital sum] (e.g., sum 21 → P/L = 13.5), shown in bold, red (#FF0000), 14px font.
The cost_table maps digital sums to costs (e.g., 0: 0.5, 1: 1.5, ..., 13: 37.5, ..., 27: 0.5).
Gameplay:
Flip All Tiles: Resets the grid with new numbers and flips all 50 tiles sequentially (500ms delay between flips), revealing state names, numbers, digital sums, and P/L values. Internally, the game tracks a score (+1 per tile matching the "Flip Sum," or +50 if no "Flip Sum" is selected), saved to localStorage for persistence across sessions.
Flip Sum: A dropdown lets players choose a digital sum (0–27) to target for higher P/L values and scoring. No action occurs until "Flip All Tiles" is clicked.
Reset: Resets the grid to its initial state (tiles face-down, new numbers generated on next flip) and clears the internal score to 0, saved to localStorage.
Visual Design:
Tiles: Fronts are red (#ff0000) with white text (#ffffff, 18px, bold). Backs are robin's egg blue (#00CCCC) with black text (#000000, 12px) for state names and sums, and bold, 14px P/L text (dark green for matches, red otherwise).
Controls: "Flip All Tiles" and "Reset" buttons, plus the "Flip Sum" dropdown, are styled in red (#ff0000, black text #000000, hover #cc0000, disabled #ff6666). Dropdown options appear in light blue (#ADD8E6) where supported.
The interface is clean, centered, and mobile-compatible, though the grid may require zooming on smaller screens.
Features
Interactive Gameplay: Flip tiles to reveal random numbers and see if your chosen sum pays off with higher winnings.
Dynamic Winnings: P/L values reflect a strategic balance of risk and reward, using a predefined cost table.
Persistent Scoring: An internal score tracks performance across sessions via localStorage, reset only by the "Reset" button.
Probability-Based: Numbers follow a normal distribution, making certain digital sums (e.g., around 13–14) more likely, adding a layer of statistical intrigue.
Mobile-Friendly: Playable on browsers (Chrome, Safari, Firefox) on desktop or mobile, with touch support.
Self-Contained: No external dependencies, making it easy to host or share.
How to Play
Open the game in a web browser.
Optionally select a "Flip Sum" (0–27) from the dropdown to target a specific digital sum.
Click "Flip All Tiles" to generate new numbers and flip all tiles, revealing state names, numbers, digital sums, and P/L values (green for matches, red otherwise).
Click "Reset" to start fresh with a new grid and cleared score.
Experiment with different "Flip Sum" choices to maximize winnings or explore the distribution of sums.
