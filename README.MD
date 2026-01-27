# 📸 Hypr-Edit

A lightweight and responsive screenshot utility for **Wayland/Hyprland**, written in Python with **PyQt6**. It lets you quickly annotate a capture before sending it to the clipboard without creating temporary files.

## ✨ Features

The tool offers a floating toolbar to edit the capture on the fly:

*   **Shape drawing**: Rectangles (`󰇙`) and Circles (`󰄯`).
*   **Obfuscation**: A pixelated blur tool (`󰝟`) to hide sensitive data.
*   **Highlighter**: A semi-transparent brush (`󰏫`) to emphasize content.
*   **Selector**: Move shapes that were already created (`󰆏`).
*   **Color palette**: A dynamic rainbow slider to change annotation colors.
*   **Canvas management**:
    *   `󰅖` **Clear all**: Removes all drawings.
    *   `󰆴` **Delete**: Removes only the selected shape.
    *   `󰄬` **Validate**: Copies the final image to the clipboard and closes the tool.

## 🛠 Dependencies

Make sure you have the following tools installed on your system:

### System (Wayland)
*   `grim`: For screenshots.
*   `slurp`: For selecting the screen area.
*   `wl-clipboard`: For clipboard management.
*   `hyprland`: Window manager / compositor.
*   `hyprshot`: Screenshot tool for Hyprland.

### Python & UI
*   `Python 3`
*   `PyQt6`: `pip install PyQt6`
*   **Font**: A [Nerd Font](https://www.nerdfonts.com/) (e.g. *JetBrainsMono Nerd Font*) is required to display toolbar icons.

## 🚀 Installation

1.  Make the script executable:
    ```bash
    chmod +x hypr-edit.py
    ```
2.  (Optional) Move it into your PATH:
    ```bash
    mv hypr-edit.py ~/.local/bin/hypr-edit
    ```

## ⚙️ Hyprland configuration

To use the tool with a keyboard shortcut, add the following line to your `~/.config/hypr/hyprland.conf` file:

```ini
# Example with SUPER + Print
bind = $mainMod, Print, exec, hyprshot -m region --raw | hypr-edit
```
