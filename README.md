<div align='center'>
 <img style="width:100%" src="https://capsule-render.vercel.app/api?type=soft&height=200&color=FFFFFF&text=Python%20Django%20PostgreSQL%20Docker&fontSize=50&fontAlign=50&strokeWidth=0&descAlignY=80&stroke=000000">
</div>

<nav align="center">
  <h2>🔗 NAVIGATION </h2>
  <p>
   <a href="#about-this-project">ABOUT THIS PROJECT</a> |
   <a href="#setup">SETUP</a> |
   <a href="#running-the-application">RUNNING THE APPLICATION</a> |
   <a href="#final-considerations">FINAL CONSIDERATIONS</a>
  </p>
</nav>

## ABOUT THIS PROJECT

This project is a **full Python Django + PostgreSQL web application environment** configured using **Docker**.

It already contains the complete Django project structure and PostgreSQL database with a user created, ready to run without recreating the project from scratch.

## SETUP

### PREREQUISITES

* Docker Desktop installed (Linux containers mode)
* Docker Compose
* Project cloned locally
* PostgreSQL user and database already configured

### STARTING THE CONTAINERS

From the project directory, run:

```bash
docker-compose up -d --build
```

This will:

* Build the Docker images (Python/Django and PostgreSQL) if not already present
* Create and start the containers

## RUNNING THE APPLICATION

If the project already has the user and database set up, simply run:

```bash
docker-compose exec web python manage.py runserver 0.0.0.0:8000
```

The application will be accessible at:

```
http://localhost:8000
```

### IF IT DOESN’T RUN IMMEDIATELY

If there’s an issue, follow these steps:

1. Check that containers are running:

```bash
docker ps
```

2. Run migrations (if needed):

```bash
docker-compose exec web python manage.py migrate
```

3. Create a superuser (admin) if necessary:

```bash
docker-compose exec web python manage.py createsuperuser
```

4. Finally, run the Django server again:

```bash
docker-compose exec web python manage.py runserver 0.0.0.0:8000
```

## FINAL CONSIDERATIONS

This Docker setup allows you to:

* Run Django and PostgreSQL without installing anything locally other than Docker
* Ensure consistent behavior across any machine
* Simplify development, testing, and deployment

<p><strong>© 2025 EltonRuan. All rights reserved.</strong></p>

<footer align="center">
 <img style="width:100%" src="https://capsule-render.vercel.app/api?type=soft&height=20&color=FFFFFF&fontSize=50&fontAlign=50&strokeWidth=0&descAlignY=80&stroke=000000&reversal=false&section=footer">
</footer>
