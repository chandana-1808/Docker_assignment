#  ELK Stack (Elasticsearch + Filebeat + Kibana) with Nginx Monitoring

##  Project Overview

This project demonstrates centralized log collection and visualization using the ELK Stack.

The stack includes:

- **Nginx** – Web server generating access and error logs
- **Filebeat** – Log shipper that forwards logs to Elasticsearch
- **Elasticsearch** – Stores and indexes log data
- **Kibana** – Visualizes and analyzes logs

The entire setup is containerized using Docker Compose.

---

##  Architecture

Nginx → Filebeat → Elasticsearch → Kibana

1. Nginx generates access and error logs.
2. Logs are written to a directory mapped to a local Docker volume.
3. Filebeat reads logs from that volume.
4. Filebeat sends logs to Elasticsearch (`filebeat-*` data stream).
5. Kibana visualizes logs using Discover and Data Views.

---
## How to run the project
Start the stack
docker compose up -d --build
docker compose ps

## Accessing the Services
Service	URL
Nginx	http://localhost

Kibana	http://localhost:5601

Elasticsearch	http://localhost:9200

##  Kibana Login Credentials

Username: elastic

Password: changeme%

## Viewing Logs in Kibana

Open http://localhost:5601

Go to Stack Management

Click Data Views

Create a new data view:

Index pattern: filebeat-*

Time field: @timestamp

Go to Discover

View Nginx access logs

## Log entry
<img width="1920" height="1080" alt="Screenshot from 2026-02-24 22-20-18" src="https://github.com/user-attachments/assets/20883140-32a5-41b1-9c15-9d009037493a" />

<img width="1920" height="1080" alt="Screenshot from 2026-02-24 22-23-58" src="https://github.com/user-attachments/assets/ba2ed5d3-987e-4a02-91be-6ae76ec0cce0" />

<img width="1690" height="822" alt="Screenshot from 2026-02-24 22-29-33" src="https://github.com/user-attachments/assets/8c337b57-3da8-4a67-9b93-e1e7a50d148c" />




