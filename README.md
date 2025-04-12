Ubuntu Tor Sandbox Setup

This project provides a secure, private sandbox environment for browsing the web anonymously. It uses the Tor network to route all internet traffic, ensuring that your browsing activity is private and your real IP address remains hidden. The setup is designed for Ubuntu users, leveraging Docker containers for secure isolation.
Overview

The Ubuntu Tor Sandbox creates an isolated environment using Docker, where all network traffic is routed through the Tor network. This ensures that users can browse the web privately without exposing their real IP address or location. The setup process is automated with a simple Bash script, making it easy for both beginners and experienced users to implement.
Key Features:

    Anonymous browsing through the Tor network.

    Docker-based sandbox for secure isolation from the main system.

    Easy setup and management through a command-line interface (CLI).

    AppArmor security integration for enhanced security.

    Logs and real-time health checks for troubleshooting.

    Beginner-friendly with clear, interactive prompts.

Prerequisites

    Ubuntu 20.04 or later.

    Docker installed on your machine. If Docker is not installed, the script will prompt you to install it.

    A basic understanding of how to use the terminal.

Installation & Setup

    Clone the repository: Clone this repository to your local machine using Git.

git clone https://github.com/WhoAmIx141/ubuntu-tor-sandbox.git
cd ubuntu-tor-sandbox

Make the script executable:

After cloning the repository, navigate to the project folder and make the script executable:

chmod +x sandbox.sh

Run the script to set up the sandbox:

To create the sandbox, use the following command:

    ./sandbox.sh create

    This will:

        Check if Docker is installed.

        Prompt you to install Docker if it isn't already installed.

        Set up Docker containers for Tor and an Ubuntu sandbox.

        Configure the necessary security settings (AppArmor, Docker isolation).

    Once the sandbox is created, you will be able to enter it and start browsing securely.

Usage

After the sandbox is created, you can use the following commands to manage it:

    Enter the sandbox:

./sandbox.sh enter

This will start an interactive session within the Ubuntu sandbox, where all network traffic will be routed through Tor.

Stop the sandbox:

./sandbox.sh stop

This will stop the containers and save any data you have created.

Reset the sandbox (remove containers and volume):

./sandbox.sh reset

This will stop and remove all containers and volumes, effectively resetting the environment. Your data will be preserved unless you specify the --delete-files option.

Refresh the Tor circuit:

./sandbox.sh refresh

This will request a new Tor circuit, ensuring your Tor connection is refreshed.

View the logs:

    ./sandbox.sh logs

    This will display the logs for the sandbox setup and any issues that might have occurred.

Troubleshooting

If you encounter any issues, the script generates logs that can help diagnose the problem. Use the following command to view the logs:

./sandbox.sh logs

Common Errors:

    "Docker not installed": If Docker is not installed, the script will prompt you to install it. After installation, log out and back in for changes to take effect.

    "Sandbox already exists": If you see this message, use the reset command to remove the existing sandbox and try again.

Contributing

Feel free to open issues or pull requests if you encounter bugs, or if you have suggestions for improvements. This project is open to contributions.
Steps to contribute:

    Fork the repository.

    Create a new branch (git checkout -b feature-name).

    Make your changes and commit them (git commit -am 'Add new feature').

    Push the changes (git push origin feature-name).

    Create a pull request with a detailed description of your changes.

License

This project is licensed under the MIT License - see the LICENSE file for details.
Example:
Usage Workflow

    Create the sandbox:

./sandbox.sh create

Enter the sandbox:

./sandbox.sh enter

Browse securely:

curl --socks5 localhost:9050 https://check.torproject.org

Exit the sandbox:

./sandbox.sh stop

Reset or refresh the Tor connection:

    ./sandbox.sh refresh
