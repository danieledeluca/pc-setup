# PC Setup

This repository contains info on all the apps, tools and settings I use on my PC.

## Software

### Winget

Winget allow you to install apps from **Windows Terminal**.

Run this command in your **Terminal** to install a list of basic apps.

```
winget install --id=7zip.7zip -e && winget install --id=Figma.Figma -e && winget install --id=Glarysoft.GlaryUtilities -e && winget install --id=Google.Chrome -e && winget install --id=Google.GoogleDrive -e && winget install --id=Logitech.OptionsPlus -e && winget install --id=Microsoft.VisualStudioCode -e && winget install --id=Mozilla.Firefox -e && winget install --id=Notepad++.Notepad++ -e && winget install --id=Microsoft.PowerToys -e && winget install --id=Google.QuickShare -e && winget install --id=QL-Win.QuickLook -e && winget install --id=RevoUninstaller.RevoUninstaller -e && winget install --id=Spotify.Spotify -e && winget install --id=MartiCliment.UniGetUI -e && winget install --id=VideoLAN.VLC -e && winget install --id=Microsoft.WindowsTerminal.Preview -e && winget install --id=RARLab.WinRAR -e
```

List of apps:

-   7-Zip
-   Figma
-   Glary Utilities
-   Google Chrome
-   Google Drive
-   Logi Options+
-   Microsoft Visual Studio Code
-   Mozilla Firefox
-   Notepad++
-   PowerToys
-   Quick Search
-   QuickLook
-   Revo Uninstaller
-   Spotify
-   UniGetUI
-   VLC media player
-   Windows Terminal Preview
-   WinRAR

### Other apps

Some other apps need to be downloaded from their sties:

-   [Adobe Creative Cloud](https://www.adobe.com/it/creativecloud/desktop-app.html) allows you to install Adobe apps.

    ```
    winget install --id=Adobe.CreativeCloud -e
    ```

    -   Adobe Acrobat Reader allows you to work with `.pdf` files

        ```
        winget install --id=Adobe.Acrobat.Reader.64-bit -e
        ```

-   [McAfee](https://www.mcafee.com/it-it/index.html) is an antivirus app.

-   [Local](https://localwp.com/) allows you to develop **WordPress** site.

    ```
    winget install --id=Flywheel.Local -e
    ```

-   [Poedit](https://poedit.net/) allows you to translate **WordPress** site.

    ```
    winget install --id=VaclavSlavik.Poedit -e
    ```

## WSL

Install the [WSL2](https://docs.microsoft.com/en-us/windows/wsl/install) (Windows Subsystem for Linux).

-   Open the **Windows Features tool** by executing the `optionalfeatures` command from the **Run prompt or a Terminal window**.
    You can also click on the Start menu and search for the term "**Turn Windows features on or off**" to do the same.
-   In the new window, **place checkmarks** for the **Virtual Machine Platform** and the **Windows Subsystem for Linux** entries.
-   Click **OK** and wait for Windows to download the required components.
-   Restart your PC. (Could be optional)

Open the **PowerShell** as `administrator` and run these commands.

```
# Install WSL and Ubuntu as default distribution
wsl --install

# Set WSL to version 2
wsl --set-default-version 2

# Update WSL
wsl --update
```

---

## WSA

Install the [WSA](https://learn.microsoft.com/it-it/windows/android/wsa/) (Windows Subsystem for Android).

> Microsoft is ending support for the Windows Subsystem for Android™️ (WSA).
> As a result, the Amazon Appstore on Windows and all applications and games dependent on WSA will no longer be supported beginning March 5, 2025.

Install the [WSA with Google Play Service](https://www.xda-developers.com/how-to-install-google-play-store-windows-subsystem-for-android/).

-   [Install Windows Subsystem for Linux](#wsl)
-   Preparing Windows Subsystem for Android for patching
    -   Download the latest [WSA Script from GitHub](https://github.com/MustardChef/WSABuilds).
    -   Extract the ZIP file to a new folder.
    -   Execute **run.bat**.

---

## Git and NodeJS

Install [Git](https://git-scm.com/) e [NodeJS](https://nodejs.org/en).

```
# Install Git
sudo apt install git

# Install nvm (Node Version Manager)
sudo apt install curl
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash

# Install NodeJS
nvm install node
```

---

## Terminal

Customize the `Windows Terminal Preview`.

### Terminal settings

```json
"profiles": {
    "defaults": {
        "colorScheme": "One Half Dark",
        "font": {
            "face": "MesloLGS NF"
        }
    }
}
```

### Oh-my-zsh

[Oh-my-zsh](https://ohmyz.sh/) is a framework built on top of zsh shell.

```
sudo apt install zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### PowerLevel10k

[PowerLevel10k](https://github.com/romkatv/powerlevel10k) is a theme for zsh shell.

Before installing PowerLevel10k you need to install a [nerd font](https://github.com/romkatv/powerlevel10k?tab=readme-ov-file#meslo-nerd-font-patched-for-powerlevel10k).

```
# Install PowerLevel10k
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k

# Run PowerLevel10k configuration
p10k configure
```

#### Configurations

| Configuration                  | Value     |
| ------------------------------ | --------- |
| Prompt Style                   | Pure      |
| Non-permanent content location | Right     |
| Show current time?             | No        |
| Prompt Height                  | Two lines |
| Prompt Spacing                 | Sparse    |
| Enable Transient Prompt?       | Yes       |

### Oh-my-zsh plugins

Oh-my-zsh has a lot of useful plugins.

-   [zsh-interactive-cd](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/zsh-interactive-cd) provides an interactive way to navigate through directories in the terminal.
-   [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions) suggests commands as you type based on history and completions.

    ```
    git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
    ```

-   [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting) provides syntax highlighting.

    ```
    git clone https://github.com/zsh-users/zsh-syntax-highlighting ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
    ```

-   [zsh-completions](https://github.com/zsh-users/zsh-completions) provides additional completion definitions.

    ```
    git clone https://github.com/zsh-users/zsh-completions ${ZSH_CUSTOM:-${ZSH:-~/.oh-my-zsh}/custom}/plugins/zsh-completions
    ```

-   [fzf](https://github.com/junegunn/fzf) is a general-purpose command-line fuzzy finder.

    ```
    sudo apt install fzf
    ```

-   [fzf-tab](https://github.com/Aloxaf/fzf-tab) replace zsh's default completion selection menu with fzf.

    ```
    git clone https://github.com/Aloxaf/fzf-tab ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/fzf-tab
    ```

-   [zoxide](https://github.com/ajeetdsouza/zoxide) is a smarter cd command.

    ```
    curl -sSfL https://raw.githubusercontent.com/ajeetdsouza/zoxide/main/install.sh | sh
    ```

    After installing it, you need to move zoxide directory.

    ```
    sudo mv ~/.local/bin/zoxide ~/../../usr/local/bin/
    ```

---

## Github

First of all you need to generate a public `SSH key`.

```
ssh-keygen -o -t rsa -C "48753350+danieledeluca@users.noreply.github.com"
```

Add your `SSH key` generated to the `ssh-agent`.

```
eval `ssh-agent -s`
ssh-add
```

Create a new SSH key on [Github](https://github.com/settings/keys).

```
cat .ssh/id_rsa.pub
```

---

## Dotfiles

See the [dotfiles](https://github.com/danieledeluca/dotfiles) repository.

---
