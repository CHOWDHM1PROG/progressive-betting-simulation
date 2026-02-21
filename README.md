Progressive Betting Strategy Simulation
Overview

This project simulates a progressive bet-doubling strategy using Python. The basic idea is straightforward: after every loss, the next bet is doubled in an attempt to recover previous losses once a win eventually occurs.

On paper, the approach looks convincing. A single win after a losing streak should recover earlier losses and leave a small profit. However, this assumes unlimited funds and ignores the possibility of extended losing runs.

This simulation explores what actually happens when the strategy is applied repeatedly with a limited starting balance.

Rather than using real money, the program models a fair 50/50 game (similar to tossing a coin) and runs multiple simulated sessions to analyse how often the strategy results in profit, loss, or complete bankruptcy.

How the Strategy Works

The system follows a simple pattern:

Start with a fixed base bet.

If you win → reset to the original base bet.

If you lose → double the next bet.

Continue until:

You win and reset, or

You can no longer afford the next bet.

Simple Example

Starting balance: £10
Base bet: £1

Losing streak:

Bet £1 → Loss → Balance £9
Bet £2 → Loss → Balance £7
Bet £4 → Loss → Balance £3
Next bet would be £8 → Not affordable → Stop

Result: Significant loss.

Win after losses:

Bet £1 → Loss → Balance £9
Bet £2 → Loss → Balance £7
Bet £4 → Win → Balance £11

Net profit: £1

This example shows why the strategy can appear appealing. Small gains occur regularly. However, a prolonged losing streak can quickly deplete the available balance.

What This Program Does

The simulation:

Uses a random 50/50 outcome for each bet

Starts with a user-defined balance and base bet

Doubles the bet after every loss

Resets to the base bet after every win

Stops a session if:

The next bet cannot be afforded

The balance reaches zero

The maximum number of bets is reached

The program repeats this process across multiple sessions and records:

Sessions that end in profit

Sessions that end in loss

Sessions that end in bankruptcy

Results are displayed visually using Matplotlib.

Running the Program
Requirements

Install Python and Matplotlib:

pip install matplotlib
Run the Script
python progressive_betting_simulation.py

You will be prompted to enter:

Starting balance (must be greater than 0)

Initial bet amount (must be positive and not exceed the starting balance)

Number of bets per session (positive integer)

Number of sessions (positive integer)

The program includes input validation to prevent unrealistic or invalid configurations.

Output

After running, two charts are displayed.

1. Balance Paths

The left-hand plot shows how the account balance changes during each session.

Each line represents one simulated session. You will typically observe:

Gradual increases during winning periods

Sharp declines during losing streaks

Sessions ending early when funds are exhausted

This highlights how volatile the strategy can be.

2. Outcome Distribution

The right-hand pie chart summarises overall results:

Profit – Ending balance is higher than the starting balance

Loss – Ending balance is lower than the starting balance but above zero

Bust – Balance reached zero

Because the game is random, results will vary between runs. Over many sessions, you will generally find that although profits occur frequently, bankruptcies still happen and can outweigh consistent small gains.

Why This Is Interesting

Progressive bet-doubling strategies are often described as “safe” because they appear to guarantee recovery after a win. In practice, that assumption depends on unlimited capital and unlimited time.

This simulation demonstrates how limited bankroll constraints combined with exponential bet growth create a genuine risk of ruin, even in a fair 50/50 game.

Disclaimer

This project is for educational purposes only. It does not promote gambling and should not be interpreted as financial advice.