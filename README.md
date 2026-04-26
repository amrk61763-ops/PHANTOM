# PHANTOM
Hide encrypted files inside JPEG images using pure Bash.
No Python. No external libraries. Just terminal tools.

## How it works

HIDE:  file / gzip / AES-256 / inject into JPEG tail |
REVEAL: JPEG / extract / AES-256 decrypt / original file

## Requirements

openssl / gzip / dd / grep / file

## Usage

# Hide a file inside an image
bash steglock.sh hide 
1- the path of the file you want to hide |
2- the path of the cover you want to but your file in |
3- any password you want to put

# Reveal a hidden file
bash steglock.sh reveal 
1- the path of the file you want to reveal |
2- the password of the file

## Author
Amr Khaled Abdelkader/
github.com/amrk61763-ops
