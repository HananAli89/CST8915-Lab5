# CST8915 Lab 5 – Containerizing the Algonquin Pet Store

**Student:** Hanan Ali

**Student ID**: 041153451

**Course**: CST8915 Full-stack Cloud-native Development

**Semester**: Fall 2026

## Demo Video

🎥 [Watch Demo Video](https://youtu.be/PUJkrV53Le8)

## Service Repositories (Forks)

| Service | Repository |
| --- | --- |
| Order Service (Node.js) | https://github.com/HananAli89/order-service-L4 |
| Product Service (Python) | https://github.com/HananAli89/product-service-python-L4 |
| Store Front (Vue + Nginx) | https://github.com/HananAli89/store-front-L4 |

Each fork contains the Dockerfile used to build its image.

## Docker Hub Images

| Image | Link |
| --- | --- |
| `hananali89/order-service:latest` | https://hub.docker.com/r/hananali89/order-service |
| `hananali89/product-service:latest` | https://hub.docker.com/r/hananali89/product-service |
| `hananali89/store-front:latest` | https://hub.docker.com/r/hananali89/store-front |

## Deployment Details

- **Product Service implementation:** Python (Flask)
- **API host embedded in the Store Front image:** `localhost`
  - Order Service: `http://localhost:3000`
  - Product Service: `http://localhost:3030`
- The stack was run locally with Docker Desktop, so the browser reaches both APIs through `localhost`.


## Setup Challenges and Lessons Learned

- **Docker Desktop installation:** The first install failed because the Windows "Virtual Machine Platform" feature was not enabled. Running `wsl --install --no-distribution` in an administrator PowerShell and restarting resolved it.
- **Build context:** I initially built the Product Service image from the Order Service folder, so the image contained the wrong code. Rebuilding from the correct folder fixed it and showed that the build context (`.`) determines what goes into the image.
