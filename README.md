# Docker Learning Repository 🚀

## Learn Docker with Examples!

Contributions are most welcome! If you find this repo useful, give it a ⭐️.

---

## 📌 What is a Container?

A **container** is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another. A **Docker container image** is a lightweight, standalone, executable package of software that includes everything needed to run an application: code, runtime, system tools, system libraries, and settings.

---

## 🆚 Containers vs Virtual Machines

| Feature           | Containers | Virtual Machines |
|------------------|------------|-----------------|
| **Resource Usage** | Shares OS kernel, lightweight | Requires full OS, heavy |
| **Portability**    | Highly portable | Needs hypervisor |
| **Security**      | Less isolated | More isolated due to separate OS |
| **Management**    | Easier & faster | More complex |

---

## 🤔 Why are Containers Lightweight?

Containers share the host OS kernel, unlike VMs, which require a full-fledged OS. This makes containers **smaller** and **faster**.

For example:
- **Ubuntu Docker base image**: ~22MB
- **Ubuntu VM image**: ~2.3GB (100x larger)

### 📁 Files and Folders in Container Base Images
```
/bin   - System binaries (ls, cp, ps, etc.)
/sbin  - System admin binaries (init, shutdown, etc.)
/etc   - Configuration files
/lib   - Library files
/usr   - User utilities, applications
/var   - Logs, spool files, temp data
/root  - Home directory of root user
```

### 🖥️ Files & Folders Used from Host OS
```
- Host file system (bind mounts)
- Networking stack
- System calls (via host kernel)
- Namespaces (isolation for resources)
- Control groups (cgroups for resource management)
```

---

## 🐳 Docker Overview

### 📌 What is Docker?
Docker is a **containerization platform** that makes it easy to package, deploy, and manage applications in containers. It helps build, run, and share containerized apps efficiently.

### 🏗️ Docker Architecture

![Docker Architecture](https://user-images.githubusercontent.com/43399466/217507877-212d3a60-143a-4a1d-ab79-4bb615cb4622.png)

- **Docker Daemon**: The brain of Docker, managing images, containers, networks, and more.
- **Docker Client**: Interacts with the daemon via CLI commands.
- **Docker Registries**: Store and distribute images (e.g., Docker Hub).

### 🔄 Docker Lifecycle
1. `docker build` → Builds a Docker image from a Dockerfile.
2. `docker run` → Runs a container from the image.
3. `docker push` → Pushes the image to a registry.

![Docker Lifecycle](https://user-images.githubusercontent.com/43399466/217511949-81f897b2-70ee-41d1-b229-38d0572c54c7.png)

---

## 🛠️ Install Docker

### 📥 Installation
Refer to the official Docker docs for detailed installation steps:
👉 [Install Docker](https://docs.docker.com/get-docker/)

For a quick setup on **Ubuntu (AWS EC2)**:
```sh
sudo apt update
sudo apt install docker.io -y
```

### ✅ Verify Installation
```sh
docker run hello-world
```
If you see **permission denied**, you might need to:
```sh
sudo systemctl start docker
sudo usermod -aG docker $USER
```
Then **logout & login** again!

---

## 🚀 Build & Run Your First Docker Image

### 🛠️ Clone Repository
```sh
git clone https://github.com/she0407
cd examples
```

### 🔐 Login to Docker Hub
```sh
docker login
```

### 🏗️ Build an Image
```sh
docker build -t she4/my-first-docker-image:latest .
```

### 📂 Verify the Image
```sh
docker images
```
Expected output:
```
REPOSITORY                      TAG       IMAGE ID        CREATED         SIZE
she4/my-first-docker-image   latest    960d37536dcd   A few seconds ago   467MB
```

### ▶️ Run a Container
```sh
docker run -it she4/my-first-docker-image
```
Expected output:
```
Hello World
```

### 📤 Push the Image to Docker Hub
```sh
docker push she4/my-first-docker-image
```

---

## 🎉 Congratulations! You’ve Successfully Built & Deployed a Docker Image!

Happy Learning! 🚀 If you found this useful, don't forget to **STAR** ⭐ the repo!

📌 **Next Steps:** Continue with the `examples` folder and explore more Docker concepts! 🎯
