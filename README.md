
# Rem God Catcher ❄️

Rem God Catcher is a powerful, cross-platform image downloading tool designed to interact with various imageboard APIs. It features a modern, glass-morphism Web UI (powered by Eel) and a robust Python backend capable of batch-downloading images with advanced tag filtering.

## 🌟 Features

* **Multi-Platform Support:** Built-in modules for Rule34, Safebooru, Zerochan, Waifu.im, and Nekos.best.
* **Modern GUI:** A sleek, dark-themed web interface with a built-in terminal log and tabbed navigation.
* **Advanced Search Logic:** * Support for `AND` & `OR` (`~`) tag queries.
  * Tag exclusions (e.g., `-video`, `-gif`).
  * Custom sorting (Score, ID, Ascending, Descending).
* **Titan Engine:** Features anti-ban protections, tactical delays, and a resilient retry-loop to handle slow networks and API rate limits.
* **Cross-Platform:** Works natively on Windows, Linux, and WSL environments.

## 🛠️ Prerequisites

* Python 3.8 or higher.
* A Chromium-based browser (Google Chrome, Microsoft Edge, or Brave) for the GUI.

## 📦 Installation

1. Clone this repository:
   ```bash
   git clone [https://github.com/YourUsername/Rem-God-Catcher.git](https://github.com/YourUsername/Rem-God-Catcher.git)
   cd Rem-God-Catcher
    ```


2. Install the required Python dependencies:
```bash
pip install eel requests urllib3 customtkinter rule34Py

```



## 🚀 Usage

### 1. Graphical User Interface (GUI)

To launch the modern web interface, simply run:

```bash
python Rem_catcher.py

```

*You can configure proxy settings (e.g., v2ray) in the Pre-Flight check window before the main application starts.*

### 2. Command Line Interface (CLI)

If you prefer a lightweight terminal experience for Rule34, run:

```bash
python Rule.py

```

## ⚙️ Project Structure

* `Rem_catcher.py` - The main Eel backend and GUI launcher.
* `Rule.py` - Standalone CLI application for Rule34 downloading.
* `web/` - Contains the HTML, CSS, JavaScript, and font assets for the frontend.
* `safe_tag_names.json` - Offline database for Safebooru tag autocomplete.

## ⚠️ Disclaimer & Terms of Use

* **Educational Purposes:** This software is provided for educational and archiving purposes only.
* **NSFW Content:** Some of the APIs supported by this tool index Not Safe For Work (NSFW) content. Users must be of legal age in their jurisdiction to use the tool for such purposes.
* **API Limits:** This tool is designed to respect the target servers by using rate-limiting and tactical pauses. Please do not modify the code to aggressively spam requests, as this may result in your IP being permanently banned by the imageboard providers.
```

Push it to GitHub with pride! You built a great tool.

