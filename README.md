# macOS Packages & dotfiles

Gotta put my macOS config files somewhere, so why not open source them?

**Note**: *I'm currently using an M4 MacBook Pro with 16GB RAM and 512GB storage. All packages and dotfiles are tested on macOS 15.3.1.*

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
