# WSL Starter
This is a feature in [WinSSHTerm](https://winsshterm.blogspot.com), which will allow you easily access your linux distribution locally on Windows ([WSL](https://en.wikipedia.org/wiki/Windows_Subsystem_for_Linux)) with PuTTY via SSH. Once everything is set up, WinSSHTerm will automatically launch the SSH server so you can quickly connect to your WSL distribution.

Walkthrough for Ubuntu 22.04 LTS on Youtube

[![Demonstration on Youtube (Ubuntu 22.04 LTS)](https://img.youtube.com/vi/gjvxvKIjmro/0.jpg)](https://www.youtube.com/watch?v=gjvxvKIjmro)

## Steps
### Prerequisites
1. Ensure that WSL is installed on your Windows system. You can see the install instructions [here](https://docs.microsoft.com/en-us/windows/wsl/install).
2. Ensure that you use WinSSHTerm 2.33.0 or higher.
### Install a linux distribution and setup a user
3. Open up WinSSHTerm and go to Tools->WSL Starter. You will see the `WSL Starter` window.
4. Choose a linux distribution on [https://github.com/WinSSHTerm/WSL_Starter](https://github.com/WinSSHTerm/WSL_Starter) and copy&paste the contents of the XML file into the text field of the `WSL Starter` window.
5. Now you can install the linux distribution by clicking on the Install button. This will open up the app page in the Microsoft Store. Click on `Install` and then on `Open`
6. A terminal will open up, and after some time you will be prompted to enter a username and password (which you can both freely choose). After that you will get a linux prompt. You can then close the terminal.
### Install, configure and launch the SSH server
7. Now enter the username and password from step 6 into the corresponding fields in the "WSL Starter" window. The default values for "ListenAddress" and "Port" should be fine if you only use one linux distribution at the same time.
8. Click on `Setup SSH` to install and configure the SSH server. This might take a few minutes.
9. Tick the check box `Run "Startup SSH" automatically`.
### Add a new connection to WinSSHTerm and start the session
10. Now click on `Close` to close the `WSL Starter` window.
11. On the left, in the `Connections` window, right-click the `Connect` node and choose `Add connection`
12. Select the new connection, and fill out these fields in the `Configuration` window (use the values from the `WSL Starter` window), e.g.:
    - Name: `WSL` (or choose any other name)
    - Host/IP: `localhost` (or `127.0.0.1` for IPv4, or `::1` for IPv6)
    - Port: `2222`
    - Note:
      - The fields `User` and `Password` will be automatically used from the `WSL Starter` window, if they are empty
      - If the values for `Host/IP` and `Port` don't match the values from the `WSL Starter` window, the automatic start feature won't work
13. Now double-click the connection to open up the PuTTY session. The SSH server will be started, if needed. You should now be successfully logged in with your user. You should be able to become root with `sudo su -`
