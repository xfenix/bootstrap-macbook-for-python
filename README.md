# Fresh macbook bootrstrap
You got new macbook and you are web developer with python backend and/or typescript frontend? This instruction will help you to prepare macbook for work.

## Let's roll!
1. Generate ssh key:
    ```bash
    ssh-keygen -o -a 100 -t ed25519 -C "ad@xfenix.ru"
    ```
    Copy you key in the clipboard:
    ```
    cat ~/.ssh/id_ed25519.pub | pbcopy
    ```
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
    brew install stats itsycal git iterm2 visual-studio-code karabiner-elements pyenv gpg-suite
    ```
1. For macbook with Apple chip (M1, M1 pro, M1 max) install Rosetta2: 
    ```
    softwareupdate --install-rosetta
    ```
1. Install docker dekstop: https://www.docker.com/products/docker-desktop
1. Place VSCode config:
   ```json
   {
        "workbench.colorTheme": "GitHub Dark",
        "editor.fontSize": 14,
        "markdown.preview.typographer": true,
        "markdown.extension.orderedList.marker": "one",
        "editor.formatOnPaste": true,
        "editor.formatOnType": true
    }
   ```
1. Setup git client:
   1. Generate GPG key in GPG tools
   1. Run:
        ```
        gpg --list-secret-keys
        ```
   1. Setup:  
        ```bash
        git config --global user.name "Denis Anikin"
        git config --global user.email ad@xfenix.ru
        git config --global user.signingkey
        git config --global commit.gpgsign true
        ```
