# PC Setup

This repository contains info on all the apps, tools and settings I use on my PC.

## Software

### Winget

Winget allow you to install apps from `Windows Terminal`.

Run this command in your `Terminal` to install a list of basic apps ([winstall](https://winstall.app/packs/zVcEYPpNJ)).

```
winget install --id=Google.Chrome -e  && winget install --id=Mozilla.Firefox -e  && winget install --id=7zip.7zip -e  && winget install --id=RARLab.WinRAR -e  && winget install --id=SomePythonThings.WingetUIStore -e  && winget install --id=Microsoft.WindowsTerminal.Preview -e  && winget install --id=Microsoft.PowerToys -e  && winget install --id=Microsoft.VisualStudioCode -e  && winget install --id=Notepad++.Notepad++ -e  && winget install --id=Google.GoogleDrive -e  && winget install --id=Google.NearbyShare -e  && winget install --id=Figma.Figma -e  && winget install --id=WhatsApp.WhatsApp -e  && winget install --id=Spotify.Spotify -e  && winget install --id=VideoLAN.VLC -e  && winget install --id=Glarysoft.GlaryUtilities -e  && winget install --id=RevoUninstaller.RevoUninstaller -e  && winget install --id=QL-Win.QuickLook -e  && winget install --id=Logitech.OptionsPlus -e
```

List of apps:

-   Google Chrome
-   Mozilla Firefox
-   7-Zip
-   WinRAR
-   WingetUI
-   WIndows Terminal Preview
-   PowerToys
-   Microsoft Visual Studio Code
-   Notepad++
-   Google Drive
-   Google Nearby Share
-   Figma
-   WhatsApp
-   Spotify
-   VLC media player
-   QuickLook
-   Glary Utilities
-   Revo Uninstaller
-   Logi Options+

### Other apps

Some other apps need to be downloaded from their sties:

-   [Adobe Creative Cloud](https://www.adobe.com/it/creativecloud/desktop-app.html) allows you to install Adobe apps.
-   [McAfee](https://myaccount.mcafee.com/dashboard/it-it/0) is an antivirus app.

## WSL

Install the [WSL2](https://docs.microsoft.com/en-us/windows/wsl/install) (Windows Subsystem for Linux).

Open the `PowerShell` as **administrator** and run these commands.

```
# Install WSL
wsl --install

# Install Ubuntu
wsl --install -d Ubuntu

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

## WordPres development

### Software

-   [Local](https://localwp.com/) allow you to develop WordPress site.

    ```
    winget install --id=Flywheel.Local
    ```

-   [Poedit](https://poedit.net/) allow you to translate WordPress site.
