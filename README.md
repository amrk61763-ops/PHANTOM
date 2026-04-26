# PHANTOM 
> Hide encrypted files inside JPEG images — Pure Bash, zero dependencies.

No Python. No external libraries. Just Linux terminal tools that exist on any system.

## How It Works

```
HIDE:   file → gzip → AES-256-CBC → inject into JPEG tail
REVEAL: JPEG → extract → AES-256 decrypt → original file
```

Any JPEG image ends with the bytes `FF D9`. Everything after that is ignored by image viewers — PHANTOM uses this space to hide your encrypted file invisibly.

## Security Layers

| Layer | Tool | Description |
|-------|------|-------------|
| Compression | gzip | Reduces file size before encryption |
| Encryption | AES-256-CBC | Military-grade encryption via openssl |
| Key Derivation | PBKDF2 | Protects against brute-force attacks |
| Steganography | JPEG tail injection | Hidden data invisible to any image viewer |

## Requirements

```bash
openssl · gzip · dd · grep · file
```

All tools are pre-installed on any Linux/macOS system and Termux (Android).

## Installation

```bash
git clone https://github.com/amrk61763-ops/PHANTOM.git
cd PHANTOM
chmod +x phantom.sh
```

## Usage

### Hide a file inside an image
```bash
bash phantom.sh hide
# Enter: file path, cover image path, encryption password
# Output: ~/Downloads/hidden.jpg
```

### Reveal a hidden file
```bash
bash phantom.sh reveal
# Enter: steg image path, encryption password
# Output: ~/Downloads/revealed_file
```

## Demo

```
$ bash phantom.sh hide
msaar elmlf: /home/user/secret.pdf
msaar elcover: /home/user/photo.jpg
Encryption...
covering
khlas_kda — hidden.jpg in Downloads

$ bash phantom.sh reveal
msaar elcover: /home/user/hidden.jpg
Enter AES-256-CBC decryption password:
khlas_kda malaf in Downloads
```

## Warning

> This tool is for educational purposes and personal use only.
> The author is not responsible for any misuse.

## Author

**Amr Khaled** — [@amrk61763-ops](https://github.com/amrk61763-ops)
