# ft_transcendence

![Kubernetes](https://img.shields.io/badge/Orchestration-K3s-blue)
![Backend](https://img.shields.io/badge/Backend-Django-green)
![Frontend](https://img.shields.io/badge/Frontend-Vite%20%7C%20Vanilla%20JS-yellow)
![Database](https://img.shields.io/badge/Database-PostgreSQL-blue)
![Monitoring](https://img.shields.io/badge/Monitoring-Grafana%20%7C%20Prometheus-orange)

A comprehensive web application featuring a multiplayer Pong game with real-time chat, user management, and social features. Built with a microservices architecture using Django, WebSockets, and deployed on Kubernetes (K3s).

## 🏗️ Architecture

This application follows a microservices architecture orchestrated by K3s:

*   **Frontend**: Modern SPA using Vanilla JavaScript, Vite, and Three.js for 3D rendering.
*   **Login Service**: JWT-based authentication with OAuth2 support.
*   **Chat Service**: Real-time messaging with WebSocket connections.
*   **User Service**: User profiles, friends, and social features.
*   **Pong Service**: Multiplayer Pong game engine.
*   **Notification Service**: Real-time notifications across the platform.
*   **Documentation Service**: Centralized API documentation.
*   **Infrastructure**: Helm Charts for deployment, Traefik as Ingress Controller.
*   **Monitoring**: Grafana and Prometheus for observability.

## ✨ Features

### 🎮 Pong Game
*   **Real-time Multiplayer**: Low-latency matches via WebSockets.
*   **3D Graphics**: Immersive experience powered by Three.js.
*   **Game Modes**:
    *   **Local**: Practice against AI or another player locally.
    *   **Online**: Matchmaking against other users.
    *   **Tournament**: Organized brackets and competitions.
*   **Customization**: Paddle skins, ball colors, and game speed settings.

### 🔐 Authentication & Security
*   **JWT Token Authentication**: Secure session management.
*   **OAuth2 Integration**: Login with 42 Intra.
*   **Two-Factor Authentication (2FA)**: Enhanced account security.
*   **Session Management**: Automatic token refresh and validation.

### 💬 Real-time Chat
*   **Global Chat**: Community discussions.
*   **Private Messages**: Direct messaging between friends.
*   **Group Chats**: Create channels and invite users.
*   **Features**: User blocking, online status indicators, and game invites.

### 👤 User Profiles
*   **Statistics**: Win/Loss ratio, match history, and performance graphs.
*   **Social**: Friend requests, block lists, and online status.
*   **Avatars**: Upload custom profile pictures.

### 🔔 Notification System
*   **Real-time Alerts**: Instant updates for game invites, messages, and friend requests.
*   **History**: Review past notifications.

## 🚀 Installation & Setup

### Prerequisites
*   Linux Environment (Ubuntu 20.04+ recommended)
*   Docker (for container building)
*   Utilities: `git`, `curl`

### Quick Start (Automated)

The project includes a comprehensive script (`start-k3s.sh`) that sets up the entire K3s cluster, installs Helm dependencies, and deploys the application.

1.  **Clone the repository**
    ```bash
    git clone https://github.com/your-repo/Transcendence.git
    cd Transcendence
    ```

2.  **Run the Setup Script**
    ```bash
    chmod +x start-k3s.sh
    ./start-k3s.sh
    ```
    *This script will:*
    *   *Install K3s, Kubectl, and Helm (if missing).*
    *   *Deploy the monitoring stack (Grafana/Prometheus).*
    *   *Build and deploy the microservices.*
    *   *Configure local DNS in `/etc/hosts`.*

3.  **Access the Application**
    *   **Frontend**: [https://trascendence.42firenze.it](https://trascendence.42firenze.it)
    *   **Grafana**: [https://grafana.trascendence.local](https://grafana.trascendence.local) (Default: `admin`/`admin123`)
    *   **API Docs**: `http://localhost:8005` (Swagger/ReDoc)

## 📂 Project Structure

```
Transcendence/
├── Back-End/                 # Django Microservices
│   ├── login/               # Authentication Service
│   ├── chat/                # Chat Service
│   ├── task_user/           # User & Social Service (Friends, Profiles)
│   ├── Notifications/       # Notification Service
│   ├── pongProject/         # Game Service
│   └── api-docs/            # API Documentation Service
├── Front-End/               # Vite + Three.js Application
├── helm-charts/             # Kubernetes Helm Charts
├── Manifests/               # K8s Manifests (CRDs, etc.)
├── scripts/                 # Utility scripts
└── start-k3s.sh             # Main Deployment Script
```

## 🔌 API Endpoints

### Authentication Service (Port 8000)
*   `POST /api/auth/login/` - User login
*   `POST /api/auth/register/` - User registration
*   `GET /api/auth/user/` - Get user info

### Chat Service (Port 8001)
*   `GET /api/chat/rooms/` - List chat rooms
*   `POST /api/chat/messages/` - Send message

### User Service (Port 8002)
*   `GET /api/users/profile/` - Get user profile
*   `POST /api/friends/add/` - Send friend request

### Pong Service (Port 8004)
*   `POST /api/pong/games/` - Create game
*   `GET /api/pong/games/{id}/` - Get game state

## 🔮 Future Improvements

*   **AI Difficulty Levels**: varied machine learning models for opponents.
*   **Mobile Support**: Touch controls and responsive layout.
*   **Voice Chat**: Integrated WebRTC voice communication.
*   **Advanced Analytics**: Heatmaps and detailed gameplay stats.

---
*Developed by 42 Firenze Students*