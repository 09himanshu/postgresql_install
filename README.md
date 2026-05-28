# PostgreSQL Install On Ubuntu

```bash
sudo apt update
sudo apt install postgresql postgresql-contrib -y
sudo service postgresql start
```

## Create DBS
```bash
sudo -u postgres psql
```
After the prompt, paste the code below

```bash
CREATE DATABASE <database_name>;
CREATE DATABASE <database_name>;
CREATE USER <username> WITH PASSWORD <password>;
GRANT ALL PRIVILEGES ON DATABASE <database_name> TO <username>;
GRANT ALL PRIVILEGES ON DATABASE <database_name> TO <username>;
\q
```

## Install extension on VS Code 
```
1. SQLTool and SQLTools 
2. PostgreSQL/Cockroach Driver
```

## Connect to SQLTool
```bash
Connection Name: <coonection name>
Host: <localhost/VM IP>
Port: 5432
Database: <database_name>
Username: <username>
Password: <password>
```

## Project folder

```bash
mkdir dental-service && cd dental-service
npm init -y
```

## Install dependencies

```bash
npm install express pg uuid winston winston-daily-rotate-file dotenv
```

## Setup folder structure

```bash
mkdir -p src/config src/middleware src/routes src/logger logs
touch src/config/db.js
touch src/middleware/requestId.js
touch src/middleware/tenantRouter.js
touch src/middleware/requestLogger.js
touch src/routes/patients.js
touch src/routes/appointments.js
touch src/routes/health.js
touch src/logger/index.js
touch src/app.js
touch setup.sql
touch seed.js
touch .env
touch .env.example
```
## Run this to grant permission

```bash
sudo -u postgres psql -d practice_a_db -c "GRANT ALL ON SCHEMA public TO devuser; ALTER DATABASE practice_a_db OWNER TO devuser;"

sudo -u postgres psql -d practice_b_db -c "GRANT ALL ON SCHEMA public TO devuser; ALTER DATABASE practice_b_db OWNER TO devuser;"
```

## run setup.sql

```bash
psql -U devuser -d practice_a_db -f setup.sql
psql -U devuser -d practice_b_db -f setup.sql
```
