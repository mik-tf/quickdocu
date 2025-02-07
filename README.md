# QuickDocu - Docusaurus Config Splitter

## Table of Contents
- [QuickDocu - Docusaurus Config Splitter](#quickdocu---docusaurus-config-splitter)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Features](#features)
  - [Installation](#installation)
    - [Option 1: Using Make (Recommended)](#option-1-using-make-recommended)
    - [Option 2: Manual Installation](#option-2-manual-installation)
  - [Usage](#usage)
    - [Using Make Commands](#using-make-commands)
    - [Direct Script Usage](#direct-script-usage)
  - [File Structure](#file-structure)
  - [How It Works](#how-it-works)
  - [Requirements](#requirements)
  - [Notes](#notes)
  - [License](#license)

## Introduction

QuickDocu is a bash script that automatically splits a Docusaurus configuration file (`docusaurus.config.ts`) into modular components, creating separate JSON configuration files for better maintainability and organization.

## Features

- Automatically extracts configuration sections from `docusaurus.config.ts`
- Creates organized JSON files for navbar, footer, and main configurations
- Generates a new modular configuration file
- Maintains all original functionality while improving code organization
- Easy to use with Make commands or direct script execution
- System-wide installation option

## Installation

### Option 1: Using Make (Recommended)
```bash
git clone https://github.com/mik-tf/quickdocu.git
cd quickdocu
make build
```

### Option 2: Manual Installation
```bash
curl -O https://raw.githubusercontent.com/mik-tf/quickdocu/main/quickdocu.sh
chmod +x quickdocu.sh
sudo ./quickdocu.sh install
```

## Usage

### Using Make Commands

1. Install QuickDocu:
```bash
make build
```

2. Reinstall/Rebuild QuickDocu:
```bash
make rebuild
```

3. Uninstall QuickDocu:
```bash
make delete
```

### Direct Script Usage

Once installed, you can run QuickDocu in any directory containing a `docusaurus.config.ts` file:

```bash
quickdocu
```

Or use the script directly without installation:
```bash
./quickdocu.sh
```

## File Structure

After running QuickDocu, you'll have the following structure:

```
your-docusaurus-project/
├── docusaurus.config.ts       # Original config file
├── docusaurus1.config.ts      # New modular config file
└── cfg/
    ├── navbar.json           # Navigation bar configuration
    ├── footer.json          # Footer configuration
    └── main.json           # Main site configuration
```

## How It Works

1. The script first validates the presence of `docusaurus.config.ts`
2. Creates a `cfg` directory if it doesn't exist
3. Extracts configuration sections:
   - Navbar configuration to `cfg/navbar.json`
   - Footer configuration to `cfg/footer.json`
   - Main site settings to `cfg/main.json`
4. Generates a new `docusaurus1.config.ts` that imports these JSON files

## Requirements

- Node.js installed on your system
- A valid Docusaurus project with `docusaurus.config.ts`
- Make (for using Makefile commands)
- sudo privileges (for system-wide installation)

## Notes

- The script preserves all original configuration values
- Backup your original configuration file before running the script
- The script assumes a standard Docusaurus configuration structure
- System-wide installation requires sudo privileges
- If your configuration file has custom sections, you may need to modify the script

---

For more information or to report issues, please visit [our GitHub repository](https://github.com/mik-tf/quickdocu).

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.