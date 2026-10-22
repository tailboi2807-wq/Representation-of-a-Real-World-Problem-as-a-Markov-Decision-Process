# Representation-of-a-Real-World-Problem-as-a-Markov-Decision-Process


## Aim
To identify a real-world problem and represent it as a Markov Decision Process (MDP) by defining its states, actions, transition probabilities, rewards, and Python representation.

---

## Problem Statement

### Problem Description
A smart traffic signal system is used to control traffic at a road junction. The system observes traffic density on different roads and decides which traffic signal should receive a green light. Its main goal is to reduce traffic congestion, minimize vehicle waiting time, and improve traffic flow.

The system uses reinforcement learning concepts to select suitable actions based on the current traffic conditions and the rewards received.
---

## MDP Components

A Markov Decision Process is represented as:

\[
MDP=(S,A,P,R,\gamma)
\]

Symbol	Meaning
\(S\)	Set of states
\(A\)	Set of actions
\(P\)	Transition probability function
\(R\)	Reward function
\(\gamma\)	Discount factor
---

## State Space

Write your answer here.

The state space should list all possible situations in which the agent can exist.

Example format:

```text
S = {
    Low Traffic,
    Medium Traffic,
    High Traffic
}
```

- Low Traffic: A small number of vehicles are waiting.
- Medium Traffic: A moderate number of vehicles are waiting.
- High Traffic: A large number of vehicles are waiting.

---

## Sample State
A sample state is High Traffic, where many vehicles are waiting at a junction. The system must choose a suitable signal action to reduce congestion.
---

## Action Space

The action space contains the possible actions available to the traffic signal controller.
```text
A = {
    Keep Green Signal,
    Switch Green Signal
}
```
Keep Green Signal: Continue the current green signal.

Switch Green Signal: Change the green signal to another road.

---

## Sample Action
A sample action is Keep Green Signal. When traffic density is high on the current road, the system may continue the green signal to allow more vehicles to pass.
---

## Transition Probability
Transition probability describes the probability of moving from one traffic state to another after performing an action.n.

General form:

$$
P(s' \mid s,a)
$$

This means:

Current State	Action	Next State	Probability
High Traffic	Keep Green Signal	Medium Traffic	0.7
High Traffic	Keep Green Signal	High Traffic	0.3
Medium Traffic	Switch Green Signal	Low Traffic	0.6
Medium Traffic	Switch Green Signal	Medium Traffic	0.4

These probabilities are illustrative values used for this assignment.
---

## Reward Function

Write your answer here.

The reward function provides feedback based on the traffic conditions and the action performed.

$$
R(s,a,s')
$$

Sample rewards:
Traffic Condition	Reward
Traffic congestion decreases	+10
Traffic remains unchanged	+2
Traffic congestion increases	-10

The system tries to maximize the total reward by reducing congestion and vehicle waiting time.

---

## Graphical Representation

<img width="775" height="497" alt="image" src="https://github.com/user-attachments/assets/69fdc0c6-6fc0-42c0-b766-bb6f460a30eb" />


Draw the MDP graph.

The graph should include:

1. States as nodes.
2. Actions as arrows.
3. Rewards on transitions.
4. Transition probabilities if applicable.


---

## Python Representation

```python

# MDP Representation using Python

print("Name: Mukesh ")
print("Register Number: 212225240093")

# State space
states = ["Low Traffic", "Medium Traffic", "High Traffic"]

# Action space
actions = ["Keep Green Signal", "Switch Green Signal"]

# Transition probabilities
transitions = {
    ("High Traffic", "Keep Green Signal"): {
        "Medium Traffic": 0.7,
        "High Traffic": 0.3
    },
    ("Medium Traffic", "Switch Green Signal"): {
        "Low Traffic": 0.6,
        "Medium Traffic": 0.4
    },
    ("Low Traffic", "Keep Green Signal"): {
        "Low Traffic": 0.8,
        "Medium Traffic": 0.2
    }
}

# Reward function
rewards = {
    ("High Traffic", "Medium Traffic"): 10,
    ("High Traffic", "High Traffic"): 2,
    ("Medium Traffic", "Low Traffic"): 10,
    ("Medium Traffic", "Medium Traffic"): 2,
    ("Low Traffic", "Low Traffic"): 2,
    ("Low Traffic", "Medium Traffic"): -10
}

# Discount factor
gamma = 0.9

# Display MDP details
print("\nStates:", states)
print("Actions:", actions)
print("Transition Probabilities:")

for key, value in transitions.items():
    print(key, "->", value)

print("\nRewards:", rewards)
print("Discount Factor:", gamma)

print("\nMDP representation completed successfully.")

```
---
## Output

Name: Mukesh
Register Number: 212225240093

States: ['Low Traffic', 'Medium Traffic', 'High Traffic']
Actions: ['Keep Green Signal', 'Switch Green Signal']

Transition Probabilities:
('High Traffic', 'Keep Green Signal') -> {'Medium Traffic': 0.7, 'High Traffic': 0.3}
('Medium Traffic', 'Switch Green Signal') -> {'Low Traffic': 0.6, 'Medium Traffic': 0.4}
('Low Traffic', 'Keep Green Signal') -> {'Low Traffic': 0.8, 'Medium Traffic': 0.2}

Rewards: {('High Traffic', 'Medium Traffic'): 10, ('High Traffic', 'High Traffic'): 2, ('Medium Traffic', 'Low Traffic'): 10, ('Medium Traffic', 'Medium Traffic'): 2, ('Low Traffic', 'Low Traffic'): 2, ('Low Traffic', 'Medium Traffic'): -10}
Discount Factor: 0.9

MDP representation completed successfully.
---

## Result
Thus, a smart traffic signal system was successfully represented as a Markov Decision Process by defining its state space, action space, transition probabilities, reward function, and discount factor. The Python program demonstrates how an MDP can model a real-world problem and help make decisions to reduce traffic congestion.
---

