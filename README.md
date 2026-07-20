# MongoDB Atlas NoSQL Lab

Task 2 implementation using MongoDB Atlas, Python, pandas and PyMongo.

## MongoDB Task 2

The assignment-ready implementation is in `MongoDB.ipynb`. It demonstrates:

- a secure Python connection to MongoDB Atlas;
- CSV migration from `pokemon_data.csv` with pandas and PyMongo;
- repeatable imports using a unique index and bulk upserts;
- flexible-schema documents containing missing, extra, array, Boolean, and nested fields;
- find, filter, projection, update, delete, count, and verification operations.

## Setup

Create and activate a virtual environment in PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

Create a private `.env` file from the provided template:

```powershell
Copy-Item .env.example .env
```

Open `.env` and replace the placeholder value with the Atlas connection string:

```env
MONGODB_URI=mongodb+srv://USERNAME:PASSWORD@CLUSTER.mongodb.net/?retryWrites=true&w=majority&appName=Cluster0
```

The notebook loads this file with `python-dotenv`. The real `.env` is excluded by `.gitignore` and must never be committed.

Start Jupyter:

```powershell
python -m notebook MongoDB.ipynb
```

Run the notebook from top to bottom. The import uses `pokedex_number` as a unique identifier, so rerunning it updates existing Pokémon instead of inserting duplicates.

## Atlas preparation

1. Create or select an Atlas cluster.
2. Create a database user with the permissions required for the lab.
3. Add the current client IP address under Network Access.
4. Copy the Python driver connection string and store it in `MONGODB_URI`.
5. Never commit the real connection string or include it in screenshots.

The notebook uses database `bde` and collection `pokemon`.

## Evidence for submission

Capture screenshots of:

- the running Atlas cluster;
- the successful `ping` output;
- the `bde.pokemon` collection in Data Explorer;
- imported Pokémon and flexible-schema documents;
- concise outputs for find, projection, update, and delete operations.

Crop all screenshots so they do not expose credentials, connection strings, or sensitive network information.

## Security

`.env`, private keys, virtual environments, Jupyter checkpoints, caches, and editor files are excluded through `.gitignore`. `.env.example` contains placeholders only.
