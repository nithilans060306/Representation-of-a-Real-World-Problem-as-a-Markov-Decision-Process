# Exp-1 Representation of a Student Study Planner as a Markov Decision Process (MDP)

## Overview

This project demonstrates how a **Student Study Planner** can be modeled as a **Markov Decision Process (MDP)**. The MDP framework is widely used in Artificial Intelligence and Reinforcement Learning to represent sequential decision-making problems.

In this project, a student's preparation for an examination is modeled using states, actions, transition probabilities, rewards, and a discount factor.

---

## Aim

To represent a Student Study Planner as a Markov Decision Process (MDP) by defining:

- State Space
- Action Space
- Transition Probability
- Reward Function
- Discount Factor
- Python Representation

---

# Problem Statement

A student plans daily study activities to prepare for examinations. Every day, the student chooses one of the following actions:

- Study
- Revise
- Practice Questions
- Take a Break

These actions affect the student's preparation level.

The objective is to select the best sequence of actions that maximizes learning and helps the student become fully prepared for the examination.

This real-world problem can be represented as a **Markov Decision Process (MDP).**

---

# MDP Components

MDP = (S, A, P, R, γ)

| Symbol | Description |
|---------|-------------|
| S | Set of States |
| A | Set of Actions |
| P | Transition Probability |
| R | Reward Function |
| γ | Discount Factor |

---

# State Space

```text
S = {
    Unprepared,
    Preparing,
    Well_Prepared,
    Exam_Ready
}
```

---

# Action Space

```text
A = {
    Study,
    Revise,
    Practice_Questions,
    Take_Break
}
```

---

# Transition Function

| Current State | Action | Next State | Probability |
|---------------|---------|------------|-------------|
| Unprepared | Study | Preparing | 0.90 |
| Preparing | Practice Questions | Well Prepared | 0.80 |
| Well Prepared | Revise | Exam Ready | 0.95 |
| Preparing | Take Break | Preparing | 1.00 |

---

# Reward Function

| Action | Reward |
|---------|-------:|
| Study | +5 |
| Revise | +4 |
| Practice Questions | +6 |
| Take Break | -2 |

---

# Discount Factor

```text
γ = 0.9
```

---

# Graphical Representation
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/0734205d-2a07-46fe-a73c-e53358b69edc" />


# Python Implementation

```py
# MDP Representation for student study planner using Python

print("Name: Nithilan S")
print("Register Number: 212223240108")

states = [
    "Unprepared",
    "Preparing",
    "Well Prepared",
    "Exam Ready"
]

actions = [
    "Study",
    "Revise",
    "Practice Questions",
    "Take Break"
]

transition = {
    ("Unprepared", "Study"): ("Preparing", 0.9),
    ("Preparing", "Practice Questions"): ("Well Prepared", 0.8),
    ("Well Prepared", "Revise"): ("Exam Ready", 0.95),
    ("Preparing", "Take Break"): ("Preparing", 1.0)
}

rewards = {
    "Study": 5,
    "Revise": 4,
    "Practice Questions": 6,
    "Take Break": -2
}

discount_factor = 0.9

print("\nStates:")
print(states)

print("\nActions:")
print(actions)

print("\nTransition Function:")
for key, value in transition.items():
    print(f"{key} --> {value}")

print("\nRewards:")
for action, reward in rewards.items():
    print(f"{action} : {reward}")

print("\nDiscount Factor (γ):", discount_factor)
```

# Output



# Result

The Student Study Planner was successfully modeled as a Markov Decision Process (MDP) and implemented using Python.
