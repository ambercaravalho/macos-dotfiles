# macOS Packages & dotfiles

Gotta put my macOS config files somewhere, so why not open source them?

**Note**: *I'm currently using an M4 MacBook Pro with 16GB RAM and 512GB storage. All packages and dotfiles are tested on macOS 15.3.1.*

## Packages 📦

Cataloging the packages, formulae, and apps installed on my system as of *March 08, 2025*. If you're not me, then you probably want to skip this section. 😜

1. **Package Manager Install**:

    ```console
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```

2. **Add Package Repositories (Taps)**:

    ```console
    brew tap felixkratz/formulae && brew tap koekeishiya/formulae && brew tap mdogan/zulu
    ```

3. **My Main Formulae**:
(tbh, you prob don't want/need the things i do. this is just here so i can reference in the future.)

    ```console
    brew install borders cmake dotnet hyfetch mas nvm python@3.13 sketchybar yabai
    ```

4. **My Main Casks**:
(again, you prob don't want all this crap on your system.)

    ```console
    brew install appcleaner balenaetcher c0re100-qbittorrent calibre curseforge cyberduck discord docker font-hack-nerd-font krita lm-studio mediamate menu-bar-splitter microsoft-edge playdate-simulator protonvpn qflipper spotify steam swift-quit tor-browser utm visual-studio-code vlc whisky wireshark zulu zulu-jdk8
    ```

5. **My App Store Apps**:
(this is just straight up dangerous. pls don't run a command with random numbers in it.)

    ```console
    mas install 497799835 425424353 1622835804 408981434 409183694 668208984 6661016989 1295203466 409201541 682658836 937984704 409203825
    ```

## dotfiles ⚙️

These are mostly just templates provided by the developers. I'll be adding more customizations in the future (maybe).

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

I love forgetting where basic configuration files sit! So here they are.

1. **Sketchybar**:

- Sketchybar Man: https://felixkratz.github.io/SketchyBar/config/bar

    ```console
    nano ~/.config/sketchybar/sketchybarrc
    brew services restart sketchybar
    ```

2. **Yabai**:

- Yabai Man: https://github.com/koekeishiya/yabai/blob/master/doc/yabai.asciidoc#config
- JankyBorders Man: https://github.com/FelixKratz/JankyBorders/wiki/Man-Page

    ```console
    nano ~/.config/yabai/yabairc
    yabai --restart-service
    ```

## Break Some Shit 🔥

I'm a madwoman who wants the FULL control over the window manager. You can get some extra functionality from Yabai at the risk of massively opening your system to vulnerabilities.

1. **Turn Off SIP**:
(this is a bad idea and really shouldn't be done. i did it though and haven't been hacked.. yet)

    https://github.com/koekeishiya/yabai/wiki/Disabling-System-Integrity-Protection

2. **Add Yabai to sudoers File**:

    ```console
    echo "$(whoami) ALL=(root) NOPASSWD: sha256:$(shasum -a 256 $(which yabai) | cut -d " " -f 1) $(which yabai) --load-sa" | sudo tee /private/etc/sudoers.d/yabai
    ```