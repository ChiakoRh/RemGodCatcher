# Changelog

All notable changes to Rem God Catcher will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

---

## [2.0.0] - 2025-01-01

### Major Changes

- **Migrated from Eel to Flask + Socket.IO** -- The Web UI no longer requires Chrome/Chromium. It now opens in your default browser via a local Flask server.
- **Added Web-based Proxy Configuration** -- Proxy settings (enable/disable, URL, TLS verify) are now configurable directly from the Web UI's Main tab. Settings persist in `.env`.

### Added

- **API Keys Tab** -- New tab in the Web UI to manage Rule34 API credentials without editing code.
- **Socket.IO Real-Time Logging** -- Console logs are pushed to the browser via WebSocket for instant feedback.
- **Waifu.im Tag Database (`tags.json`)** -- Local tag database with name-to-slug conversion. Typing "Genshin Impact" now correctly sends "genshin-impact" to the API.
- **Persistent Proxy Settings** -- Proxy configuration is saved to `.env` and restored on restart.
- **Google Fonts Integration** -- Inter font loaded from Google Fonts CDN for a modern, clean UI.
- **Custom Scrollbar Styling** -- Scrollbar appearance customized for the console log panels.
- **Input Focus States** -- Added focus ring animations on input fields for better UX.
- **Checkbox Styling** -- Checkboxes now use the cyan accent color to match the theme.

### Fixed

- **Font Path Mismatch** -- CSS referenced `Playfair-VariableFont_wdth,opsz.ttf` but the actual file was `PlayfairDisplay-VariableFont_wght.ttf`. Both CSS and Python font loading paths corrected.
- **Input Border Color Bug** -- CSS had `rgba(255, 255, 25, 0.3)` (missing a `2` in the green channel). Fixed to `rgba(255, 255, 255, 0.3)`.
- **Console Log XSS** -- Replaced `innerHTML += text\n` with `document.createElement("div")` to prevent HTML injection in log messages.
- **Hardcoded API Keys** -- Removed hardcoded `api_key` and `user_id` from source code. Moved to `.env` file via `python-dotenv`.
- **Rule34 API Key Format** -- Fixed `client.api_key` format. The library expects raw key string, not `&api_key=...` prefix (the library adds params internally).
- **Rule34 Proxy Injection** -- Proxy settings are now injected into `rule34Py`'s internal session via `client.session.proxies`.
- **Waifu.im NSFW Parameter** -- Changed `"True"` to `"true"` for `IsNsfw` parameter (API requires lowercase).
- **Waifu.im Empty Results Message** -- Now shows available tags when a tag doesn't exist, instead of generic "End of database reached".
- **Safebooru Parentheses in Tags** -- Parentheses in tag names (e.g., `femboy_hooters_(meme)`) are now stripped to prevent URL encoding issues.
- **Safebooru Cloudflare Handling** -- Improved error messaging for 403 responses (Cloudflare blocks).
- **Removed Unused Global Variables** -- Cleaned up `RULE34_API_KEY` and `RULE34_USER_ID` global references.

### Changed

- **Font**: Replaced Playfair + MonoLisa with **Inter** (Google Fonts) for the UI. Console uses JetBrains Mono/Consolas fallback.
- **CSS**: Complete rewrite with glass-morphism improvements, better spacing, hover effects, and dark theme refinements.
- **HTML**: Added viewport meta tag, Socket.IO CDN script, and restructured tab content.
- **JavaScript**: Full rewrite -- all `eel.xxx()` calls replaced with `fetch()` REST API + `socket.emit()` for WebSocket events.
- **Python**: Removed `eel`, `customtkinter` dependencies. Added `flask`, `flask-socketio`, `webbrowser`. Removed tkinter startup config window (now in Web UI).
- **README**: Rewritten with badges, project structure, platform comparison table, and setup instructions.
- **.env**: Added `USE_PROXY`, `PROXY_URL`, `VERIFY_TLS` fields alongside API keys.

### Removed

- **CustomTkinter Startup Window** -- The pre-flight network config window (tkinter) was removed. All settings are now in the Web UI.
- **`eel` dependency** -- No longer required. Replaced by Flask + Socket.IO.
- **`customtkinter` dependency** -- No longer required.

---

## [1.0.0] - 2024-12-01

### Added

- Initial release with Eel-based Web UI.
- Support for Rule34, Safebooru, Zerochan, Waifu.im, and Nekos.best.
- CustomTkinter startup configuration window.
- Glass-morphism dark theme with tabbed navigation.
- Tag auto-suggestion for all platforms.
- AND/OR tag query support with exclusions.
- Anti-ban engine with tactical delays and retry loops.
- Download history tracking via JSON files.
