---
title: Architecture
---

# Architecture <span class="badge-inprogress">In Progress</span>

=== "Overview"

    ## System Architecture

    DeepFlyer uses a per-user container model. Every user who starts an activity gets their own isolated Docker container running the full simulation stack. The shared backend manages container lifecycle and serves the REST API.

    ```
    Browser
    +------------------+      WebSocket     +---------------------+
    |  React UI        | <----------------> |  Sim Container      |
    |                  |      MJPEG video   |  (one per user)     |
    |                  | <---------------- |                     |
    +--------+---------+                   |  Gazebo + PX4 SITL  |
             |                             |  ROS 2 nodes        |
             | REST API                   |  WebSocket bridge   |
             v                             +---------------------+
    +------------------+
    |  FastAPI Backend | --- Docker API --> Container Manager
    |                  |
    +--------+---------+
             |
             v
    +------------------+
    |  PostgreSQL DB   |
    +------------------+
    ```

    ### Key design decisions

    | Decision | Reason |
    |---|---|
    | One container per user | Full isolation: one crash cannot affect another user's session |
    | PX4 SITL inside container | Same firmware binary as real drones, maximising sim-to-real transfer |
    | WebSocket for control | Low-latency two-way link needed for real-time flight commands |
    | MJPEG for video | Browser-native, no plugins required |
    | JWT auth (8 hours) | Stateless authentication, no session table lookups on every request |

=== "Container Lifecycle"

    <div class="inprogress-box">
      <span class="icon">🚧</span>
      <h3>Being Written</h3>
      <p>This tab will cover the full container start, stop, and idle-timeout lifecycle.</p>
      <ul>
        <li>Container spawn sequence via Docker API</li>
        <li>Health check and readiness probe</li>
        <li>Idle detection and auto-destroy logic</li>
        <li>Port allocation (9000-9099 for API, 9100-9199 for video)</li>
        <li>GPU slot allocation</li>
      </ul>
    </div>

=== "WebSocket Protocol"

    <div class="inprogress-box">
      <span class="icon">🚧</span>
      <h3>Being Written</h3>
      <p>This tab will document all WebSocket message types used between the browser and the simulation container.</p>
      <ul>
        <li>Message type reference: arm, disarm, velocity, waypoints, set_avoidance_logic</li>
        <li>Telemetry message format</li>
        <li>Reconnection and heartbeat behaviour</li>
        <li>Error message types</li>
      </ul>
    </div>

=== "Data Flow"

    <div class="inprogress-box">
      <span class="icon">🚧</span>
      <h3>Being Written</h3>
      <p>This tab will trace the full data path from a browser keypress through to drone movement and back.</p>
      <ul>
        <li>Browser keypress to ROS 2 to PX4 to Gazebo physics to sensor data back to the browser</li>
        <li>Latency budget at each step</li>
        <li>Score calculation and save flow</li>
      </ul>
    </div>
