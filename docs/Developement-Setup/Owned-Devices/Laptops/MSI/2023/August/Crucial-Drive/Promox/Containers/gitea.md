# Gitea Installation and Post-Installation Guide

## Introduction

Welcome to the comprehensive guide for installing and configuring Gitea, a self-hosted Git service, on a Linux system. This process is divided into two main steps: Preparation (STEP-1.sh) and Post Installation (Step2.sh).

### STEP-1.sh - Preparation

This script ensures your system is ready for a seamless Gitea installation. Follow these steps:

1. **Update System:** Ensure your system is up-to-date by running:
   ```bash
   apt update
   apt install vim
   ```

2. **Install Gitea:** Download and make the [Gitea binary](https://raw.githubusercontent.com/rohanbatrain/scripts/main/Containers/gitea/Step-1.sh) executable.
   ```bash
   wget -O gitea https://dl.gitea.com/gitea/1.21.3/gitea-1.21.3-linux-amd64
   chmod +x gitea
   ```

3. **Create Gitea User:** Add a system user named "git" for running Gitea.
   ```bash
   adduser \
      --system \
      --shell /bin/bash \
      --gecos 'Git Version Control' \
      --group \
      --disabled-password \
      --home /home/git \
      git
   ```

4. **Configure Directories:** Set up the necessary directory structure for Gitea.
   ```bash
   mkdir -p /var/lib/gitea/{custom,data,log}
   chown -R git:git /var/lib/gitea/
   chmod -R 750 /var/lib/gitea/
   mkdir /etc/gitea
   chown root:git /etc/gitea
   chmod 770 /etc/gitea
   ```

5. **Configure Working Directory:** Define the Gitea working directory.
   ```bash
   export GITEA_WORK_DIR=/var/lib/gitea/
   ```

6. **Copy Binary:** Copy the Gitea binary to a global location.
   ```bash
   cp gitea /usr/local/bin/gitea
   ```

7. **Run Gitea as a Service:** Configure Gitea to run as a Linux service.
   ```bash
   wget https://raw.githubusercontent.com/go-gitea/gitea/release/v1.21/contrib/systemd/gitea.service -O /etc/systemd/system/gitea.service
   systemctl enable gitea --now
   ```

8. **Reboot System:** Restart the system.
   ```bash
   systemctl reboot
   ```

### Step2.sh - Post Installation

After the system restarts, execute Step2.sh for post-installation tasks:

1. **Set Permissions:** Adjust permissions for Gitea configuration files to enhance security.
   ```bash
   chmod 750 /etc/gitea
   chmod 640 /etc/gitea/app.ini
   ```

## Usage

1. Execute [STEP-1.sh](https://raw.githubusercontent.com/rohanbatrain/scripts/main/Containers/gitea/Step-1.sh) to prepare the system for Gitea installation.
2. After the system reboots, run [Step-2.sh](https://raw.githubusercontent.com/rohanbatrain/scripts/main/Containers/gitea/Step-2.sh) for post-installation tasks.

## Conclusion

Following these detailed steps ensures a successful installation and configuration of Gitea on your Linux system. For additional configuration options and advanced settings, refer to the [official Gitea documentation](https://docs.gitea.io/en-us/). Happy coding!
