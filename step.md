


# Docker Setup for Ubuntu 24.04

## 1. System Update
Before starting the Docker installation, it's recommended to update your system to the latest packages:

```bash
sudo apt update && sudo apt upgrade -y
```


## 2. Install Dependencies
Install necessary packages for Docker installation:

```bash
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common
```


![image](https://github.com/user-attachments/assets/9ebabedd-6ca4-45c3-937f-2309dcc48a73)


## 3. Add Docker GPG Key
Add Docker's official GPG key to authenticate packages:

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```


## 4. Add Docker Repository
Add the Docker repository to your system’s APT sources list:

```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```


![image](https://github.com/user-attachments/assets/c91d78b1-7a06-482e-8aa9-005a65b8777a)

## 5. Install Docker
Install Docker using the following command:

```bash
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io
```

![image](https://github.com/user-attachments/assets/3ae954a6-4280-49df-9e28-733c02ac70b2)
![image](https://github.com/user-attachments/assets/fd5c0983-3250-4468-9ea1-ab20a0469706)



## 6. Verify Installation
Check if Docker is installed successfully by verifying the version:

```bash
docker --version
```
![image](https://github.com/user-attachments/assets/10014865-6035-48d8-b0ff-0ace01f18eda)


## 7. Optional: Run Docker as Non-Root User
To allow running Docker commands without `sudo`:

1. Add your user to the Docker group:

    ```bash
    sudo usermod -aG docker $USER
    ```

2. Log out and log back in, or use:

    ```bash
    newgrp docker
    ```

3. Test Docker by running a test container:

    ```bash
    docker run hello-world
    ```



## 8. Enable Docker on Boot
Ensure Docker starts automatically when the system boots:

```bash
sudo systemctl enable docker
sudo systemctl start docker
```



## 9. Final Test
Verify everything is working correctly by running the following command:

```bash
docker run hello-world
```


Now Docker should be installed and running on your Ubuntu 24.04 system.
