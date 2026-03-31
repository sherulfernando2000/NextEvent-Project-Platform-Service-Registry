# Service-Registry

A service discovery server built on Netflix Eureka. All microservices register themselves here on startup, allowing the API Gateway and other services to locate them dynamically by name rather than hardcoded URLs.

## 👤 Student Information

- **Student Name:** Sherul Dhanushka Fernando
- **Student Number:** 2301691014
- **Slack Handle:** https://ijse-eca-hdse-69-70.slack.com/team/U0AEH8NS9DW
- **GCP Project ID:** project-0ae0d75b-3979-4ebf-be9

---

## 📝 ABOUT

The **Service-Registry** acts as the **"Directory"** of the NextEvent system.

Instead of using hardcoded IP addresses or ports, all services register here and communicate using service names.

This allows:

- Dynamic service discovery
- Loose coupling between microservices
- Easier scaling and load balancing

## Tech Stack

| Technology | Details |
|---|---|
| Java | 25 |
| Spring Boot | 4.0.3 |
| Spring Cloud | 2025.1.0 |
| Spring Cloud Netflix Eureka Server | Service discovery |
| Spring Cloud Config Client | Fetches config from Config-Server |

## How It Works

The Service-Registry acts as the central directory for the microservices architecture. When a service starts, it registers with this server. The API Gateway queries this registry to resolve service locations using load-balanced URIs (e.g., `lb://STUDENT-SERVICE`).

## Service Details

| Property | Value |
|---|---|
| Port | `9001` |
| Artifact ID | `Service-Registry` |
| Group ID | `lk.ijse.eca` |
| Config Source | `http://localhost:9000` (Config-Server) |

## Getting Started

Follow the lecture guidelines, refer to the lecture video for more information and how to get started correctly.

> **Important:** Config-Server must be running before starting the Service-Registry, as it fetches its configuration from Config-Server on startup.

**Startup order:**
1. Config-Server (`9000`)
2. **Service-Registry** (`9001`)
3. Other services...

```bash
./mvnw spring-boot:run
```

The Eureka dashboard will be available at: `http://localhost:9001`

## Need Help?

If you encounter any issues, feel free to reach out and start a discussion via the Slack workspace.
