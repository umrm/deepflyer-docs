---
title: Simulation Stack
---

# Simulation Stack <span class="badge-inprogress">In Progress</span>

=== "Overview"

    ## What Runs Inside Each Container

    | Component | Version | Role |
    |---|---|---|
    | Gazebo Harmonic | gz-harmonic | 3D physics simulation and world rendering |
    | PX4 SITL | v1.14+ | Real flight controller firmware in software |
    | ROS 2 | Humble | Middleware connecting nodes to PX4 |
    | Vehicle | gz_my_drone | Quadrotor model with onboard camera |
    | World | lawn | Indoor environment with obstacles |

    ### ROS 2 Nodes

    | File | What it does |
    |---|---|
    | offboard_control.py | Publishes velocity and position setpoints to PX4, handles arm and disarm, manages waypoint missions |
    | pid_tuner.py | Applies PID gain parameters to the PX4 rate controller, runs the straight-line CTE test path |
    | crash_detector.py | Subscribes to the IMU topic and flags crash events when acceleration exceeds a threshold |

=== "PX4 SITL Details"

    <div class="inprogress-box">
      <span class="icon">🚧</span>
      <h3>Being Written</h3>
      <p>This tab will cover the PX4 SITL configuration used by DeepFlyer.</p>
      <ul>
        <li>PX4 parameters set per activity</li>
        <li>Offboard mode enable sequence</li>
        <li>uXRCE-DDS bridge configuration</li>
        <li>Rate controller gain parameter names used in the PID Tuning activity</li>
        <li>Vehicle model files and sensor configuration</li>
      </ul>
    </div>

=== "ROS 2 Node Details"

    <div class="inprogress-box">
      <span class="icon">🚧</span>
      <h3>Being Written</h3>
      <p>This tab will document each ROS 2 node with full topic and message type references.</p>
      <ul>
        <li>offboard_control.py: published topics, subscribed topics, service calls</li>
        <li>pid_tuner.py: gain parameter mapping to PX4 parameter IDs</li>
        <li>crash_detector.py: IMU threshold values and reset procedure</li>
        <li>WebSocket to ROS 2 message mapping table</li>
      </ul>
    </div>

=== "RL Training Pipeline"

    <div class="inprogress-box">
      <span class="icon">🚧</span>
      <h3>Being Written</h3>
      <p>This tab will describe the reinforcement learning training implementation.</p>
      <ul>
        <li>Observation space: what sensor inputs the policy receives</li>
        <li>Action space: what velocity commands the policy outputs</li>
        <li>Reward function components and weights</li>
        <li>Episode reset logic</li>
        <li>Training loop and checkpoint saving</li>
        <li>Model export format for sim-to-real transfer</li>
      </ul>
    </div>
