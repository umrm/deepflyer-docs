---
title: The Interface
---

# The Interface

A quick tour of the DeepFlyer site: the navigation bar, the status indicators you will see on every activity page, and how sessions work.

---

## Navigation Bar

![Navigation Bar](../assets/images/navbar.png)

The navigation bar is visible at the top of every page once you are logged in.

| Link | Where it takes you |
|---|---|
| **DeepFlyer** logo | Home page |
| **Dashboard** | Your training stats, recent activity, and badges |
| **Activities** | Browse and launch all five activities |
| **Leaderboard** | Global pilot rankings by score |
| **Profile** | Your account details and badge collection |
| **Log Out** | Sign out |

---

## Status Indicators

Every activity page shows a connection dot in the top bar. It tells you whether your browser is currently linked to the simulation.

| What you see | What it means | What to do |
|---|---|---|
| <span class="status-live">● LIVE</span> | Connected, simulation is running | Wait 1-2 minutes, then arm |
| <span class="status-connecting">● CONNECTING...</span> | Establishing connection | Wait a few seconds |
| <span class="status-disconnected">● DISCONNECTED</span> | Connection lost | Page reconnects automatically within 3 seconds |

!!! warning "LIVE does not mean the drone is ready to arm yet"
    When the dot turns green, the WebSocket connection is established but the simulation environment (Gazebo world, drone, and sensors) is still loading in the background. **Wait 1 to 2 minutes after seeing LIVE before clicking ARM.** Arming too early may have no effect or show an error in the log. This is a known issue and will be fixed in a future update.

---

## Sessions

### Each activity start launches a fresh container

Every time you click **Start** on an activity card, the platform closes any existing simulation and launches a brand new container. This applies every time, including if you are switching from one activity to another.

Each start takes around **30 seconds** regardless of whether you have run an activity before in the session.

!!! info "No container is reused between activities"
    If you are on Activity 1 and click Start on Activity 2, the Activity 1 container closes and a new one starts for Activity 2. Plan to wait 30 seconds each time you switch.

### Idle timeout

If you leave an activity page open without doing anything, the container shuts down after **5 minutes** of inactivity. This keeps server resources free for other users.

!!! warning "Disarm before navigating away"
    If you leave an activity page without clicking Disarm, your score for that session will not be saved. Always click **Disarm** before switching pages or closing the tab.

### Reconnecting

If you close a browser tab and come back while the container is still running, the page reconnects automatically. The status dot will briefly show <span class="status-connecting">● CONNECTING...</span> and then switch back to <span class="status-live">● LIVE</span>.

---

## The Log Terminal

Every activity has a scrollable log panel in the bottom-left area of the page. It records everything that happens during your session.

| Prefix | What it logs |
|---|---|
| `[SYS]` | System events: connection status, arming state changes |
| `[CMD]` | Commands you sent: arm, disarm, velocity |
| `[TEL]` | Position and heading data while flying |
| `[LOGIC]` | Obstacle avoidance logic deploy events |
| `[CRASH]` | Crash detection events |
| `[ERR]` | Errors: connection problems, invalid commands |

---

## Next Steps

- [Quick Start](quickstart.md): Create an account and complete your first flight
- [All Activities](../activities/index.md): See what each activity involves before you start
