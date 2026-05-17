# Utilities

This repository contains helper tools for the project, primarily a **Docker Compose setup** for running the Frontend (FE) and Backend (BE) locally.

It allows you to quickly spin up both services in containers, with the FE proxying API requests to the BE.

---

## Project Structure


1. This repo with docker-compose.yml and instructions
2. Frontend FE repo
3. Backend BE repo

**Note:** The FE and BE repositories should be cloned **next to this repo inside a shared directory**, not inside it.

---

## Prerequisites

- [Docker](https://www.docker.com/) installed
- [Docker Compose](https://docs.docker.com/compose/) installed
- Ports **3001**, **5000**, and **5433** free on your machine

---

## Setup Instructions

1. Clone this repo:

```bash
git clone <utilities_repo_url>
cd Utilities
```
2. Clone the Frontend and Backend repos next to this folder:
```bash
git clone <FE_repo_url> ../FE
git clone <BE_repo_url> ../BE
```
3. Run Docker Compose:
```bash
docker compose up --build
```
4. Open your browser:

Frontend (FE): http://localhost:3001/

Backend (BE): http://localhost:5000/

Note: The backend requires a Finnhub API key. Create a `.env` file in this `Utilities` folder with the following content before running `docker compose up`:

```
FINNHUB_API_KEY=your_finnhub_api_key_here
```

## Notes

The FE uses nginx and proxies /api/ requests to the backend container.

Use `docker compose down` to stop the containers.

Rebuild containers after code changes with:

```bash
docker compose up --build
```