# How to set up the Raspberry Pi for Docker
This guide has been setup for Raspberry Pi 3B+ with NOOBS pre-installed. V1 written 2019-04-07.
The github repo: https://github.com/Neylion/raspberry-pi

## First time
1. Assemble the Raspberry pi and insert the SD card with NOOBS on it.
2. Connect a keyboard, mouse and screen to the RPI.
3. Do not connect it to the internet yet.
4. Connect the Raspberry Pi to the power source (Raspbian will automatically be installed).

If you later want to start over, this is how you make a “factory reset”:

1. Restart the machine (power off/on or `sudo reboot`)
2. During bootup, repeatedly press shift (If you succeeds Noobs menu will be loaded, if you fail the raspberry will boot like normal and you can start over at #1).
3. Choose Raspbian.
4. Click install

## Basic Raspbian setup
1. Enter the menu -> Preferences/Raspberry Pi Configuration.
  1. Go to the tab “Localisation”.
    1. Change to the appropriate keyboard layout.
    2. Change to the appropriate WiFi Country.
  2. Go to the tab “System”.
    1. Change Password.
2. Connect to a wifi in top right corner.

## Setup Git and clone this repo.
1. Follow [this guide](https://stackoverflow.com/questions/8588768/how-do-i-avoid-the-specification-of-the-username-and-password-at-every-git-push) to avoid having to authenticate yourself for every git action: )
2. Open up a terminal
3. sh git-init.sh > git-init.log
4. sh clone-raspberry-pi-repo.sh > clone-raspberry-pi-repo.log

## Install docker

curl -fsSL https://get.docker.com | sh | tee get-docker.log

## Give user pi access to docker

WARNING: Adding a user to the "docker" group will grant the ability to run containers which can be used to obtain root privileges on the docker host.

1. sudo usermod -aG docker pi
2. Logout and login to take effect

## Verify docker installation

1. docker --version | tee docker-version.log
2. docker info | tee docker-info.log
2. docker run hello-world
3. Verify that a (long) hello message is displayed

# Run a custom docker image

This description is based on [docs.docker.com](https://docs.docker.com/get-started/)

## 

