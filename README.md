# Xavier Environment

This is an OSX development environment configuration. This README documents the complete process for setting up the development environment, and quickly getting up and running on any OSX machine.

As a general overview, this configuration will replace usage of the default terminal with ITerm2 and Zsh. It will utilize Oh-My-Zsh as the plugin manager for the terminal. This configuration will also configure a minimal, effective NeoVim environment with Tmux.

This entire development environment has theme synchronicity based on the OneDark theme. The Style guide will walk through adjusting the ITerm2 profile settings and using the PowerLevel9K Terminal theme. The font of choice for this configuration is Fira Code.

![Color Reference](https://raw.githubusercontent.com/Rheisen/xavier-config/master/images/color_reference.png)

Colors: `#282C34`, `#E06C75`, `#98C379`, `#E5C07B`, `#61AFEF`, `#C678DD`, `#56B6C2`, `#ABB2BF`

## Quick Install

1. Download and run ITerm2 ([web link](https://iterm2.com/downloads.html))
2. Run the installer script: `sh -c "$(curl -fsSL https://raw.githubusercontent.com/Rheisen/xavier-config/main/install.sh)"`
3. Install the Fira Code font in the xavier-config iterm assets directory (should open at the end of the install)
4. Setup ITerm2 colors and fonts:
    - Open the ITerm2 Preferences Menu (ITerm2 > Preferences)
    - Select Appearance, Select Theme, change to "Minimal"
    - Select Profiles, Select Colors, Select "Import" from Color Presets in bottom right corner
    - Import `xavier-config.itermcolors` from within documents/xavier-config/iterm and select from dropdown
    - Recommended: No cursor guide, 0 Minimal Contrast, 0 Cursor Boost
    - Select Text (still under Profiles), and change Font to FiraCode Nerd Font (Retina or Regular recommended)
    - Done (you can remove ~/documents/xavier-config/iterm if you'd like)
5. Install the plugs for Neovim (`nvim ~/.xavier-config/nvim/init.vim` and run `:PlugInstall`)
6. Replace YOURUSERNAME in the .zshrc: `nvim ~/.xavier-config/zsh/.zshrc`
7. Source the zshrc config: `source ~/.zshrc`

#### Recommended Downloads:

- Node Version Manager (NVM) ([web link](https://github.com/nvm-sh/nvm))
- Ruby Version Manager (RVM) ([web link](https://rvm.io/))

## Manual Install

### Step One: Downloads

- ITerm2 ([web link](https://iterm2.com/downloads.html))
- Homebrew ([web link](https://brew.sh/))
- Stop here!! Complete Step Two
- Oh-My-Zsh ([web link](https://github.com/ohmyzsh/ohmyzsh))
- VimPlug (install for Vim & NeoVim) ([web link](https://github.com/junegunn/vim-plug))
- PowerLevel9K (follow oh-my-zsh install) ([web link](https://github.com/Powerlevel9k/powerlevel9k/wiki/Install-Instructions#option-2-install-for-oh-my-zsh))
- zsh-history-substring-search (follow oh-my-zsh install) ([web link](https://github.com/zsh-users/zsh-history-substring-search))
- Done

### Step Two: Brew Installations

Install or upgrade the following with Homebrew:

- `brew install zsh`
- `brew install neovim`
- `brew install git`
- `brew install tmux`
- `brew install fzf`
- `brew install ripgrep`
- `brew install bat`
- Done

#### Recommended Brews
- `brew install gradle`
- `brew tap pivotal/tap`
- `brew install springboot`
- `brew install gnupg gnupg2`
- `brew install git-flow`

### Step Three: Clone this Repository

- Configure git if git is not already configured.
- Git clone this repository inside the root directory.
- Hide the repository (optional, recommended): `mv xavier-config .xavier-config`
- Open the repository with finder: `open ~/.xavier-config`
- Done

### Step Four: ITerm2 Setup

- Open ITerm2 (if you didn't use it in the previous step)
- Ensure Zsh is the default shell: `sudo sh -c "echo $(which zsh) >> /etc/shells" && chsh -s $(which zsh)`
- Copy the "iterm" folder somewhere easily findable: `cp ~/.xavier-config/iterm ~/documents/iterm`
- Open the ITerm2 Preferences Menu (ITerm2 > Preferences)
- Select Profiles, Select Colors, Select "Import" from Color Presets in bottom right corner
- Import `xavier-config.itermcolors` from within documents/iterm
- Recommended: No cursor guide, 0 Minimal Contrast, 0 Cursor Boost
- Select Text (still under Profiles), and change Font to FiraCode Nerd Font (Retina or Regular recommended)
- Done

### Step Five: Environment Configuration

#### Neovim
- Remove (`rm ~/.config/nvim/init.vim`) or create the nvim directory (`mkdir ~/.config; mkdir ~/.config/nvim`)
- Symlink the xavier-config NeoVim configuration: `ln -s ~/.xavier-config/nvim/init.vim ~/.config/nvim/init.vim`
- Open the nvim init file `nvim ~/.xavier-config/init.vim` and run `:PlugInstall`
- Follow the comments in the init.vim file for installing CoC language support as desired.
#### ZSH
- Copy the .zshrc-example file as the base for your new .zshrc: `cp ~/.xavier-config/zsh/.zshrc-example ~/.xavier-config/zsh/.zshrc`
- Open the zshrc file: `nvim ~/.xavier-config/zsh/.zshrc` and change the ZSH export as needed
- Add any additonal scripts from previous configuration files to this zshrc
- Remove the current ZSH configuration: `rm ~/.zshrc`
- Symlink the xavier-config ZSH configuration: `ln -s ~/.xavier-config/zsh/.zshrc ~/.zshrc`
#### TMUX
- Symlink the Tmux configuration: `ln -s ~/.xavier-config/.tmux.conf ~/.tmux.conf`
- Done
