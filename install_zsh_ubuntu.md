
# Installing Zsh on Ubuntu  

This guide will walk you through installing and setting up Zsh with Oh My Zsh and useful plugins.  

## Step 1: Update Package Lists  

Before installing, update your system's package lists:  

```sh
sudo apt update
```

## Step 2: Check Your Current Shell  

Run the following command to check your current shell:  

```sh
echo $SHELL
```

If it returns `/bin/bash` or something other than Zsh, proceed with the installation.  

## Step 3: Install Zsh  

Install Zsh using:  

```sh
sudo apt install zsh
```

## Step 4: Change Default Shell to Zsh  

Set Zsh as your default shell:  

```sh
chsh -s $(which zsh) $(whoami)
```

Restart your terminal or log out and log back in for changes to take effect.  

## Step 5: Install Oh My Zsh  

Run the following command to install [Oh My Zsh](https://ohmyz.sh/):  

```sh
sh -c "$(wget https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"
```

## Step 6: Install Plugins  

Install useful Zsh plugins:  

```sh
sudo apt install zsh-autosuggestions zsh-syntax-highlighting
```

## Step 7: Configure Plugins  

Open the `.zshrc` configuration file in a text editor:  

```sh
vi ~/.zshrc
```

Find the line that says:  

```sh
plugins=(git)
```

Replace it with:  

```sh
plugins=(git zsh-autosuggestions zsh-syntax-highlighting fast-syntax-highlighting zsh-autocomplete)
```

Save and exit (in vim, press `Shift + :`, then `:wq`, and press `Enter`).  

## Step 8: Apply Changes  

Run the following command to apply the changes:  

```sh
source ~/.zshrc
```

## Step 9: Verify Installation  

Restart your terminal and check if Zsh is running correctly:  

```sh
echo $SHELL
```

It should return `/usr/bin/zsh` or a similar path containing `zsh`.  
