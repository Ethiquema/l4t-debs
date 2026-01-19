# L4T APT Repository for Nintendo Switch

APT repository mirror of [theofficialgman/l4t-debs](https://github.com/theofficialgman/l4t-debs) for Nintendo Switch Linux distributions.

## Usage

```bash
# Add GPG key
curl -fsSL https://ethiquema.github.io/l4t-debs/public.key | \
    sudo gpg --dearmor -o /usr/share/keyrings/l4t-debs.gpg

# Add repository
echo "deb [signed-by=/usr/share/keyrings/l4t-debs.gpg] https://ethiquema.github.io/l4t-debs noble main" | \
    sudo tee /etc/apt/sources.list.d/l4t-debs.list

# Update and install
sudo apt update
sudo apt install linux-image-l4t-switch linux-dtb-l4t-switch
```

## Available Packages

- `linux-image-l4t-switch` - L4T kernel for Nintendo Switch
- `linux-dtb-l4t-switch` - Device tree blobs for all Switch models

## How it works

A GitHub Action runs every 24 hours to:
1. Check if [theofficialgman/l4t-debs](https://github.com/theofficialgman/l4t-debs) has new commits
2. If changes detected, rebuild the APT repository metadata
3. Deploy to GitHub Pages

## Credits

- Kernel packages by [theofficialgman](https://github.com/theofficialgman/l4t-debs)
- Part of [switch-linux-builder](https://github.com/Ethiquema/switch-linux-builder)