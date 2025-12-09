# **Docker Fundamentals – Multi-Container Application (Using Docker Compose)**

This project demonstrates the use of **Docker Compose** to build and run a **multi-container application** consisting of:

* A **Flask web application**
* A **Redis database**
* An **Nginx reverse proxy**

The goal of this assignment is to show that multi-service applications can be orchestrated, networked, and managed easily using Docker Compose.

---

## **What This Project Does**

This project creates a simple web application where:

* A **Flask app** responds with a message and a visit counter
* The counter value is stored in **Redis**
* All incoming requests go through **Nginx**, which acts as a **reverse proxy** for the Flask app
* Docker Compose starts and manages all 3 services with a single command

This setup is commonly used in real-world production systems.

---

## **Project Structure**

```
.
├── app.py                # Flask application
├── requirements.txt      # Python dependencies
├── Dockerfile            # Builds the Flask app image
├── nginx.conf            # Reverse proxy configuration
└── docker-compose.yml    # Defines and runs all services
```

---

## **Technologies Used**

* **Docker**
* **Docker Compose**
* **Flask (Python)**
* **Redis**
* **Nginx**

---

## **⚙️ How It Works**

### **1.Flask Application**

The Flask app exposes a route (`/`) and connects to Redis.
Every time the page loads, Redis increments a counter and returns the number of visits.

### **2️.Redis**

Acts as an in-memory data store to track visits.

### **3.Nginx**

Handles all HTTP requests on port **80** and forwards them to the Flask app on port **5000**.

### **4.Docker Compose**

Orchestrates all 3 services and creates:

* A shared network
* Containers for each service
* Automatic service dependencies

---

## **How to Run the Application**

Run the command:

```
docker-compose up --build
```

This automatically builds the Flask image and starts:

* `web` (Nginx)
* `app` (Flask)
* `redis` (Redis)

Then visit:

 **[http://localhost](http://localhost)**

You will see the Flask response and the visit counter.

---

## **What This Demonstrates (Learning Outcomes)**

✔ Understanding of multi-container architecture
✔ Ability to configure and use Dockerfiles
✔ Use of Docker Compose for orchestration
✔ Networking between containers
✔ Connecting an application service to a database
✔ Using Nginx as a reverse proxy inside Docker

This assignment shows practical knowledge of containerized applications and service management using Docker tools.

---

## **Status**

The application is fully working:

* Containers build successfully
* All services start correctly
* Nginx routes traffic to Flask
* Redis stores counter values


