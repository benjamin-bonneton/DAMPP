# DAMPP

**DAMPP** (Dockerized Apache, MariaDB, PHP & PHPMyAdmin) is a lightweight, easy-to-use local development environment powered by Docker. 

It bundles the essential components for web development—Apache, MariaDB, PHP, and PHPMyAdmin—making it simple to start building and testing PHP applications on your machine.

## Features

- **Apache** (2.4.62): Robust web server for serving your PHP applications.
- **MariaDB** (10.4.32): Reliable MySQL-compatible database.
- **PHP** (8.2.12): Modern PHP runtime for your web projects.
- **PHPMyAdmin** (5.2.1): Web-based database management interface.
- **Dashboard**: Simple dashboard for quick access and documentation.
- **Easy Configuration**: Change ports, memory limits, and credentials via the `.env` file.
- **Volume Mapping**: Persist your web files and database data outside the containers.

## Installing Docker and Docker Compose

Before using DAMPP, make sure you have **Docker** and **Docker Compose** installed on your machine.

- **Windows / macOS:**  
   Download and install [Docker Desktop](https://www.docker.com/products/docker-desktop/) (includes Docker Compose).

- **Linux:**
   ```sh
   sudo apt-get install docker-compose-v2
   ```

Verify the installation with:
```sh
docker --version
```
```sh
docker compose version
```

## Quick Start

1. **Clone the repository:**
   ```sh
   git clone https://github.com/benjamin-bonneton/DAMPP.git
   cd DAMPP
   ```

2. **Configure environment variables (optional):**
   - Edit the `.env` file to adjust ports, memory limits, and credentials as needed.

3. **Start the stack:**
   ```sh
   docker compose up -d
   ```

4. **Access your services:**
   - **Local website:** [http://localhost](http://localhost)
   - **PHPMyAdmin:** [http://localhost:8080](http://localhost:8080)
   - **Dashboard:** [http://localhost:8081](http://localhost:8081)

## Folder Structure

- `www/` — Place your PHP/web files here. Served at [http://localhost](http://localhost).
- `database/` — MariaDB data is stored here (persistent).
- `config/` — Docker and service configuration files.
- `dashboard/` — Dashboard web files.

## Default Credentials

- **MariaDB**
  - Host: `DAMPP_db`
  - Port: `3306`
  - User: `root`
  - Password: `root` (or as set in `.env`)
- **PHPMyAdmin**
  - Connects automatically using MariaDB credentials.

## Configuration

Edit the `.env` file to change:

- Service ports (e.g., `WEB_PORT`, `DB_PANEL_PORT`)
- Memory limits for each service
- Database credentials

## Stopping and Removing

To stop the containers:
```sh
docker compose down
```

To remove all data (including databases), delete the `database/` folder.

## Troubleshooting

- Make sure Docker is installed and running.
- If ports are already in use, change them in the `.env` file.
- For PHP configuration details, visit [http://localhost/php](http://localhost/php) (if available).

## Credits

- Project by [Benjamin Bonneton](https://benjamin-bonneton.com)
- Source: [GitHub - DAMPP](https://github.com/benjamin-bonneton/DAMPP)

## License

MIT License. See [LICENSE](LICENSE) for details.
