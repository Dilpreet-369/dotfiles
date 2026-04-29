# linux
This repo will contain all my config files for my linux setup

##### sudo pacman -S sway swaybg foot wmenu xorg-xwayland

- **swaybg**: Essential for setting wallpapers.
    
- **foot**: A fast, lightweight Wayland-native terminal (Sway's default).
    
- **wmenu**: A Wayland-native menu (replacement for dmenu).
    
- **xorg-xwayland**: Allows you to run older X11 apps that haven't moved to Wayland yet.

mkdir -p ~/.config/sway
cp /etc/sway/config ~/.config/sway/

### Quick Config Tweaks

Open `~/.config/sway/config` in your editor. You might want to change your modifier key (usually Alt by default, many prefer Super/Windows key):

Bash

```
# Change Mod1 (Alt) to Mod4 (Super)
set $mod Mod4

# Set your terminal
set $term foot
```

### Zoom in the terminal 

To zoom in **foot**, you use standard keyboard shortcuts that are common across many modern terminal emulators.

### Default Zoom Shortcuts

- **Zoom In:** `Ctrl` + `+` (or `Ctrl` + `Shift` + `=`)
    
- **Zoom Out:** `Ctrl` + `-`
    
- **Reset to Default:** `Ctrl` + `0`
    

---

### Customizing the Font (Permanent Change)

If you find yourself zooming in every time you open the terminal, you should change the default font size in your configuration file.

1. **Create/Open the config file:**
    
    Bash
    
    ```
    mkdir -p ~/.config/foot
    nano ~/.config/foot/foot.ini
    ```

2. **Add or Edit the font line:** Under the `[main]` section, define your font and size:
    
    Ini, TOML
    
    ```
    [main]
    font=monospace:size=12
    ```
    
    _(Replace `12` with your preferred size and `monospace` with your favorite font, like `JetBrains Mono` or `Hack`)._
    
- **Save and Exit:** In `nano`, press `Ctrl + O` to save and `Ctrl + X` to exit.

`foot` might look a bit "off" or fail to render certain symbols. A good starter pack is:

Bash

```
sudo pacman -S ttf-font-awesome ttf-jetbrains-mono-nerd
```

## Adding Night light (gammastep)

### 1. Edit the Config

Open your Sway configuration file:

Bash

```
nano ~/.config/sway/config
```

### 2. Add the "Exec" Command

Scroll to the very bottom of the file and add this exact line. The `exec` keyword is required to tell Sway to run the command on startup:

Bash

```
exec gammastep -O 3500
```

- **`exec`**: Runs the command when Sway starts.
    
- **`-O 3500`**: "One-shot" mode that forces the orange tint (3500K) immediately and keeps it there.

