# UE23CS352A: Machine Learning Hackathon - "Hackman"

This repository contains the solution for the "Hackman" challenge. The goal is to build an intelligent Hangman assistant that uses a Hidden Markov Model (HMM) and a Reinforcement Learning (RL) agent to solve Hangman puzzles with maximum efficiency.

##  CHALLENGE

The challenge is to build a hybrid system to play Hangman. The agent must be trained *only* on the provided `corpus.txt` file and is evaluated on a hidden test set from the same corpus. The objective is to maximize wins while minimizing wrong and repeated guesses.

## ARCHITECTURE

Our solution is a hybrid system composed of two main components:

1.  **The "Oracle" (HMM):** A probabilistic language model (`src/oracle.py`) that, given the current masked word (e.g., `_ P P L _`) and guessed letters, calculates a probability distribution for all remaining letters. This is implemented by filtering the corpus for all possible matching words and calculating letter frequencies.
2.  **The "Brain" (DQN Agent):** A Deep Q-Network (`src/agent.py`) that acts as the decision-maker. It takes the full game state as input (masked word, guessed letters, lives remaining, and the HMM probability vector) and outputs the optimal letter to guess next.



## SETUP

Follow these steps to set up the project locally.

**1. Clone the Repository**
```bash
git clone <your-repo-url>
cd hackman-project
```
**2. Create and Activate the Virtual Environment**
```bash
# Create the venv
python3 -m venv .venv

# Activate on macOS/Linux
source .venv/bin/activate

# --- OR ---

# Activate on Windows (Command Prompt)
.venv\Scripts\activate.bat
```
**3. Install Requirements**
```bash
pip install -r requirements.txt
```

## RUNNING THE PROJECT

### 1. Train the Agent

To train the DQN agent from scratch, run the `train.py` script. This will use the `corpus.txt` file for training and save the final model weights to `models/dqn_agent.pth`.

```bash
python train.py
```

### 2. Evaluate the Agent

To evaluate the performance of your trained agent against the test.txt set, run the evaluate.py script. This will load the saved model from models/ and play one game for every word in the test set.

```bash
python evaluate.py
```

## NOTEBOOKS & DELIVERABLES

/notebooks/: Contains the Jupyter notebooks used for development, experimentation, and plotting.

/deliverables/: Contains the final Analysis_Report.pdf as required by the submission guidelines.