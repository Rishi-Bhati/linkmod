# LinkMod v0.2: The Power Update!

This release marks a major evolution for LinkMod, transforming it from a simple link customizer into a powerful, all-in-one URL management tool. We've integrated Bitly for seamless URL shortening, added secure API key management, and enhanced the command-line interface for a more robust user experience.

## ✨ What's New

*   **Bitly URL Shortening**: You can now shorten long URLs directly from your command line. If you provide a single URL, LinkMod will return a shortened Bitly link.
*   **Combined Power**: The original custom naming functionality now works in tandem with Bitly. When you provide a URL and a custom name, LinkMod will first shorten the link and then apply your custom name to the shortened version (e.g., `my-repo@bit.ly/xxxxxxx`).
*   **Secure API Key Management**: We've integrated the `keyring` library to securely store your Bitly API key in your system's native credential manager. No more plain text keys!
*   **Dedicated API Key Setter**: A new `--set-key` flag has been added, allowing you to add or update your Bitly API key at any time, without having to wait for a prompt.
*   **Robust Error Handling**: The tool now gracefully handles network errors, such as connection failures or timeouts when communicating with the Bitly API, and will fall back to using the original URL if shortening fails.

## 🚀 Enhancements

*   **Improved Command-Line Interface**: The CLI is now more intuitive, with clear usage instructions for all available commands.
*   **Comprehensive README**: The `README.md` has been completely overhauled with detailed instructions, usage examples, and troubleshooting tips for common setup issues.

## How to Use the New Features

*   **Shorten a URL**: `linkMod {long_url}`
*   **Shorten and Customize**: `linkMod {long_url} {custom_name}`
*   **Set/Update API Key**: `linkMod --set-key`

Thank you for using LinkMod! We hope you enjoy these new features.
