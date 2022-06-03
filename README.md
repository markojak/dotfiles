# My dotfiles + Configurations
All Dotfiles + Themes

0. `xcode-select --install`

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

## iterm2

Based on Documentation from https://gitlab.com/gnachman/iterm2/-/wikis/Move-Settings-Between-Machines
Not using DynamicState / Scripts etc. - So only restoring PREFERNCES



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
