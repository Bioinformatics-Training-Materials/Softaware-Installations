# 1. Linux Setup

## a. For Mac Users:
- Simply access the terminal by searching for **"Terminal"** in Spotlight or navigating to **Applications > Utilities > Terminal**.
- You’re all set! Wait for the session to proceed.

## b. For Linux Users:
- If you are already using a Linux distribution like **Ubuntu**, **CentOS**, or **Debian**, you’re good to go. No additional steps are required.

## c. For Windows 10 and Above Users:
### Enable Windows Subsystem for Linux (WSL):
1. Follow this guide to install WSL: [Windows Subsystem for Linux (Microsoft)](https://learn.microsoft.com/en-us/windows/wsl/install).
2. Quick steps for those with experience in OS installations; otherwise, stick to instructions in number 1.
   - Open **PowerShell** as an administrator and run:
     ```powershell
     wsl --install  
     ```
   - This command installs Ubuntu by default. If you want another distribution, specify it:
     ```powershell
     wsl --install -d <distribution-name>  
     ```
   - Restart your system if prompted.

### Additional Resources:

- If you encounter errors, raise an issue on GitHub for assistance.

## d. Alternative 1: Google Cloud Console
- If WSL doesn’t work or you’re using an older version of Windows, you can use **Google Cloud Console**.
  - Sign up for a free tier here: [Google Cloud Console](https://console.cloud.google.com/).
      - Tutorial: [Create a project on Google Cloud](https://www.youtube.com/watch?v=dTT1RGW8eYw).

## e. Alternative 2: Online Linux Terminals
- Use an online terminal for quick access:
   - [Webminal](https://www.webminal.org/)
 
## f. If All Else Fails:
- Bring these issues up during the session for personalized troubleshooting.
