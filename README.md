# Wazuh Manager Installation Automation

This C++ program automates the installation of Wazuh Manager on an Ubuntu server. It starts by updating and upgrading the system, then proceeds with adding the Wazuh repository, installing the necessary dependencies, and setting up the Wazuh Manager service.

## Prerequisites

- Ubuntu server (e.g., AWS EC2 instance)
- Root or sudo privileges
- Internet connection for downloading packages
- C++ compiler (g++) installed on the server

## Installation

1. Transfer the `install_wazuh.cpp` file to your Ubuntu server.
2. If not already installed, install g++:
   ```
   sudo apt update
   sudo apt install -y g++
   ```
3. Compile the program:
   ```
   g++ install_wazuh.cpp -o install_wazuh
   ```

## Usage

Run the compiled program with sudo privileges:
```
sudo ./install_wazuh
```

The program will execute the following steps:
- Update package list
- Upgrade the system
- Install dependencies (curl, gnupg, apt-transport-https)
- Add Wazuh GPG key
- Add Wazuh repository
- Update package list again
- Install Wazuh Manager
- Enable and start the Wazuh Manager service

Output will be displayed for each step. If any step fails, the program will exit with an error.

## Notes

- This program installs only the Wazuh Manager component. For a complete Wazuh setup, you may need to install additional components like the Wazuh Indexer and Dashboard.
- Ensure your system meets the hardware and software requirements for Wazuh as outlined in the official documentation.
- The program uses the latest stable 4.x version of Wazuh packages.

## License

This project is provided as-is for educational and automation purposes. Refer to Wazuh's licensing for the installed software.