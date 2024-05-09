# Dify - Zmicro Service

[![CI](https://github.com/zmicro-design/service-dify/actions/workflows/ci.yml/badge.svg)](https://github.com/zmicro-design/service-dify/actions/workflows/ci.yml)
[![GitHub issues](https://img.shields.io/github/issues/zmicro-design/service-dify.svg)](https://github.com/zmicro-design/service-dify/issues)

[中文文档](./README_CN.md)


## Getting Started

### Installation

1. **Prerequisites:** Ensure you have Docker installed and running on your system.
2. **Installation Script:** Run the following command to download and execute the installation script:

```bash
curl https://raw.githubusercontent.com/zmicro-design/service-dify/master/install -sSL | bash -s -- dify
```

   - **Explanation:**
     - `curl`: downloads the installation script from GitHub.
     - `https://raw.githubusercontent.com/zmicro-design/service-dify/master/install`: URL of the installation script.
     - `-sSL`: downloads the script silently with SSL verification.
     - `bash -s -- dify`: executes the downloaded script with `dify` argument (likely for service identification).

3. **Login Password:** During installation, you'll be prompted to enter your login password. This password is likely used for authenticating with a container registry or managing docker services.

4. **Configuration (Optional):** After installation, the script might prompt you to confirm or modify configurations like port and secret key for the `dify` service.

**Note:** Consider mentioning any specific docker daemon configuration required (e.g., setting up a Docker registry login).

### More Usage

Here are some commands for managing the `dify` service:

* **Start:**
  ```bash
  zmicro service start dify
  ```
* **Stop:**
  ```bash
  zmicro service stop dify
  ```
* **View Logs:**
  ```bash
  zmicro service logs dify -f --tail 100
  ```
    - `-f`: follows the log output in real-time.
    - `--tail 100`: shows the last 100 log lines.
* **Edit Configuration:**
  ```bash
  zmicro service edit config dify
  ```
* **Restart:**
  ```bash
  zmicro service restart dify
  ```
* **Upgrade:**
  ```bash
  zmicro service upgrade dify
  ```

## FAQ

**1. Network Error During Installation**

If you encounter a network error like `curl: Failed to connect...`, you might need to configure your terminal to use a proxy service (e.g., `clash`). Here's how:

1. Run the following command to set your proxy environment variables (replace `7890` with your actual proxy port):

   ```bash
   export HTTPS_PROXY=http://127.0.0.1:7890 HTTP_PROXY=http://127.0.0.1:7890
   ```

2. Re-run the installation command after setting the proxy.

**2. Password Prompt**

The `Password:` prompt during installation likely requests your login credentials for a container registry or docker service management tool. Enter your valid password to proceed.

**3. failed to read config file: read /etc/api-gateway/config.yaml: is a directory**

Add directory permissions for your `Docker Desktop`, directory is `/opt`

## License

* MIT
