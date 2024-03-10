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