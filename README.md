# Solidity "Hello World" setup log: Jan 17 2022


I was blockchain-curious today, so I setup a development environment to do some hacking on Ethereum. While most tutorials I encountered recommended using Remix, a zero-setup IDE, I find I understand new technology better if I must assemble the development toolchain myself. This README.md outlines how I was able to go from a blank Ubuntu 20.04 LTS VM to compiling and running a "hello world" Solidity contract on Jan 17 2022. Perhaps you will find it a useful exercise too.

## Motivation
- [Reddit: What is your experience being a professional blockchain engineer? Is it worth it?](https://www.reddit.com/r/ethdev/comments/s66a3x/what_is_your_experience_being_a_professional/)

## How I decided to use Brownie first over Hardhat and Truffle
- I like Python more than Javascript, and Brownie is a Python-based framework
- r/ethdev seems to dislike Truffle, so I avoided it for now
- [Reddit: Brownie vs Hardhat vs Truffle?](https://www.reddit.com/r/ethdev/comments/rkw5nq/brownie_vs_hardhat_vs_truffle/)

## Environment setup

### 1. VM Setup
1a. Download and install Ubuntu 20.04 LTS to use as a base for our development environment

1b. [Install VSCode to use as IDE](git@github.com:tobkin/learning-brownie-framework.git)

1c. [Install Solidity extension for VSCode to enable syntax highlighting](https://marketplace.visualstudio.com/items?itemName=JuanBlanco.solidity)

### 2. Configure git and Github
2a. Install and configure git
```
$ sudo apt-get install git
$ git config --global user.name "Toby Tobkin"
$ git config --global user.email "tobkin@hey.com"
```

2b. Generate a private/public key pair to read/write to this repo via SSH
```
$ ssh-keygen -t ed25519 -C "tobkin@hey.com"
$ eval "$(ssh-agent -s)"
$ ssh-add ~/.ssh/id_ed25519
```

2c. [Add the public key to Github account](https://github.com/settings/keys)

2d. Clone this repo:
```
$ git clone git@github.com:tobkin/learning-brownie-framework.git
```

### 3. Install Brownie and related prerequisites globally
3a. Install pip and npm
```
$ sudo apt-get install pip npm
```

3b. Install Brownie and prerequisites for using Brownie. There are other install options besides this one that may be more suitable for production environments.
```
$ python3 -m pip install --user pipx
$ python3 -m pipx ensurepath
$ sudo apt install python3.8-venv
$ pipx install eth-brownie

$ sudo npm install ganache-cli
```

### 4. Run HelloWorld locally
```
$ brownie compile
$ brownie console

>>> hw = HelloWorld.deploy({'from': accounts[0]})
>>> hw.greet()
'Hello World!'

```

### 5. Congrats you made it
More exercises past hello world I found useful: https://solidity-by-example.org/
