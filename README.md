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

## Vim

1. Clone the repository and run the installation script.

    ```bash
    cd
    git clone --depth=1 https://github.com/amix/vimrc.git ~/.vim_runtime
    sh ~/.vim_runtime/install_awesome_vimrc.sh
    ```

## Tmux

1. Clone the repository.

    ```bash
    cd
    git clone https://github.com/gpakosz/.tmux.git
    ln -s -f .tmux/.tmux.conf
    cp .tmux/.tmux.conf.local .
    ```

2. Change color theme manually by chaning `~/.tmux.conf.local`

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
3. mouse setting
   ```bash
    set -g mouse on
    setw -g mode-keys vi
    
    # Use Alt-arrow keys without prefix key to switch panes
    bind -n M-Left select-pane -L
    bind -n M-Right select-pane -R
    bind -n M-Up select-pane -U
    bind -n M-Down select-pane -D
    
    # Shift arrow to switch windows
    bind -n S-Left  previous-window
    bind -n S-Right next-window
    
    # scrollback buffer size increase
    set -g history-limit 100000
    
    # change window order
    bind-key -n C-S-Left swap-window -t -1
    bind-key -n C-S-Right swap-window -t +1
    
    # disable window name auto change
    set-option -g allow-rename off
    
    # bar color
    set -g status-bg black
    set -g status-fg white
    
    # toggle pane title visibility
    bind T run 'zsh -c "arr=( off top ) && tmux setw pane-border-status \${arr[\$(( \${arr[(I)#{pane-border-status}]} % 2 + 1 ))]}"'
    # rename pane
    bind t command-prompt -p "(rename-pane)" -I "#T" "select-pane -T '%%'"
   ```
  
5. Add following line in `~/.tmux.conf` for using zsh

   ```bash
   set-option -g default-shell /bin/zsh
   ```
