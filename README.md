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

You can customize the Vagrant setup according to your project requirements by modifying the `Vagrantfile` and the provisioning scripts located in the `provision` directory. Feel free to add additional software, tweak configurations, or change settings to suit your needs.

## Contributing

Contributions are welcome! If you find any issues with this setup or have suggestions for improvements, please open an issue or submit a pull request. Your feedback helps make this project better for everyone.

## License

This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and distribute the code as per the terms of the license.

