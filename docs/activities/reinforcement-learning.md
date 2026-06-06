---
title: "RL Training"
---

# Reinforcement Learning Training <span class="badge-intermediate">Intermediate</span> <span class="badge-inprogress">In Progress</span>

<div class="activity-header">
<h2>Activity 5 of 5 &nbsp;·&nbsp; Intermediate</h2>
<div class="activity-meta">
  <span>⏱ Up to 30 minutes</span>
  <span>🧠 RL parameters</span>
  <span>📈 Live reward graph</span>
  <span>Route: <code>/activities/reinforcement-learning</code></span>
</div>
</div>

!!! warning "This activity is not yet available"
    Reinforcement Learning Training is still being built. The page is accessible but the activity is not fully functional yet. Full documentation will be added once the activity is ready.

---

## What This Activity Will Cover

When complete, this activity will let you:

- Configure a reinforcement learning agent with your own learning rate, reward weight, and episode count
- Launch a training job and watch the drone learn to fly episode by episode
- Read a live reward graph to track whether the agent is improving
- Hit a high score and appear on the leaderboard

---

## How RL Works (Background)

Even though the activity is not ready yet, here is the concept so you understand what is coming.

The drone tries an action, receives a reward score from the environment, and updates its strategy based on that score. Over many repetitions it learns which actions lead to higher rewards.

```
Agent takes action
        |
        v
Environment gives reward (positive = good, negative = bad)
        |
        v
Agent updates its strategy
        |
        v
Repeat for the next episode
```

The goal is to choose training parameters that help the agent learn quickly and reliably.

---

## Parameters You Will Configure

| Parameter | What it controls |
|---|---|
| **Learning Rate** | How much the agent updates its strategy after each episode. Too high = unstable. Too low = slow. Recommended starting value: 0.001 |
| **Reward Weight** | Scales how strongly the agent responds to the reward signal. Recommended starting value: 1.0 |
| **Max Episodes** | How many episodes to run before training stops automatically. A standard run uses 100 episodes |

---

## Badges You Can Earn

| Badge | Requirement |
|---|---|
| 🧠 First RL Success | Complete any RL Training run |
| 🎓 RL Master | Score 950 or higher |

---

Full step-by-step instructions and screenshots will be added here once the activity is complete.

---

[Back to All Activities](index.md)
