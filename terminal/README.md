# Steps to setup a pretty terminal on Mac

## 1. Install brew
```sh
export HOMEBREW_BREW_GIT_REMOTE="..."  # put your Git mirror of Homebrew/brew here
export HOMEBREW_CORE_GIT_REMOTE="..."  # put your Git mirror of Homebrew/homebrew-core here
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

## 2. Install iterm2

```sh
brew install --cask iterm2
```

## 2. Install spaceship
Spaceship is a pretty terminal prompt: https://github.com/spaceship-prompt/spaceship-prompt

1. Install spaceship using brew

    ```sh
    brew install spaceship
    ```

2. Add prompt initialization to your `.zshrc`:

    ```sh
    echo "source $(brew --prefix)/opt/spaceship/spaceship.zsh" >>! ~/.zshrc
    ```

3. Configure spaceship:

    ```sh
    mkdir ~/.config
    touch ~/.config spaceship.toml
    ```

4. Copy the contents of `.config/spaceship.toml` of this repo to `~/.config spaceship.toml`

## 3. Add zsh-autosuggestions
Zsh autosuggestions - https://github.com/zsh-users/zsh-autosuggestions

1. Clone this repository somewhere on your machine. This guide will assume `~/.zsh/zsh-autosuggestions`.

    ```sh
    git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/zsh-autosuggestions
    ```

2. Add the following to your `.zshrc`:

    ```sh
    source ~/.zsh/zsh-autosuggestions/zsh-autosuggestions.zsh
    ```

## 4. Add new color scheme to iterm2

1. Download scheme into file - `~/popping-and-locking.itermcolors`

```sh
curl -sS https://raw.githubusercontent.com/mbadolato/iTerm2-Color-Schemes/master/schemes/Popping%20and%20Locking.itermcolors > ~/popping-and-locking.itermcolors
```

2. Add this scheme by importing `~/popping-and-locking.itermcolors` into Profiles/Colors/Color Presets
