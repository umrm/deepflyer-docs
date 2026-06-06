---
title: API Reference
---

# API Reference <span class="badge-inprogress">In Progress</span>

=== "Endpoints Overview"

    ## REST API

    The backend API is available under `/api/`. All endpoints except register and login require a Bearer JWT in the `Authorization` header.

    | Method | Endpoint | Auth needed | Description |
    |---|---|---|---|
    | POST | `/api/auth/register` | No | Create a new account |
    | POST | `/api/auth/login` | No | Log in and get a JWT token |
    | GET | `/api/user/me` | Yes | Get your profile and stats |
    | POST | `/api/session/start` | Yes | Launch a simulation container |
    | POST | `/api/session/stop` | Yes | Stop the running container |
    | GET | `/api/session/status` | Yes | Check current session info |
    | POST | `/api/results` | Yes | Save an activity result and award badges |
    | GET | `/api/leaderboard` | Yes | Get ranked scores |

=== "Auth Endpoints"

    <div class="inprogress-box">
      <span class="icon">🚧</span>
      <h3>Being Written</h3>
      <p>This tab will provide full request and response schemas for the auth endpoints.</p>
      <ul>
        <li>POST /api/auth/register: required fields, validation rules, error codes</li>
        <li>POST /api/auth/login: OAuth2 password flow, JWT format and expiry</li>
        <li>Token refresh strategy</li>
        <li>Error response format</li>
      </ul>
    </div>

=== "Session Endpoints"

    <div class="inprogress-box">
      <span class="icon">🚧</span>
      <h3>Being Written</h3>
      <p>This tab will document the session management endpoints.</p>
      <ul>
        <li>POST /api/session/start: activity parameter, response shape including assigned ports</li>
        <li>POST /api/session/stop: graceful container teardown</li>
        <li>GET /api/session/status: running state, ports, activity name</li>
        <li>Port assignment scheme</li>
        <li>Concurrent session handling</li>
      </ul>
    </div>

=== "Results and Leaderboard"

    <div class="inprogress-box">
      <span class="icon">🚧</span>
      <h3>Being Written</h3>
      <p>This tab will detail the results and leaderboard endpoints.</p>
      <ul>
        <li>POST /api/results: score, duration, status fields; badge award logic</li>
        <li>GET /api/leaderboard: activity filter, limit parameter, response schema</li>
        <li>Badge award conditions and thresholds</li>
        <li>Score calculation per activity</li>
      </ul>
    </div>
