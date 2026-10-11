# CCM101 Enterprise Cloud Architect

## Project Title

Secure Multi-Tier Web Application

## Application Stack

WordPress + MySQL

## Group Members

- ACERIT, SUZANNE P.
- ESTIBAR, JOHN DARYL T.
- JAVONILLO, KYRA NICOLE V.
- SALCEDO, KRISTINE C.

## Project Description

This project deploys a secure and persistent multi-tier web application. WordPress is the web tier and MySQL is the database tier. Both run as Docker containers, managed with Docker Compose, on an Ubuntu Server virtual machine in VirtualBox. The VM files and a separate backup disk are stored on an external drive.

## Technologies Used

- Windows 11 host with Oracle VirtualBox (Type 2 hypervisor)
- Ubuntu Server 26.04 LTS
- Docker and Docker Compose
- WordPress and MySQL 8.0
- UFW firewall
- Bash and Cron
- GitHub and draw.io

## Containers

| Container | Image | Role |
| --- | --- | --- |
| ccm101-wordpress | wordpress:latest | Web application, publishes port 80 |
| ccm101-mysql | mysql:8.0 | Database, no published port |

## Persistent Storage

Two Docker volumes keep the data outside the containers.

| Volume | Holds |
| --- | --- |
| wordpress_data | WordPress files, themes, and uploads |
| db_data | MySQL database files |

The data survives container removal and VM reboots.

## Security

- UFW is enabled with a default deny policy for incoming traffic.
- Only 22/tcp (SSH) and 80/tcp (HTTP) are allowed.
- MySQL port 3306 is not published, so the database is only reachable inside the Docker network.
- Passwords are kept in a local `.env` file that is never committed. Only `.env.example` is in the repository.

## Automation

`automation-script.sh` backs up the WordPress database with `mysqldump`. It saves to the backup disk mounted at `/mnt/ssd-backup`, deletes backups older than 7 days, and writes a log line. Cron runs it every day at 11 PM.

```
0 23 * * * /home/estibargroup/ccm101-final/automation-script.sh >> /home/estibargroup/cron.log 2>&1
```

## Files

| File | Purpose |
| --- | --- |
| README.md | This overview |
| architecture-diagram.png | Topology of host, hypervisor, VM, firewall, and containers |
| docker-compose.yml | WordPress and MySQL stack |
| automation-script.sh | Database backup script |
| operational-manual.md | Deploy, secure, and maintain the stack |
| final-reflection.md | Reflection from Mission 1 to Mission 10 |
