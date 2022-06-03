# My dotfiles + Configurations
All Dotfiles + Themes

1. Brew installation (Brewfile updated 30/12/2021)
```bash
brew bundle install
```

2. Install nvm
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```
Check `.nvmrc` files on repos as required.

3. Install Node (CLI currently tested v14.)
```bash
xargs npm install --global < npm.global
```

4. Pyenv + PIP3
Check that Pyenv is installed `pyenv version`

5. Install PIP3 Packages
```bash
pip install -r pip-req.txt
```

6. Install Rust
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

7. Authenticate as required. Current CLIs
- Railway
- Vercel
- GCP
- AWS
- Helm
### ZSH + Powerlevel9k + Oh-my-ZSH

1. Install [iTerm2 Stable Latest](https://iterm2.com/downloads/stable/latest)

2. Import Configurations (Main / Chiron) as required

3. Follow [How I setup my Terminal oh my zsh](https://blog.woodies11.dev/how-i-set-up-my-terminal-oh-my-zsh-powerline9k-iterm-2/)

## Resources / Notes

- npm export
```bash
npm list --global --parseable --depth=0 | sed '1d' | awk '{gsub(/\/.*\//,"",$1); print}' > path/to/npmfile
```
- npm import
```bash
xargs npm install --global < path/to/npmfilez
```
# Documentation (New Mac)
Getting started - Make sure to install Xcode / Xcode Tools. `xcode-select --install`
(Without this there is no git or Homebrew won't work either)

1. Install iTerm2 from [Downloads](https://iterm2.com/downloads.html) Page

2. Install [Homebrew](https://brew.sh/) with their CLI bash command

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

3. To get this repository you'll need `.ssh` keys configured. This directory will be missing. A quick `ssh-keygen` will create the directory with the appropriate permissions.
You can then copy over the ssh keys as required __(not in this repository)__

4. Clone this repository and work through the installations in the various tools. The key tools to start with are:

- Terminal (iTerm2) + Profiles
- .zsh Configuration and oh-my-zsh
- Hyper Terminal
- Homebrew
- Nvm + Node + Global Packages (v16.x at time of this writing)

## Terminal Setup
This assumes you already have the xcode-tools installed (git) + iTerm2 installed.
Mainly for appearances and for aliases / things that I want to work properly.

- Load `com.googlecode.iterm2.plist` configuration usin the Preferences in the new iTerm2 instance to restore profile.
[Additional Documentation](https://gitlab.com/gnachman/iterm2/-/wikis/Move-Settings-Between-Machines)

- Install oh-my-zsh (sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)")

- Install [Powerlevel10k with oh-my-zsh](https://github.com/romkatv/powerlevel10k#oh-my-zsh)

```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```
**Enabling Plugins (zsh-autosuggestions & zsh-syntax-highlighting)**
- Download zsh-autosuggestions by

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
```

- Download zsh-syntax-highlighting by

```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting```

plugins=(git zsh-autosuggestions zsh-syntax-highlighting)

`git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions`

- Transfer .gitconfig and overwrite

## Node / NVM / Global packages
Next get up and running with [nvm](https://github.com/nvm-sh/nvm) which will manage node versions

- Install using bash (note that the version would have changed)

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```
