# COSC 1301 — PostgreSQL + pgAdmin Codespace

This repository is a ready-to-run database environment for the Week 8 Database Lab and Project 3. Everything is pre-configured — you do not need to install anything locally.

## Getting Started

1. Click the green **Code** button on this repository → **Codespaces** tab → **Create codespace on main**.
2. Wait for the Codespace to build (1–2 minutes the first time).
3. A forwarded port for **pgAdmin** should open automatically. If it doesn't, go to the **Ports** tab at the bottom of the editor and click the globe icon next to port `8080`.
4. Log in to pgAdmin with:
   - **Email:** `student@cosc1301.local`
   - **Password:** `password`
5. In the left sidebar, expand **Servers → COSC 1301 Database**. It is already connected — no setup required. If prompted for a password, use `password`.

## Where Things Live

- `docker-compose.yml` — defines the PostgreSQL database and pgAdmin and connects them automatically.
- `.env` — environment variables (usernames, passwords, ports). You shouldn't need to edit this.
- `sample_data/ducks.csv` — the duck census dataset collected by your class in Week 7, used in the Database Lab.
- `.devcontainer/` — tells GitHub Codespaces how to launch this environment.

## Loading the Duck Data

Once connected in pgAdmin:

1. Right-click **Servers → COSC 1301 Database → Databases → cosc1301** → **Query Tool**.
2. Follow the CREATE TABLE instructions in the Database Lab to create the `ducks` table.
3. Right-click the `ducks` table → **Import/Export Data** → Import → select `sample_data/ducks.csv`.

## Using This for Project 3

Use this same environment for your Project 3 database. Create a new table inside the `cosc1301` database for your own personal topic — the same CREATE TABLE → import → query pattern from the lab applies directly to your own data.

## Troubleshooting

- **pgAdmin won't load:** Check the Ports tab — confirm port 8080 is forwarded. Try opening it in a new browser tab.
- **"Could not connect to server":** Wait 30 seconds after the Codespace finishes building — the database container sometimes needs a few extra seconds.
- **Codespace is slow:** GitHub Codespaces free tier has usage limits. If you run out of free hours, contact your instructor.
