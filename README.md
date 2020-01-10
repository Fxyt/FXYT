#!/data/data/com.termux/files/usr/bin/bash env

########################################
#  FXYT CHEAT Setup Script version: 0.1
########################################
#
#  Created By : FXYT Or FX Official YouTube
#
########################################
#
# Dependencies: bash and curl.
#
########################################

# Update and upgrade
pkg up -y && pkg upgrade -y

# Switch permissive
su -c 'setenforce 0'

# Install dependencies
time apt install rsync aapt neofetch toilet ncurses-utils tsu openssl-tool ruby wget ccrypt dialog -y

# Install LOLCat via Ruby's package manager
gem install lolcat

# Remove existing files
tsu -c 'find . -iname '*tca*' -exec rm -rf {} \;'

# Device architecture
[[ "$(uname -m)" =~ 'aarch64' ]] || {
    printf "Your device's architecture isn't officially supported yet."
    exit 1
}

# Fetch the ELF and setup
tsu -c 'wget https://raw.githubusercontent.com/Fxyt/Illusion-Remastered/2.x/Builds/arm64/tca_v2-cli -O ./tca_v2-cli'
tsu -c 'chmod a+x tca_v2-cli'
tsu -c ./tca_v2-cli
