# macOS Packages & dotfiles

Gotta put my macOS config files somewhere, so why not open source them?

**Note**: *I'm currently using an M4 MacBook Pro with 16GB RAM and 512GB storage. All packages and dotfiles are tested on macOS 15.3.1.*

## Packages 📦

1. **Package Manager Install**:

    ```console
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```

2. **Add Package Repositories**:

    ```console
    brew tap felixkratz/formulae && brew tap koekeishiya/formulae && brew tap mdogan/zulu
    ```

3. **My Main Formulae**:
(tbh, you prob don't want/need the things i do. this is just here so i can reference in the future.)

    ```console
    brew install borders cmake dotnet hyfetch nvm python@3.13 sketchybar yabai
    ```

4. **My Main Casks**:
(again, you prob don't want all this crap on your system.)

    ```console
    brew install appcleaner balenaetcher c0re100-qbittorrent calibre curseforge cyberduck discord docker font-hack-nerd-font krita lm-studio mediamate menu-bar-splitter microsoft-edge playdate-simulator protonvpn qflipper spotify steam swift-quit tor-browser utm visual-studio-code vlc whisky wireshark zulu zulu-jdk8
    ```

## dotfiles ⚙️

1. **Get dotfiles**:

    ```console
    cd /tmp
    git clone https://github.com/ambercaravalho/macos-dotfiles.git
    ```

2. **Move to Config Dir**:

    ```console
    mv -r ./.config/* ~./.config/
    ```

3. **Enable WM & Menubar Services**:

    ```console
    brew services start sketchybar && yabai --start-service
    ```

## Extra Configs 🎉

1. **Sketchybar**:

    ```console
    nano ~/.config/sketchybar/sketchybarrc
    brew services restart sketchybar
    ```

2. **Yabai**:

    ```console
    nano ~/.config/yabai/yabairc
    yabai --restart-service
    ```