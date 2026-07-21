
```bash
sudo apt update -y
sudo apt install -y curl git zsh gh

# zsh/ohmyzsh
chsh -s $(which zsh)

RUNZSH=no sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

ZSH_CUSTOM="$HOME/.oh-my-zsh/custom"
git clone https://github.com/zsh-users/zsh-autosuggestions.git "$ZSH_CUSTOM/plugins/zsh-autosuggestions"
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git "$ZSH_CUSTOM/plugins/zsh-syntax-highlighting"
git clone --depth 1 -- https://github.com/marlonrichert/zsh-autocomplete.git "$ZSH_CUSTOM/plugins/zsh-autocomplete"
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git "$ZSH_CUSTOM/themes/powerlevel10k"

# mise
sudo apt install -y extrepo
sudo extrepo enable mise
sudo apt update
sudo apt install -y mise

# git blame
git config --global user.name "Afonso Pimenta"
git config --global user.email "afonsocpimenta04@gmail.com"

# move dotfiles to ~ and self destruct
git clone https://github.com/APimenta4/.dotfiles.git "$HOME/.dotfiles_temp"
rm -f "$HOME/.dotfiles_temp/README.md"
cp -a "$HOME/.dotfiles_temp/." "$HOME/"
rm -rf "$HOME/.dotfiles_temp"

gh auth login
```
