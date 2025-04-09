

---

# 📡 Link2Proxy 📡

## Introduction

Welcome to **Link2Proxy**, a Python module that allows you to easily fetch and rotate proxies automatically. Whether you're scraping websites or need proxies for testing purposes, **Link2Proxy** helps you get free proxies from multiple sources, store them locally, and use them to make requests.

## 📝 Installation

To install **Link2Proxy**, you can clone this repository or install it via `pip` once the module is uploaded to PyPI.

```bash
pip install link2proxy
```

## 🔧 Usage

### `get_proxies()`

This function allows you to fetch proxies from multiple online sources and store them locally in a file.

#### Example:

```python
import link2proxy

# Fetch proxies from the available sources and save them to a file
link2proxy.get_proxies()
```

- **Description**: 
  - Fetches proxies from various online sources (e.g., spys.me, sslproxies.org, etc.).
  - Proxies are stored in a local file (`link2proxy.txt`).
  - This is useful if you need to periodically refresh your proxy list.

- **Parameters**:
  - No parameters are needed.

- **Returns**:
  - No return value. The proxies are saved in the local file.

---

### `get_proxy()`

This function retrieves a proxy from the local file where they are stored. If the file is empty, it will automatically call `get_proxies()` to populate the list with fresh proxies.

#### Example:

```python
import link2proxy

# Get a proxy and use it for a request
proxy = link2proxy.get_proxy()
print(requests.get('https://google.com', proxies=proxy).status_code)
```

- **Description**:
  - Fetches one proxy from the saved list (stored in `link2proxy.txt`).
  - If the file is empty, it triggers `get_proxies()` to fetch fresh proxies.

- **Parameters**:
  - No parameters are needed.

- **Returns**:
  - A dictionary containing a proxy for both `http` and `https`:
    ```python
    {"http://": "http://<proxy>", "https://": "https://<proxy>"}
    ```

---

## 📄 File Structure

The proxies are stored in a file called `link2proxy.txt` inside a folder called `proxies` in the root directory of your project. This file will contain a list of proxies in the format `ip:port`.

Example of file structure:
```
/project_directory
  /proxies
    link2proxy.txt
```

## ⚠️ Disclaimer

- **Please use this program only for educational purposes.**
- **It is not meant to be used in any malicious way, and I decline any responsibility for what you do with it.**

---

### <p align="center">🔗 Connect with Zarby 🔗</p>
