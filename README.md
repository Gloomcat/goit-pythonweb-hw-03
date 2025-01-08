# Project Setup Instructions

This guide will walk you through setting up the project in a virtual environment (venv), installing the necessary dependencies, and running the application using Docker. The application will be accessible at **http://127.0.0.1:3000**.

---

## 🛠️ Prerequisites

Make sure you have the following installed on your machine:
- **Python 3.10+**
- **pip** (Python package manager)
- **Docker**
- **Docker Compose**

---

## 🚀 Step 1: Set Up a Virtual Environment

It's recommended to set up a **virtual environment** to manage your Python dependencies.

```bash
# Go to directory with cloned project
cd <your-cloned-project-path>

# Create a virtual environment
python -m venv .venv

# Activate the virtual environment
# On Windows
.venv\Scripts\activate.ps1

# On macOS/Linux
source .venv/bin/activate
```

Once the virtual environment is activated, your shell prompt will change to indicate that you are now working within the venv.

---

## 📦 Step 2: Install Dependencies

With the virtual environment activated, install the dependencies listed in the **`requirements.txt`** file:

```bash
pip install -r requirements.txt
```

---

### **Run the Application locally with Python**

With the virtual environment activated, run command:

```bash
python main.py
```

---

### **Run the Application with Docker Compose**

```bash
docker-compose up --build
```

This will build and run the application, mapping port **3000** on your host machine to **port 3000** inside the container.

To stop the application, run:

```bash
docker-compose down
```

---

## 🧪 Step 3: Verify the Setup

After running the container, open your browser and navigate to:

```
http://127.0.0.1:3000
```

You should see the application running.

---

## 📁 Persistent Storage with Docker Volumes

The **`storage/`** folder is mapped to a Docker volume to persist data even if the container is stopped or removed. Any changes to **`storage/`** folder files on your host machine will be reflected inside the Docker container.

### Verify the Volume Mapping:

Run the following command to inspect the container's volume:

```bash
docker inspect <your-container-name>
```

Look for the **`Mounts`** section to verify that **`storage/`** is correctly mapped.

---

## 📚 Additional Notes

- **Bootstrap** is used for styling the front-end templates.
- Ensure you have proper permissions to run Docker on your system.
