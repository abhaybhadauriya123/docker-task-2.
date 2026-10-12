# Docker Task-2: Personal Details Website

## Objective
Build a simple website that displays basic profile details using a Dockerfile and Docker Compose, then run it on AWS EC2.

## Files
- `index.html` — website content and styling
- `Dockerfile` — builds an Nginx image containing the website
- `docker-compose.yml` — builds and runs the website container
- `screenshots/` — add actual screenshots from your EC2 terminal and browser

## Before running
Edit `index.html` and replace `Your Name` and the sample profile details with the details you want to publish. Do not add passwords, private contact details, or confidential information.

## Run on Ubuntu EC2
Install Docker and the Compose plugin if they are not already installed:

```bash
sudo apt update
sudo apt install docker.io docker-compose-v2 -y
sudo systemctl enable --now docker
```

From the project directory, build and start the website:

```bash
sudo docker compose up -d --build
sudo docker compose ps
sudo docker images
sudo docker logs docker-task-2-profile
```

Test locally on the EC2 instance:

```bash
curl http://localhost:8080
```

## Open the website in a browser
To view it from your own computer, add an inbound rule for TCP port `8080` to the EC2 security group, with **Source = My IP** only. Then open:

`http://EC2-PUBLIC-IP:8080`

Replace `EC2-PUBLIC-IP` with the instance's public IPv4 address. Do not open the port to `0.0.0.0/0` for this assessment. Remove the inbound rule when you finish if public access is no longer needed.

## Useful commands
```bash
sudo docker compose ps
sudo docker compose logs
sudo docker compose down
sudo docker compose up -d --build
```

## Screenshots to add
1. `screenshots/01-project-files.png` — project files visible.
2. `screenshots/02-docker-build.png` — successful `docker compose up -d --build`.
3. `screenshots/03-container-running.png` — `sudo docker compose ps`.
4. `screenshots/04-website-browser.png` — personal website open in browser.
5. `screenshots/05-curl-output.png` — `curl http://localhost:8080` output.

Only add real screenshots from your own environment. Never include passwords, SSH private keys, access tokens, or confidential information.
