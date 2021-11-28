# Fresh macbook bootrstrap
You got new macbook and you are web developer with python backend and/or typescript frontend? This instruction will help you to prepare macbook for work.

## Basic setup
1. Setup o my zsh
    ```bash
    sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    ```
1. Generate ssh key:
    ```bash
    ssh-keygen -o -a 100 -t ed25519 -C "ad@xfenix.ru"
    ```
    Copy you key in the clipboard:
    ```
    cat ~/.ssh/id_ed25519.pub | pbcopy
    ```
1. Install FiraCode font: https://github.com/tonsky/FiraCode
1. Install chrome: https://www.google.com/chrome/
1. Reccomended extensions:
   1. https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm?hl=en
   1. https://chrome.google.com/webstore/detail/tab-suspender/fiabciakcmgepblmdkmemdbbkilneeeh?hl=en
   1. Also for Russian users: https://chrome.google.com/webstore/detail/%D0%BE%D0%B1%D1%85%D0%BE%D0%B4-%D0%B1%D0%BB%D0%BE%D0%BA%D0%B8%D1%80%D0%BE%D0%B2%D0%BE%D0%BA-%D1%80%D1%83%D0%BD%D0%B5%D1%82%D0%B0/npgcnondjocldhldegnakemclmfkngch?hl=ru
1. Install homebrew:
    ```bash
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```
1. Install all necessary packages:
    ```bash
    brew install stats itsycal git iterm2 visual-studio-code karabiner-elements pyenv gpg-suite grammarly
    ```
1. Configure Iterm2:
   1. Must not bother you ![](iterm2-part1.png)
   1. Best font ![](iterm2-part2.png)
   1. Good looking + Guake/Quake like behavior ![](iterm2-part3.png)
1. For macbook with Apple chip (M1, M1 pro, M1 max) install Rosetta2: 
    ```
    softwareupdate --install-rosetta
    ```
1. Install docker dekstop: https://www.docker.com/products/docker-desktop
1. Setup git client:
   1. Generate GPG key in GPG tools
   1. Run command:
        ```bash
        gpg --list-secret-keys
        ```
        Then copy following key:
        ![gpg key](./gpg-key.png)
   1. Setup:  
        ```bash
        git config --global user.name "Denis Anikin"
        git config --global user.email ad@xfenix.ru
        git config --global user.signingkey KEY_FROM_PREVIOUS_STEP
        git config --global commit.gpgsign true
        ```

## Python part
1. Setup pyenv
    ```bash
    echo 'eval "$(pyenv init --path)"' >> ~/.zprofile
    ```
    ```bash
    echo 'eval "$(pyenv init -)"' >> ~/.zshrc
    ```
1. Install and select desired python
   ```bash
   pyenv install 3.10.0
   ```
   ```bash
   pyenv global 3.10.0
   ```
1. Install all necessary packages
    ```bash
    pip install black isort docformatter pybetter
    ```

### VSCode configuration
This config meant for python development. But you can grab any part of it for other purposes.<br>
Place following in you `settings.json`:
```json
    {
        "window.zoomLevel": 1,

        "workbench.colorTheme": "GitHub Dark",
        "workbench.iconTheme": "helium-icon-theme",
        "workbench.productIconTheme": "fluent-icons",

        "markdown.preview.typographer": true,
        "markdown.extension.orderedList.marker": "one",

        "editor.wordBasedSuggestions": false,
        "editor.fontFamily": "FiraCode-Retina",
        "editor.fontSize": 14,
        "editor.fontLigatures": true,
        "editor.formatOnPaste": true,
        "editor.formatOnType": true,
        "editor.renderWhitespace": "all",
        "editor.rulers": [
            120
        ],

        "debug.console.fontSize": 14,

        "terminal.integrated.fontSize": 14,

        "emmet.triggerExpansionOnTab": true,
        "emmet.includeLanguages": {
            "plaintext": "html"
        },

        "python.formatting.blackPath": "/Users/xfenix/.pyenv/shims/black",
        "python.formatting.provider": "black",
        "python.sortImports.path": "/Users/xfenix/.pyenv/shims/isort",
        "python.sortImports.args": [
            "--line-width",
            "120",
            "--lines-after-imports",
            "2",
            "--no-lines-before",
            "STDLIB,LOCALFOLDER"
        ],
        "emeraldwalk.runonsave": {
            "commands": [
                {
                    "match": ".*\\.py$",
                    "command": "/Users/xfenix/.pyenv/shims/docformatter --in-place ${file}"
                },
                {
                    "match": ".*\\.py$",
                    "command": "/Users/xfenix/.pyenv/shims/pybetter ${file}"
                }
            ]
        }
    }
```
Dont forget to replace in `/Users/xfenix/...` string `xfenix` with you user
