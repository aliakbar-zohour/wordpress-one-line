# Simple WordPress with Docker

This project provides a simple Docker-based setup to run a full WordPress website locally using Docker Compose.

## 🚀 Features

- WordPress powered by the official `wordpress:latest` image
- MariaDB database (`mariadb:10.6.4-focal`)
- Data persistence using Docker volumes
- Quick and easy local development setup

## 🛠 Requirements

- [Docker](https://www.docker.com/products/docker-desktop)
- [Docker Compose](https://docs.docker.com/compose/install/)

## 📁 Project Structure

```
.
├── docker-compose.yml
└── README.md
```

## ⚙️ How to Use

1. **Clone the repository**

```bash
git clone https://github.com/aliakbar-zohour/wordpress-one-line.git
cd wordpress-one-line
```

2. **Start the services**

```bash
docker-compose up -d
```

3. **Access WordPress**

Open your browser and navigate to [http://localhost](http://localhost). You should see the WordPress installation page.

## 🧪 Services

### Database (MariaDB)

- Image: `mariadb:10.6.4-focal`
- Ports: `3306`, `33060` (internal only)
- Environment Variables:
  - `MYSQL_ROOT_PASSWORD=somewordpress`
  - `MYSQL_DATABASE=wordpress`
  - `MYSQL_USER=wordpress`
  - `MYSQL_PASSWORD=wordpress`

### WordPress

- Image: `wordpress:latest`
- Port: `80` (localhost)
- Environment Variables:
  - `WORDPRESS_DB_HOST=db`
  - `WORDPRESS_DB_USER=wordpress`
  - `WORDPRESS_DB_PASSWORD=wordpress`
  - `WORDPRESS_DB_NAME=wordpress`

## 💾 Data Persistence

The database data is stored in a Docker volume called `db_data`, ensuring data is not lost when containers are stopped.

## 🔄 Restart Policy

Both services have `restart: always` configured to ensure they are always running.

## 📌 Notes

- You can switch to MySQL by uncommenting the relevant line in the `docker-compose.yml` file.
- Make sure no other services are using port 80.

## 🧹 Stopping the Services

To stop and remove the containers:

```bash
docker-compose down
```

To stop and remove containers along with the volume:

```bash
docker-compose down -v
```

---

Enjoy your local WordPress development environment! 🎉
