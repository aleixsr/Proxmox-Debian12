[![Version](https://img.shields.io/badge/Version-1.0.1-red.svg)](version) [![License](https://img.shields.io/badge/License-BSD--Clause_3-green.svg)](LICENSE) [![Readme em Português e Inglês](https://img.shields.io/badge/README-en%2Fpt--br-blue)](#)

```bash
                                                                  _               
             _ __  _ __ _____  ___ __ ___   _____  __    ___  ___| |_ _   _ _ __  
            | '_ \| '__/ _ \ \/ / '_ ` _ \ / _ \ \/ /   / __|/ _ \ __| | | | '_ \ 
            | |_) | | | (_) >  <| | | | | | (_) >  <    \__ \  __/ |_| |_| | |_) |
            | .__/|_|  \___/_/\_\_| |_| |_|\___/_/\_\___|___/\___|\__|\__,_| .__/ 
            |_|                                    |_____|                 |_|     v1.0.1  
```

[![Language](https://img.shields.io/badge/🌎-English:-blue)](#)

# Proxmox VE Installer on Debian 12 Bookworm

This setup/script automates the installation of Proxmox on Debian 12 and the creation of a bridge to facilitate network configuration.

**Note: This script is designed to run on a Debian 12 system. Make sure to have superuser permissions before executing the script.**

## Requirements

- Installed Debian 12 Bookworm

- Superuser permissions
  
  ```bash
  su root
  ```

- Installed Git
  
  ```bash
  apt update && apt upgrade && apt install -y git
  ```

- (Important) Clone the repository from the directory:
  
  ```bash
   cd /
  ```

## Usage Instructions

1. Clone the repository to your Debian 12 system.
   
   ```bash
   # With git already installed on your machine, clone the repository
   git clone https://github.com/aleixsr/Proxmox-Debian12.git
   ```

2. Access the downloaded folder with the 'cd' command
   
   ```bash
   cd /Proxmox-Debian12
   ```

3. Make the script executable.
   
   ```bash
   # Give execution permission to the setup
   chmod +x ./setup
   ```

4. Run the setup.
   
   ```bash
   ./setup
   ```

5. **Grub Update**: Keep grub file when asked (do not modify)

6. **Postfix**: Select Internet Site when asked

7. Follow screen instructions and after several reboots all will should be installed. Check **listening ports**:
   ![](/Users/asola/Library/Application%20Support/marktext/images/2024-07-19-13-27-32-image.png)
   If they're not listeing perform
   
   `rm -rf /etc/apt/sources.list.d/pve-enterprise.list
   apt update && apt dist-upgrade-y
   reboot`
   
   

8. Remeber to <u>set a password to root user</u> and login using a browser [https://your_ip_address:8006]()

## Additional Packages

The script installs some additional packages to enhance the experience and provide additional functionalities. The packages include:

1. **'sudo':** Essential tool to grant administrative permissions to the selected user.
2. **'~~nala~~':** An application that enhances the graphical interface of 'apt'.
3. **'neofetch':** A system information display tool with a colorful and user-friendly interface.
4. **'net-tools':** A classic set of network utilities, such as ifconfig and route.
5. **'nmap':** A powerful network scanning and security auditing tool.

Make sure to review the official documentation for each package for more details on their functionalities.

## Features

1. **Proxmox Installation:** The script automatically installs Proxmox on the Debian 12 base.

2. **Additional Packages:** These additional packages are installed to enhance the user experience and provide useful tools for the system and Proxmox environment.

3. **Bridge Creation:** Facilitates network configuration by creating a bridge named vmbr0. You can choose to configure manually or use DHCP.

## Updates and Support

For support or to report issues, [ open an issue](https://github.com/mathewalves/Proxmox-Debian12/issues).

## License

This script is distributed under the [BSD 3-Clause License](https://opensource.org/licenses/BSD-3-Clause).

## Acknowledgments

Thank you for using the Proxmox Installation Script on Debian 12
If you come across any improvements or would like to contribute, feel free to create a pull request. Your contributions are welcome to enhance this script.

We appreciate your participation in the community and your contribution to the ongoing development of this script.

**Enjoy Proxmox!** 🚀

---