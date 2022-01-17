# learning-brownie-framework

I've been curious to education myself on Web3 and Crypto, so I'm setting up a development environment to do some hacking on Ethereum. I'll see where open-minded hacking takes me.

## Motivation
- [Reddit: What is your experience being a professional blockchain engineer? Is it worth it?](https://www.reddit.com/r/ethdev/comments/s66a3x/what_is_your_experience_being_a_professional/)

## How I decided to use Brownie first over Hardhat and Truffle
- I like Python more than Javascript, and Brownie is a Python-based framework
- r/ethdev seems to dislike Truffle, so I avoided it for now
- [Reddit: Brownie vs Hardhat vs Truffle?](https://www.reddit.com/r/ethdev/comments/rkw5nq/brownie_vs_hardhat_vs_truffle/)

## Environment setup

### VM Setup
1a. Download and install Ubuntu 20.04 LTS to use as a base for our development environment

1b. Download and install Brave Browswer because it's not Firefox:
```
sudo apt install apt-transport-https curl

sudo curl -fsSLo /usr/share/keyrings/brave-browser-archive-keyring.gpg https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/brave-browser-archive-keyring.gpg arch=amd64] https://brave-browser-apt-release.s3.brave.com/ stable main"|sudo tee /etc/apt/sources.list.d/brave-browser-release.list

sudo apt update

sudo apt install brave-browser
```

1c. [Install VSCode to use as IDE](git@github.com:tobkin/learning-brownie-framework.git)

1d. [Install Solidity extension for VSCode to enable syntax highlighting](https://marketplace.visualstudio.com/items?itemName=JuanBlanco.solidity)

### Configure git and Github
2a. Install and configure git
```
# install and configure git
sudo apt-get install git
git config --global user.name "Toby Tobkin"
git config --global user.email "tobkin@hey.com"
```

2b. Generate a private/public key pair to read/write to this repo via SSH
```
ssh-keygen -t ed25519 -C "tobkin@hey.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

2c. [Add the public key to Github account](https://github.com/settings/keys)

2d. Clone this repo:
```
git clone git@github.com:tobkin/learning-brownie-framework.git
```

### Install Brownie globally
3a. Install pip
```
sudo apt-get install pip
```

3b. Install brownie globally via pipx, plus hiccups I found on the way: https://github.com/eth-brownie/brownie. There are other installation options that may be preferrable for less casual situations, but I did not use these installation options.
```
python3 -m pip install --user pipx
python3 -m pipx ensurepath
sudo apt install python3.8-venv
pipx install eth-brownie
```
