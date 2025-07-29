# LinkMod: The Ultimate Command-Line URL Tool



**LinkMod** is a powerful and flexible command-line tool that enhances your URL management workflow. It offers two primary functionalities:

1.  **Bitly URL Shortening**: Quickly shorten long URLs using the Bitly API.
2.  **Custom Link Naming**: Create memorable, custom-named links in the format `custom-name@your-link.com`.

When you provide a long URL and a custom name, LinkMod will first shorten the URL with Bitly (if an API key is available) and then create a custom link with the shortened URL.

## Features

-   **Seamless Bitly Integration**: Shorten URLs with a single command.
-   **Secure API Key Storage**: Your Bitly API key is stored securely in your system's native credential manager using the `keyring` library.
-   **Cross-Platform**: Works on Windows, macOS, and Linux.
-   **User-Friendly Prompts**: The tool guides you through setting up your Bitly API key for the first time.
-   **Flexible Usage**: Use either the URL shortening, the custom link naming, or both combined.

## Installation

You can install LinkMod using `pip`:

```bash
pip install .
```

This will install the package and all its dependencies (`requests` and `keyring`).

## Usage

LinkMod's functionality changes based on the number of arguments you provide.

### 1. Shorten a URL with Bitly

To shorten a long URL, simply provide it as a single argument:

```bash
linkMod {long_url}
```

**Example:**

```bash
linkMod https://www.github.com/Rishi-Bhati/linkmod
```

**Output:**

```
Short link: https://bit.ly/xxxxxxx
```

### 2. Create a Custom Link (with optional Bitly shortening)

To create a custom-named link, provide the original URL and your desired custom name:

```bash
linkMod {long_url} {custom_name}
```

**Example:**

```bash
linkMod https://www.github.com/Rishi-Bhati/linkmod my-repo
```

**Output:**

```
Checking for Bitly API key...
Bitly API key found. Shortening link...
Link shortened successfully.
my-repo@bit.ly/xxxxxxx
```

If no Bitly API key is found, the tool will use the original link:

```
Checking for Bitly API key...
Bitly API key not found. Using original link.
my-repo@www.github.com/Rishi-Bhati/linkmod
```

### 3. Set/Update Your Bitly API Key

You can add or update your Bitly API key at any time using the `--set-key` flag:

```bash
linkMod --set-key
```

The tool will then prompt you to enter your new API key.

## 🔧 Setup Notes (if `linkMod` command is not found)

If you installed the package but `linkMod` is not recognized as a command, try the following:

### On Linux/macOS:
Ensure `~/.local/bin` is in your PATH:

```bash
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

Or run this for the current terminal session:

```bash
export PATH="$HOME/.local/bin:$PATH"
```

### On Windows:

Ensure the following folder is in your system PATH:

`C:\Users\<YourUsername>\AppData\Roaming\Python\Python3X\Scripts`

Or wherever Python installs your packages.

You may need to restart the terminal or system after adding to PATH.

---

### 2. ✅ Optional: Add a `post_install` Script (Advanced)

Python packaging **does not officially support** automatic post-install hooks (like modifying `PATH`) due to security and portability reasons. So this isn't a reliable method, especially for PyPI packages.

Instead, documentation is the correct and clean way.

---

### 3. ✅ Use a Desktop Shortcut or `.bat` File (Windows Only)

For users on Windows:
- You can suggest creating a simple `.bat` file in a folder already in `PATH`.
  
**Example `linkMod.bat`:**
```bat
@echo off
python -m linkmod.linkmod %*
```

Place this in `C:\Windows\` or any folder in `PATH`.

## Contributing

Contributions are welcome! Please feel free to submit a pull request or open an issue on the [GitHub repository](https://github.com/Rishi-Bhati/linkmod.git).

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
