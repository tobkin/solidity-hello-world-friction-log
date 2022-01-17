# learning-brownie-framework

## Environment setup
1. Download and install Ubuntu 20.04 LTS as a VM image
2. Download and install Brave Browswer:
```
sudo apt install apt-transport-https curl

sudo curl -fsSLo /usr/share/keyrings/brave-browser-archive-keyring.gpg https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/brave-browser-archive-keyring.gpg arch=amd64] https://brave-browser-apt-release.s3.brave.com/ stable main"|sudo tee /etc/apt/sources.list.d/brave-browser-release.list

sudo apt update

sudo apt install brave-browser
```
3. Install pip
```
sudo apt-get install pip
```
4. Install brownie globally via pipx, plus hiccups I found on the way: https://github.com/eth-brownie/brownie. There are other installation options that may be preferrable for less casual situations, but I did not use these installation options.
```
python3 -m pip install --user pipx
python3 -m pipx ensurepath
sudo apt install python3.8-venv
pipx install eth-brownie

```
