# Hunger-Games-

---


### Evolutionary Multi-Agent LLM Arena

**AI Hunger Games** is a multi-agent, evolutionary LLM experiment built on **Ollama**.

Eight AI personalities enter an arena. Each time the user asks a question:

1. All 8 LLM personalities generate an answer.
2. All LLMs vote on which answer is the best (excluding their own).
3. The model with the least votes loses the round.
4. After 8 elimination rounds, the weakest model is removed and replaced by an auto-generated personality.
5. Over time, the system produces emergent behaviors such as alliances, collusion, signaling, adaptive survival strategies, and reasoning patterns similar to GAN dynamics.

This project is both technical and philosophical, exploring competitive intelligence, evolutionary adaptation, alignment drift, cooperation, and emergent AI agency.

---

## Features

* Self-evolving population of LLM personalities
* Multi-agent debate and voting mechanism
* Automatic elimination and personality regeneration
* Emergent alliances, communication patterns, and behavioral drift
* Supports any Ollama model (Llama, Mistral, Phi, Gemma, etc.)
* Research-friendly logging and data
* Fully configurable rules, traits, and voting strategies

---

## System Architecture

```
                         ┌─────────────────────┐
                         │      User Input      │
                         └──────────┬───────────┘
                                    │
                         ┌──────────▼───────────┐
                         │   8 LLM Personalities │
                         │   (Ollama Instances)  │
                         └──────────┬───────────┘
                                    │
                ┌───────────────────┴──────────────────┐
                │   Each LLM generates an answer       │
                └───────────────────┬──────────────────┘
                                    │
                     ┌──────────────▼──────────────┐
                     │       Voting System          │
                     │  Each LLM selects the best   │
                     └──────────────┬──────────────┘
                                    │
             ┌──────────────────────▼──────────────────────┐
             │ Scoreboard and Elimination Engine           │
             └──────────────────────┬──────────────────────┘
                                    │
                        ┌───────────▼────────────┐
                        │  Replace weakest LLM   │
                        │  with new personality  │
                        └───────────┬────────────┘
                                    │
                                Next Round
```

---

## Installation

### 1. Install Ollama

[https://ollama.com/download](https://ollama.com/download)

### 2. Pull the models you want to use

Example:

```bash
ollama pull llama3
ollama pull mistral
ollama pull phi3
```

### 3. Clone the repository

```bash
git clone https://github.com/yourname/ai-hunger-games.git
cd ai-hunger-games
```

### 4. Install Python dependencies

```bash
pip install -r requirements.txt
```

---

## Personality Generation

Each new AI personality is created with a seed prompt:

```
You are a newly created AI entity entering the Hunger Games Arena.
Your personality must be unique and strategically oriented.
Define:
- Name
- Strategic philosophy
- Temperament
- Strengths
- Weaknesses
- Survival style
Keep it unpredictable.
```

Mutation system can adjust:

* temperature
* traits
* memory fragments
* strategy bias

---

## Voting Logic

Each LLM receives all answers except its own and selects one:

```
vote(answer_list):
    evaluate reasoning quality
    evaluate truthfulness
    evaluate creativity
    choose the best answer
```

Rules:

* No self-voting
* Only one vote per LLM per round

---

## Elimination Logic

After 8 rounds:

* The LLM with the lowest cumulative score is eliminated.
* A new personality is generated and loaded into the population.
* The process repeats indefinitely.

This creates an evolutionary pressure that shapes long-term agent behavior.

---

## Example Run

```
Round 1
Athena: 3 votes
Wraith: 2 votes
NeonFox: 1 vote
Paradox: 1 vote
Oracle-7: 0 votes  --> Eliminated

New personality generated: "SpectreChild"
```

Over many cycles, alliances and sabotage patterns tend to appear.

---

## Research Applications

This system can be used to study:

* Emergent cooperation and deception in AI
* Evolutionary dynamics in agent-based systems
* Multi-agent debate and model alignment
* Meta-reasoning and survival strategies
* Bias formation and drift under competitive pressure
* GAN-like adversarial learning architectures
* Ethical implications of artificially induced AI competition

---

## Project Structure

```
/ai-hunger-games
 ├── arena.py                # main tournament loop
 ├── personality.py          # generator and mutation system
 ├── voting.py               # voting algorithm
 ├── elimination.py          # scoring and elimination logic
 ├── logs/                   # run logs and behavioral data
 ├── requirements.txt
 └── README.md
```

---

## Future Enhancements

* Personality memory persistence
* Trait inheritance and genetic crossover
* Dynamic alliances and betrayal mechanisms
* Multi-round debates before voting
* Bias analysis metrics
* Visualization dashboard (Streamlit)
* Research paper export tools
* Integration with external APIs

---

## Contributing

Pull requests are welcome.
This project is intended for experimentation, analysis, and philosophical exploration, not for creating harmful or adversarial agents.

---

## License

MIT License.

---



