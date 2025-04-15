# optimize-img

A lightning-fast image optimization tool for macOS that makes your images web-ready in seconds!

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

## 📖 Description

`optimize-img` is a powerful tool to optimize PNG, JPEG, and WebP images for web use. This script can reduce image file sizes without significant quality loss and optionally convert images to the WebP format.

## 🔧 Installation

### Requirements

- macOS
- [Homebrew](https://brew.sh/) for installing dependencies
- Required packages:
  - `pngquant` - for PNG optimization
  - `jpegoptim` - for JPEG optimization
  - `webp` - for WebP conversion and optimization

### Installing Dependencies

```bash
brew install pngquant jpegoptim webp
```

### Quick Installation

Install `optimize-img` with a single command:

```bash
curl -O https://raw.githubusercontent.com/alecscodes/optimize-img/master/optimize-img && chmod u+x optimize-img && sudo cp optimize-img /usr/local/bin
```

### Manual Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/alecscodes/optimize-img.git
   cd optimize-img
   ```

2. Make the script executable:

   ```bash
   chmod u+x optimize-img
   ```

3. Move it to your PATH:

   ```bash
   sudo cp optimize-img /usr/local/bin
   ```

## 📋 Usage

```
optimize-img [options] [image_files]
```

### Arguments

| Argument | Description |
|----------|-------------|
| `[image_files]` | Optional. Specific image files to optimize. If not provided, all images in current directory will be processed. Supports PNG, JPEG, WebP, and SVG formats. |

### Options

| Option | Description |
|--------|-------------|
| `-h, --help` | Display help message and exit. |
| `--no-backup` | Skip creating backup files of original images. Default behavior creates [filename]-old.[ext] backup files. Use this to save disk space when you have version control or don't need the original files. |
| `--webp` | Convert images to WebP format while preserving originals. Creates a new .webp file alongside each original with 80% quality. The original files remain unchanged when used alone. WebP provides superior compression for web use compared to traditional formats. |

### Option Combinations

| Combination | Description |
|-------------|-------------|
| `--webp --no-backup` | Convert to WebP format while also optimizing originals without creating backups of the originals. |
| `[no options]` | Optimize all images in current directory and create backups of the original files for safety. |

### File Handling

| Format | Optimization Method |
|--------|---------------------|
| PNG | Optimized with pngquant (65-80% quality, strip metadata) |
| JPEG | Optimized with jpegoptim (80% quality, strip metadata) |
| WebP | Recompressed to 80% quality |
| SVG | No optimization performed (detected only) |

### Examples

```bash
# Optimize all images in current directory
optimize-img

# Optimize specific image files
optimize-img image1.png image2.jpg

# Optimize all images without creating backups
optimize-img --no-backup

# Convert all images to WebP format
optimize-img --webp

# Convert to WebP without backup of original
optimize-img --webp --no-backup img.png
```

## 📊 Example Results

| Image Type | Original Size | Optimized Size | Reduction |
|------------|--------------|----------------|-----------|
| PNG        | 1.2 MB       | 280 KB         | 77%       |
| JPEG       | 800 KB       | 240 KB         | 70%       |
| WebP       | 600 KB       | 180 KB         | 70%       |

*Actual results may vary based on image content*

## ✨ Features

- 🔥 Batch optimize all images in a directory
- 🔄 Convert images to WebP format
- 🛡️ Create automatic backups of original files
- ⚙️ Easy to use with sensible defaults
- 🧩 Works with PNG, JPEG, WebP, and SVG files

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 💬 Feedback

If you have any feedback or issues, please open an issue on the [GitHub repository](https://github.com/alecscodes/optimize-img/issues).
