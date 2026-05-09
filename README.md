# NU-CCIT MVC Capstone Starter

A structured monorepo template for **National University CCIT** capstone projects following a multi-layer **MVC architecture** — covering backend, frontend, mobile, infrastructure, novelty technology, and academic manuscript.

---

## 📁 Repository Structure

```
NU-CCIT-MVC-Capstone-Starter/
├── backend/        # Express.js (CommonJS) REST API
├── frontend/       # React + Vite web client
├── mobile/         # Flutter mobile app
├── infra/          # MongoDB + Mongo Express on Docker
├── novelty/        # Emerging technology layer (team-defined)
├── manuscript/     # Academic paper, diagrams, surveys, tables
└── .gitignore
```

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| Backend | Node.js + Express.js (CommonJS) |
| Frontend | React + Vite |
| Mobile | Flutter (Dart) |
| Database | MongoDB |
| DB Admin | Mongo Express |
| Infrastructure | Docker + Docker Compose |
| Novelty | _(team-defined — see below)_ |

---

## 🗂 Folder Breakdown

### `backend/`
Express.js REST API using **CommonJS** (`require`/`module.exports`). Houses the **Models** (Mongoose schemas), **Controllers** (route handlers), and **Routes**. Connects to MongoDB via the Docker network.

### `frontend/`
React web app scaffolded with **Vite**. The browser-based **View** layer that consumes the backend REST API.

### `mobile/`
**Flutter** mobile application (Dart). Cross-platform — builds to Android and iOS — and communicates with the same backend API.

### `infra/`
Docker Compose configuration that spins up:
- **MongoDB** — the primary database
- **Mongo Express** — a web-based MongoDB admin UI

### `novelty/`
> ⚠️ **Intentionally left empty.**

Populated by the team based on their chosen emerging technology:

| Novelty Type | Examples |
|---|---|
| **AI / ML** | Model training, inference pipeline, dataset processing |
| **Blockchain** | Smart contracts, on-chain logic, wallet integration |
| **Automation** | RPA scripts, workflow automation, scheduled jobs |
| **Systems** | Go or Rust microservices, low-level optimization |
| **Other** | IoT, AR/VR, computer vision, NLP, etc. |

### `manuscript/`
All academic research assets, version-controlled alongside the code:

```
manuscript/
├── paper/        # .docx and .pdf thesis drafts
├── diagrams/     # .drawio / .png / .svg system diagrams
├── tables/       # .xlsx or .csv data tables
└── surveys/      # Questionnaires and evaluation forms
```

---

## ✅ Prerequisites

Make sure the following are installed on your machine before proceeding:

| Tool | Download |
|---|---|
| Git | https://git-scm.com |
| Node.js (v18+) | https://nodejs.org |
| Docker Desktop | https://www.docker.com/products/docker-desktop |
| Flutter SDK | https://docs.flutter.dev/get-started/install |

---

## 🚀 Step-by-Step Setup

### 1. Clone the Repository

```bash
git clone https://github.com/Ian-nwb/NU-CCIT-MVC-Capstone-Starter.git
cd NU-CCIT-MVC-Capstone-Starter
```

---

### 2. Start the Database (Docker)

Spin up MongoDB and Mongo Express using Docker Compose.

```bash
cd infra
docker compose up -d
```

| Service | URL |
|---|---|
| MongoDB | `mongodb://localhost:27018` |
| Mongo Express (admin UI) | http://localhost:8081 |

> Make sure Docker Desktop is running before this step.

To stop the containers:
```bash
docker compose down
```

---

### 3. Run the Backend

```bash
cd backend
npm install
npm run dev
```

The Express API will be available at **http://localhost:3000** (or whichever port is set in your `.env`).

> Copy `.env.example` to `.env` and fill in your environment variables before starting.

```bash
cp .env.example .env
```

---

### 4. Run the Frontend

```bash
cd frontend
npm install
npm run dev
```

The React + Vite app will be available at **http://localhost:5173**.

> Set the backend API URL in your frontend `.env`:
> ```
> VITE_API_URL=http://localhost:3000
> ```

---

### 5. Run the Mobile App (Flutter)

```bash
cd mobile
flutter pub get
flutter run
```

> Make sure a device or emulator is running first. To list available devices:
> ```bash
> flutter devices
> ```

Update the API base URL in your Flutter project (typically in `lib/config/` or `lib/constants/`) to point to the running backend.

---

### 6. (Optional) Run the Novelty Layer

Refer to the `novelty/README.md` created by your team for setup instructions specific to your chosen technology.

---

## 🔄 Running Everything Together

For a typical development session, open **four terminals**:

| Terminal | Command |
|---|---|
| 1 — Infra | `cd infra && docker compose up -d` |
| 2 — Backend | `cd backend && npm run dev` |
| 3 — Frontend | `cd frontend && npm run dev` |
| 4 — Mobile | `cd mobile && flutter run` |

---

