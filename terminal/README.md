# Steps to setup a pretty terminal on Mac

## 1. Install [Homebrew](https://brew.sh/)
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## 2. Install iterm2

```sh
brew install --cask iterm2
```

## 3. Install starship
Starship is a pretty terminal prompt: https://github.com/starship/starship, https://starship.rs/guide/

1. Install starship using brew

    ```sh
    brew install starship
    ```

2. Add the following command (prompt initialization) to your `.zshrc`:
    
    ```sh
    eval "$(starship init zsh)"
    ```

3. Configure starship:

    ```sh
    mkdir ~/.config
    touch ~/.config/starship.toml
    ```

4. Copy the contents of `.config/starship.toml` of this repo to `~/.config/starship.toml`

5. Starship requires some [Nerd Font](https://www.nerdfonts.com/) to be installed. You can check wether it is installed with this line:
    
    ```sh
    echo -e "\xee\x82\xa0"
    ```

    If you see a git branch logo - you're all set up. If not, first, install a font: put its contents into the `/Library/Fonts` or `~/Library/Fonts` directory:
       
    ```sh
    ➜ tree ~/Library/Fonts -L 2
    /Users/user/Library/Fonts
    ├── CaskaydiaCoveNerdFontMono-Bold.ttf
    ├── CaskaydiaCoveNerdFontMono-BoldItalic.ttf
    ├── CaskaydiaCoveNerdFontMono-ExtraLight.ttf
    ├── CaskaydiaCoveNerdFontMono-ExtraLightItalic.ttf
    ├── CaskaydiaCoveNerdFontMono-Italic.ttf
    ├── CaskaydiaCoveNerdFontMono-Light.ttf
    ├── CaskaydiaCoveNerdFontMono-LightItalic.ttf
    ├── CaskaydiaCoveNerdFontMono-Regular.ttf
    ├── CaskaydiaCoveNerdFontMono-SemiBold.ttf
    ├── CaskaydiaCoveNerdFontMono-SemiBoldItalic.ttf
    ├── CaskaydiaCoveNerdFontMono-SemiLight.ttf
    └── CaskaydiaCoveNerdFontMono-SemiLightItalic.ttf
    ```
    
    Then [add it](https://webinstall.dev/nerdfont/) to your iTerm: find iTerm2 in the top Mac menu, then...

    + Preferences (Cmd ⌘ + ,)
    + Profiles
    + Text
    + Font
    + Select "CaskaydiaCove Nerd Font"


## 4. Add zsh-autosuggestions
Zsh autosuggestions - https://github.com/zsh-users/zsh-autosuggestions

1. Clone this repository somewhere on your machine. This guide will assume `~/.zsh/zsh-autosuggestions`.

    ```sh
    git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/zsh-autosuggestions
    ```

2. Add the following to your `.zshrc` or `.zprofile`:

    ```sh
    source ~/.zsh/zsh-autosuggestions/zsh-autosuggestions.zsh
    ```

## 5. Add new color scheme to iterm2

1. Download scheme into file - `~/popping-and-locking.itermcolors`

    ```sh
    curl -sS https://raw.githubusercontent.com/mbadolato/iTerm2-Color-Schemes/master/schemes/Popping%20and%20Locking.itermcolors > ~/popping-and-locking.itermcolors
    ```

2. Add this scheme by importing `~/popping-and-locking.itermcolors`:

    + Preferences (Cmd ⌘ + ,)
    + Profiles
    + Colors
    + Color Presets
    + Import...

## 6. Add command syntax highlighting
https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md
1. Install brew formulae
    ```sh
    brew install zsh-syntax-highlighting
    ```
2. Source it to the shell
    ```sh
    echo "source $(brew --prefix)/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ~/.zshrc
    ```
3. Restart the shell

## 7. Enable syntax highlighting in vim
```sh
touch ~/.vimrc && echo 'filetype plugin indent on' >> ~/.vimrc && echo 'syntax on' >> ~/.vimrc
```
