# Macbook bootrstrap
You got new macbook and you are web developer? This instruction will help you.

### Basic setup
1. Generate ssh key:
    ```bash
    ssh-keygen -o -a 100 -t ed25519 -C "ad@xfenix.ru"
    ```
    To copy in the clipboard:
    ```
    cat ~/.ssh/id_ed25519.pub | pbcopy
    ```
3. Install chrome: https://www.google.com/chrome/
4. Install homebrew:
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
1. Smth else:
    ```bash
    
    ```

### GPG setup
1. Generate key in GPG tools
1. 
