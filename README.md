# COSC 1301 — PostgreSQL Codespace

This repository is a ready-to-run database environment for the Week 8 Database Lab and Project 3. Everything is pre-configured — you do not need to install anything locally.

## Getting Started

1. Click the green **Code** button on this repository → **Codespaces** tab → **Create codespace on main**.
2. Wait for the Codespace to build (1–5 minutes the first time).
3. You can interact with the database using the terminal or the pre-configured PostgreSQL VS Code extension.

## Connecting via Terminal (psql)

Open a new terminal in VS Code and run the following command to connect to the database:

```bash
psql -h localhost -U postgres
```

## Connecting via PostgreSQL VS Code Extension

This workspace is pre-configured with connection details for the PostgreSQL extension.

1. Click the **PostgreSQL** icon (elephant) in the left Activity Bar of VS Code.
2. From there, you should see the local server connection listed.
3. Click the connection to expand it and connect, then click on the Databases folder.
4. Right-click on the `class` database, then select **New Query** to write and execute SQL commands.

## Where Things Live

- `docker-compose.yml` --- defines the PostgreSQL database container.
- `.env` --- the environment variables (usernames, passwords). You shouldn't need to edit this.
- `sample_data/ducks.csv` --- the duck census dataset collected by the class in Week 07.
- `.devcontainer/` --- tells GitHub Codespaces how to launch the environment.
- `.vscode/` --- specific VS Code pre-defined settings.

## Loading the Duck Data

Using the terminal (`psql`):

1. Connect to the database using the `psql` command detailed above.
2. Follow the CREATE TABLE instructions in the Database Lab to execute the scheme for the `ducks` table.
3. Import the CSV data by running the following command:
```SQL
\copy ducks FROM 'sample_data/ducks.csv' WITH (FORMAT csv, HEADER true);
```

## Using This Repo for Project 3

You can use this same environment for your Project 3 database. Just create a new table inside the `class` database for your own personal topic --- the same CREATE TABLE -> import -> query pattern from the lab applies to your own data.

## Troubleshooting
- **Codespace is slow:** GitHub Codespaces free tier has usage limits. If you run out of free hours, contact me.