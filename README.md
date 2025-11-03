# Hackman — HMM + DQN for Hangman

Minimal project README. This file intentionally contains only brief, essential information (no contact or next-steps section).

Summary
-------

Hybrid Hangman solver combining a Hidden Markov Model (HMM) language oracle with a Deep Q-Network (DQN) policy agent. The HMM suggests letter probabilities from the provided corpus; the DQN learns when to follow the oracle or explore other letters.

Repository layout
---------------

- `corpus.txt` — training corpus (one word per line)
- `test.txt` — evaluation words (one word per line)
- `ML12_Hankman.ipynb` — development notebook (exploration and experiments)
- `train.py` — training script (if present)
- `evaluate.py` — evaluation script (if present)

Quickstart
----------

1. Create & activate a virtual environment

```bash
python3 -m venv .venv
source .venv/bin/activate
```

2. Install dependencies

```bash
pip install -r requirements.txt
```

Running
-------

Train the agent (example):

```bash
python train.py
```

Evaluate a model on `test.txt` (example):

```bash
python evaluate.py --model models/dqn_agent.pth --test-file test.txt
```

Data and evaluation notes
-------------------------

- Train only on `corpus.txt`. Evaluate on `test.txt` or a held-out split.
- Key metrics: win rate, average wrong guesses, repeated guesses.
