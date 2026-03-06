# nuScenes DB Tool

nuScenes DB Tool is a Python application for loading, managing, and querying the nuScenes dataset using PostgreSQL.  

It provides a graphical interface, a REST API, and supporting scripts for working with nuScenes data in a structured database form.

The project is intended for dataset inspection, preprocessing, and experimentation rather than production deployment.

## Overview

The tool consists of three main parts:

• A desktop GUI for database interaction  
• A REST API implemented with FastAPI for programmatic access  
• A PostgreSQL schema designed around the nuScenes dataset  

## Installation

### Option 1: Executable

Download the latest executable release and run it directly:

https://github.com/erdemonal/nuScenes-Toolkit/releases/tag/exe-release

No Python installation is required for this option.

### Option 2: Docker

Clone the repository:

```bash
git clone https://github.com/erdemonal/nuScenes-Toolkit.git
cd nuScenes-Toolkit
```

Create a .env file:

```env
DB_HOST=host.docker.internal
DB_PORT=5432
DB_NAME=nuscenes_db
DB_USER=postgres
DB_PASSWORD=yourpassword
NUSCENES_DATAROOT=/path/to/nuscenes
SQL_FILE_PATH=/path/to/nuScene.sql
```

Build and start the containers:

```bash
make start-fresh
```

The API documentation will be available at:

http://127.0.0.1:8000/docs

### Option 3: Manual Setup

Clone the repository:
```bash
git clone https://github.com/erdemonal/nuScenes-Toolkit.git
cd nuScenes-Toolkit
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the application:

```bash
python nuscenetool.py
```

## Usage

After launching the application, connect to a PostgreSQL database by providing the host, port, database name, user, and password.

Once connected, database tables can be selected and inspected through the interface.

Records can be inserted, updated, or deleted directly from the table view.
CSV files can be imported into existing tables, and query results or full tables can be exported as CSV or SQL dumps.

A SQL query tool allows execution of arbitrary queries against the database.

## API

The FastAPI service exposes endpoints for accessing nuScenes data stored in PostgreSQL.

Interactive API documentation is available at:

http://127.0.0.1:8000/docs
