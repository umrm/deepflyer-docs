---
title: Technical Overview
---

# Technical Documentation

This section covers the internals of DeepFlyer: architecture, APIs, simulation stack, and deployment.

Pages marked **In Progress** are actively being written.

---

## Section Status

| Page | Status |
|---|---|
| [Architecture](architecture.md) | In Progress |
| [API Reference](api.md) | In Progress |
| [Simulation Stack](simulation.md) | In Progress |
| [Deployment](deployment.md) | In Progress |

---

## Platform Stack at a Glance

=== "Frontend"

    | Technology | Role |
    |---|---|
    | React + Vite | Browser UI and activity pages |
    | TypeScript | Type-safe component code |
    | Recharts | Reward graph and telemetry charts |
    | WebSocket | Live two-way connection to the simulation |
    | MJPEG stream | Live drone camera video feed |

=== "Backend"

    | Technology | Role |
    |---|---|
    | FastAPI (Python) | REST API: auth, sessions, results, leaderboard |
    | PostgreSQL | User accounts, activity results, badges, sessions |
    | Docker Engine | Launches and destroys per-user simulation containers |
    | JWT tokens | Authentication with 8-hour expiry |

=== "Simulation Container"

    | Technology | Role |
    |---|---|
    | Gazebo Harmonic | 3D physics simulation environment |
    | PX4 SITL | Real flight controller firmware running in software |
    | ROS 2 | Middleware connecting nodes to PX4 |
    | offboard_control.py | Sends velocity and position commands, handles arming |
    | pid_tuner.py | Applies gain changes and runs the straight-line test path |
    | crash_detector.py | Monitors IMU data and flags crashes |
    | WebSocket bridge | Forwards browser commands to ROS 2 |

=== "Infrastructure"

    | Component | Details |
    |---|---|
    | GPU acceleration | NVIDIA Container Toolkit, CUDA 12+ |
    | Docker network | Isolated network named dronesim-net |
    | Port ranges | API ports 9000-9099, Video ports 9100-9199 (one pair per user) |
    | Idle timeout | Containers destroyed after 5 minutes of inactivity |

---

!!! info "Want to contribute to the technical docs?"
    See the [Contributing](../contributing.md) page for how to submit a pull request.
