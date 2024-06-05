# Vonor's Dotfiles

This repository contains some of my configuration files.

## VSCode Configuration

This repository includes configuration files for Visual Studio Code (VSCode).

### Font

The configurations utilize the **MonaSpace Neon Var** font. Please ensure you have this font installed on your system for the best experience.
You can download it from its official [GitHub](https://github.com/githubnext/monaspace) page.

### Theme

The **United Ubuntu** theme from the extension **rdnlsmith.linux-themes** is applied in these configurations, which is already included in this VSCode setup.

### Installation

1. Clone this repository to your local system.
2. Copy the configuration files to your VSCode settings directory. The location of this directory varies based on your operating system:
    - **Windows**: `%APPDATA%\Code\User`
    - **macOS**: `$HOME/Library/Application Support/Code/User/`
    - **Linux**: `$HOME/.config/Code/User/`
3. Restart VSCode for the changes to take effect.

## DevContainer Setup

This repository also includes a basic DevContainer setup. DevContainers provide a fully configured and isolated development environment inside a Docker container.

### Getting Started

1. Install [Docker](https://www.docker.com/get-started) on your system.
2. The [Remote - Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension is already part of the VSCode setup provided in this repository. If you're using this setup, you won't need to install the extension separately.
3. Open this repository in VSCode and when prompted, reopen the project in the container. This will start the build of the Docker image as defined in the `.devcontainer` directory.

Please refer to the [VSCode DevContainers documentation](https://code.visualstudio.com/docs/remote/containers) for more information.

## Git Global Configuration

Before you start using Git, you need to set up your global configuration which includes your username and email. This information will be used for every commit you make.

```bash
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
```

Replace `Your Name` and `youremail@example.com` with your actual name and email.

## SSH Agent and Adding a Key

SSH agent is a program that runs in the background and stores your private keys. When you initiate an SSH connection, the agent forwards the key to the server, eliminating the need to enter your passphrase every time.

Here's how you can use ssh-agent and add a key:

### On Linux and macOS

1. Start the ssh-agent in the background:

    ```bash
    eval "$(ssh-agent -s)"
    ```

2. Add your SSH private key to the ssh-agent:

    ```bash
    ssh-add ~/.ssh/id_rsa
    ```

Replace ~/.ssh/id_rsa with the path to your private key, if it's different.

### On Windows

1. Ensure that you have OpenSSH client installed. It comes pre-installed on Windows 10 version 1803 or later. If not, you can install it manually.

2. Set the ssh-agent to autostart. **Note: This command needs to be run with administrator privileges.**

    ```powershell
    Set-Service -Name ssh-agent -StartupType 'Automatic'
    ```

3. Add your SSH private key to the ssh-agent:

    ```powershell
    ssh-add.exe ~/.ssh/id_rsa
    ```

Replace ~/.ssh/id_rsa with the path to your private key, if it's different.

Please refer to the [GitHub SSH documentation](https://docs.github.com/en/authentication/connecting-to-github-with-ssh) for more information.

## Contributing

Contributions are welcome! Please feel free to submit a pull request.

## License

This project is licensed under the MIT License. See the `LICENSE.md` file for details.
