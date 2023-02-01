# PC Setup

This repo contains info on all the apps, tools and settings I use on my PC.

## Software

### Winget

Winget allow you to install apps from `Windows Terminal`.

Run this command in your `Terminal` to install a list of basic apps ([winstall](https://winstall.app/packs/zVcEYPpNJ)).

```
winget install --id=Google.Chrome -e  && winget install --id=Google.Drive -e  && winget install --id=7zip.7zip -e  && winget install --id=RARLab.WinRAR -e  && winget install --id=Microsoft.WindowsTerminal.Preview -e  && winget install --id=Microsoft.PowerToys -e  && winget install --id=Microsoft.VisualStudioCode -e  && winget install --id=Notepad++.Notepad++ -e  && winget install --id=Flywheel.Local -e  && winget install --id=Figma.Figma -e  && winget install --id=WhatsApp.WhatsApp -e  && winget install --id=Spotify.Spotify -e  && winget install --id=VideoLAN.VLC.Nightly -e  && winget install --id=Glarysoft.GlaryUtilities -e  && winget install --id=RevoUninstaller.RevoUninstaller -e  && winget install --id=QL-Win.QuickLook -e  && winget install --id=Logitech.OptionsPlus -e
```

List of apps:

-   Google Chrome
-   Google Drive
-   7-Zip
-   WinRAR
-   WIndows Terminal Preview
-   PowerToys
-   Microsoft Visual Studio Code
-   Notepad++
-   Local
-   Figma
-   WhatsApp
-   Spotify
-   VLC media player nightly
-   Glary Utilities
-   Revo Uninstaller
-   QuickLook
-   Logi Options+

### Extra apps

Some other apps need to be downloaded from their sties:

-   [Adobe Creative Cloud](https://www.adobe.com/it/creativecloud/desktop-app.html) allow you to install Adobe apps:
    -   Adobe Photoshop
    -   Adobe Illustrator
    -   Adobe Acrobat DC
-   [McAfee](https://myaccount.mcafee.com/dashboard/it-it/0) is an antivirus app

---

## WSL

Install the [WSL2](https://docs.microsoft.com/en-us/windows/wsl/install) (Windows Subsystem for Linux).

Open the `PowerShell` as **administrator** and run these commands.

```
// Install WSL
wsl --install

// Install Ubuntu
wsl --install -d Ubuntu

// Install Git
sudo apt-get install git

// Install nvm (Node Version Manager)
sudo apt-get install curl
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash

// Install NodeJS
nvm install --lts
```

---

## Terminal

Customize the `Windows Terminal Preview`.

### Oh-my-zsh

[Oh-my-zsh](https://ohmyz.sh/) is a framework built on top of `Zsh` shell.

```
sudo apt-get install zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### Oh-my-zsh plugins

Oh-my-zsh has a lot of useful plugins.

-   [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions) suggests commands as you type based on history and completions.

    ```
    sudo git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
    ```

---

## Github

First of all you need to generate a public `SSH key`.

```
ssh-keygen -o -t rsa -C "48753350+danieledeluca@users.noreply.github.com"
```

Add your `SSH key` generated to the `ssh-agent`.

```
ssh-add ~/.ssh/id_rsa
```

Clone the [`.dotfiles`](https://github.com/danieledeluca/dotfiles) repository to get all the configuration files you need.

```
git clone git@github.com:danieledeluca/dotfiles.git ~/.dotifles
```

Run the config script.

```
~/.dotfiles/config.sh
```

---

## NodeJS

### Global configuration

In your `/root` directory run this command to install some dependencies useful for linting and formatting code:

```
npm i -D eslint eslint-config-airbnb-base eslint-plugin-import stylelint stylelint-config-sass-guidelines
```

These are the dependencies that will be install:

-   [eslint](https://www.npmjs.com/package/eslint)
    -   [eslint-config-airbnb-base](https://www.npmjs.com/package/eslint-config-airbnb-base)
    -   [eslint-plugin-import](https://www.npmjs.com/package/eslint-plugin-import)
    -   [eslint-config-prettier](https://www.npmjs.com/package/eslint-config-prettier)
    -   [eslint-plugin-prettier](https://www.npmjs.com/package/eslint-plugin-prettier)
-   [stylelint](https://www.npmjs.com/package/stylelint)
    -   [stylelint-config-sass-guidelines](https://www.npmjs.com/package/stylelint-config-sass-guidelines)
    -   [stylelint-config-prettier-scss](https://www.npmjs.com/package/stylelint-config-prettier-scss)
-   [prettier](https://www.npmjs.com/package/prettier)
