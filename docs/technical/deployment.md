---
title: Deployment
---

# Deployment <span class="badge-inprogress">In Progress</span>

=== "Overview"

    ## Running DeepFlyer on Your Own Server

    DeepFlyer is distributed as a Docker Compose stack. You can self-host it on any Linux machine with an NVIDIA GPU.

    ### Server Requirements

    | Component | Minimum |
    |---|---|
    | OS | Ubuntu 22.04 LTS or 24.04 LTS |
    | GPU | NVIDIA GPU with CUDA 12+ (GTX 1660 or better) |
    | RAM | 16 GB (32 GB recommended for 10+ concurrent users) |
    | Storage | 40 GB free for Docker images |
    | Docker | Engine 24+ with NVIDIA Container Toolkit |

    ### Quick Start

    <div class="inprogress-box">
      <span class="icon">🚧</span>
      <h3>Being Written</h3>
    </div>

=== "Environment Variables"

    <div class="inprogress-box">
      <span class="icon">🚧</span>
      <h3>Being Written</h3>
      <p>This tab will list every environment variable with its default value and description.</p>
      <ul>
        <li>SECRET_KEY: JWT signing secret</li>
        <li>POSTGRES_HOST / USER / PASSWORD / DB: database connection settings</li>
        <li>SIM_IMAGE: simulation container image tag</li>
        <li>DRONESIM_NETWORK: Docker network name</li>
        <li>API_BASE_PORT / VIDEO_BASE_PORT: port range start values</li>
        <li>IDLE_TIMEOUT_S: seconds before an idle container is destroyed</li>
        <li>USE_GPU: enable or disable NVIDIA GPU passthrough</li>
      </ul>
    </div>

=== "Docker Compose Services"

    <div class="inprogress-box">
      <span class="icon">🚧</span>
      <h3>Being Written</h3>
      <p>This tab will describe each service defined in docker-compose.yml.</p>
      <ul>
        <li>frontend: React app served by Nginx</li>
        <li>backend: FastAPI app with Uvicorn</li>
        <li>postgres: PostgreSQL 15 with init scripts</li>
        <li>Volume mounts and network configuration</li>
        <li>Health checks and restart policies</li>
        <li>GPU device reservation syntax</li>
      </ul>
    </div>

=== "Database Schema"

    <div class="inprogress-box">
      <span class="icon">🚧</span>
      <h3>Being Written</h3>
      <p>This tab will show the full PostgreSQL schema.</p>
      <ul>
        <li>users table: id, name, email, hashed_password, created_at</li>
        <li>sim_sessions table: user_id, activity, api_port, video_port, status, timestamps</li>
        <li>activity_results table: user_id, activity, score, duration_s, status, created_at</li>
        <li>user_badges table: user_id, badge, awarded_at</li>
        <li>Index definitions and constraints</li>
      </ul>
    </div>
