# Installing Zsh on Ubuntu  

This guide will walk you through installing and setting up **Zsh** with **Oh My Zsh** and useful plugins.  

---

## Step 1: Update Package Lists  

Before installing, update your system's package lists:  

```sh
sudo apt update
```

---

## Step 2: Check Your Current Shell  

Check your current shell with:  

```sh
echo $SHELL
```

If it returns `/bin/bash` or something other than Zsh, continue with the installation.  

---

## Step 3: Install Zsh  

Install Zsh using:  

```sh
sudo apt install -y zsh
```

---

## Step 4: Change Default Shell to Zsh  

Set Zsh as your default shell:  

```sh
chsh -s $(which zsh) $(whoami)
```

Restart your terminal or log out and log back in for changes to take effect.  

---

## Step 5: Install Oh My Zsh  

Install [Oh My Zsh](https://ohmyz.sh/) using:  

```sh
sh -c "$(wget https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"
```

---

## Step 6: Install Plugins  

### Install via Package Manager  

Some plugins can be installed through `apt`:  

```sh
sudo apt install zsh-autosuggestions zsh-syntax-highlighting
```

### Install via Git  

Manually install additional plugins by cloning them into the Oh My Zsh custom plugins directory:  

```sh
# Autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# Syntax Highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# Fast Syntax Highlighting
git clone https://github.com/zdharma-continuum/fast-syntax-highlighting.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/fast-syntax-highlighting

# Autocomplete
git clone --depth 1 https://github.com/marlonrichert/zsh-autocomplete.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/zsh-autocomplete
```

---

## Step 7: Configure Plugins  

Edit your `.zshrc` file:  

```sh
vi ~/.zshrc
```

Find the line:  

```sh
plugins=(git)
```

Replace it with:  

```sh
plugins=(git zsh-autosuggestions zsh-syntax-highlighting fast-syntax-highlighting zsh-autocomplete)
```

Save and exit (`Esc`, then `:wq`, and `Enter`).  

---

## Step 8: Apply Changes  

Apply the new configuration:  

```sh
source ~/.zshrc
```

---

## Step 9: Verify Installation  

Restart your terminal and check if Zsh is running correctly:  

```sh
echo $SHELL
```

It should return `/usr/bin/zsh` or a similar path containing `zsh`.  
