# Website Setup with Vagrant

This repository contains a Vagrant setup for quickly provisioning a development environment for website projects. It automates the process of setting up a virtual machine with necessary dependencies and configurations, allowing developers to focus on building and testing their websites without worrying about environment setup.

## Features

- **Consistent Development Environment**: Ensures that all team members have the same development environment, reducing compatibility issues.
- **Isolation**: Keeps the host machine clean by running the development environment within a virtual machine.
- **Easy Setup**: Automates the setup process, saving time and effort for developers.

## Prerequisites

Before you begin, ensure you have met the following requirements:

- [Vagrant](https://www.vagrantup.com/downloads) installed on your local machine.
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads) installed on your local machine.

## Getting Started

To get started with this setup, follow these steps:

1. **Clone the Repository**: Clone this repository to your local machine.

    ```bash
    git clone https://github.com/gianniszisakis/Website-Setup-Vagrant.git
    ```

2. **Navigate to the Repository**: Change your current directory to the cloned repository.

    ```bash
    cd Website-Setup-Vagrant
    ```

3. **Start the Virtual Machine**: Use Vagrant to start the virtual machine and provision the environment.

    ```bash
    vagrant up
    ```

4. **Access the Development Environment**: Once the provisioning is complete, SSH into the virtual machine.

    ```bash
    vagrant ssh
    ```

5. **Start Developing**: You're now inside the virtual machine and ready to start developing your website.

## Customization

You can customize the Vagrant setup according to your project requirements by modifying the `Vagrantfile` and the provisioning. Feel free to add additional software, tweak configurations, or change settings to suit your needs.

This script automates the deployment of a web template onto an Apache web server. Below are the steps performed by the script:

```bash
# Install necessary packages: Apache web server, wget for downloading files, and unzip and zip for handling compressed files
yum install httpd wget unzip zip -y

# Start the Apache web server
systemctl start httpd

# Enable Apache to start automatically on system boot
systemctl enable httpd

# Create a temporary directory for our project
mkdir -p /tmp/ourProject

# Change directory to the temporary directory
cd /tmp/ourProject

# Download the web template zip file. The --no-check-certificate flag disables certificate checks for HTTPS connections.
wget --no-check-certificate https://www.tooplate.com/zip-templates/2137_barista_cafe.zip

# Extract the contents of the downloaded zip file. The -o flag overwrites existing files without prompting.
unzip -o 2137_barista_cafe.zip

# Copy the contents of the extracted directory to the Apache web server's root directory
cp -r 2137_barista_cafe/* /var/www/html

# Restart the Apache web server to apply changes
systemctl restart httpd

# Change directory back to /tmp/
cd /tmp/

# Remove the temporary directory and its contents. The -rf flags remove directories and files forcefully and recursively without prompting for confirmation.
rm -rf /tmp/ourProject
```

## Contributing

Contributions are welcome! If you find any issues with this setup or have suggestions for improvements, please open an issue or submit a pull request. Your feedback helps make this project better for everyone.

## License

This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and distribute the code as per the terms of the license.

