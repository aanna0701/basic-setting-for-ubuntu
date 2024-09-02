# Ubuntu customization settings
## Zsh

### install zsh

```bash
sudo apt-get install zsh
```

### install oh-my-zsh

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

<br />

## Powerlevel10k

1. Clone the repository.
    ```bash
    git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
    ```

2. Set `ZSH_THEME="powerlevel10k/powerlevel10k"` in ~/.zshrc.

3. Restart Zsh with `exec zsh`.

4. Type `p10k configure` if the configuration wizard doesn't start automatically.

<br />

## Zsh Plugins

### zsh-autosuggestions

1. Clone this repository into `$ZSH_CUSTOM/plugins` (by default `~/.oh-my-zsh/custom/plugins`).

    ```bash
    git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
    ```

2. Add the plugin to the list of plugins for Oh My Zsh to load (inside `~/.zshrc`).

    ```bash
    plugins=( 
        # other plugins...
        zsh-autosuggestions
    )
    ```

<br />

## LS Colors

1. Clone the repository.

    ```bash
    git clone https://github.com/trapd00r/LS_COLORS.git
    ```
2. To enable the colors, add the following line to your shell's start-up script.

    ```bash
    source ~/path/to/lscolors.sh
    ```

## Tmux

1. Clone the repository.

    ```bash
    cd
    git clone https://github.com/gpakosz/.tmux.git
    ln -s -f .tmux/.tmux.conf
    cp .tmux/.tmux.conf.local .
    ```

2. Change color theme manually by chaning ~/.tmux.conf.local

   ```bash
   # Modify tmux_conf_theme_colour_x with bellow lines
   # Atom One Dark theme
   tmux_conf_theme_colour_1="#282c34"  # Background (Very dark gray-blue)
   tmux_conf_theme_colour_2="#3e4451"  # Pane borders (Dark gray)
   tmux_conf_theme_colour_3="#5c6370"  # Inactive panes (Gray)
   tmux_conf_theme_colour_4="#61afef"  # Focused pane (Bright blue)
   tmux_conf_theme_colour_5="#e5c07b"  # Text (Gold)
   tmux_conf_theme_colour_6="#282c34"  # Unfocused pane (Very dark gray-blue)
   tmux_conf_theme_colour_7="#abb2bf"  # Status line (Light gray)
   tmux_conf_theme_colour_8="#282c34"  # Background (Very dark gray-blue)
   tmux_conf_theme_colour_9="#e06c75"  # Highlighted text (Soft red)
   tmux_conf_theme_colour_10="#c678dd" # Warnings (Purple)
   tmux_conf_theme_colour_11="#98c379" # Success or active (Green)
   tmux_conf_theme_colour_12="#5c6370" # Inactive elements (Gray)
   tmux_conf_theme_colour_13="#abb2bf" # Inactive text (Light gray)
   tmux_conf_theme_colour_14="#282c34" # Background (Very dark gray-blue)
   tmux_conf_theme_colour_15="#282c34" # Inactive borders (Very dark gray-blue)
   tmux_conf_theme_colour_16="#d19a66" # Alerts (Orange)
   tmux_conf_theme_colour_17="#abb2bf" # Text (Light gray)
   ```
