# Dify - Zmicro Service

[![CI](https://github.com/zmicro-design/service-dify/actions/workflows/ci.yml/badge.svg)](https://github.com/zmicro-design/service-dify/actions/workflows/ci.yml)
[![GitHub issues](https://img.shields.io/github/issues/zmicro-design/service-dify.svg)](https://github.com/zmicro-design/service-dify/issues)

## 开始使用

### 安装

1. **先决条件：**确保您的系统已安装并运行 Docker。
2. **安装脚本：**运行以下命令下载并执行安装脚本：

```bash
curl https://raw.githubusercontent.com/zmicro-design/service-dify/master/install -sSL | bash -s -- dify
```

   - **解释：**
     - `curl`：从 GitHub 下载安装脚本。
     - `https://raw.githubusercontent.com/zmicro-design/service-dify/master/install`：安装脚本的 URL。
     - `-sSL`：静默下载脚本并进行 SSL 验证。
     - `bash -s -- dify`：使用 `dify` 参数（可能是用于服务标识）执行下载的脚本。

3. **登录密码：**安装过程中，系统会提示您输入登录密码。此密码可能用于容器注册表身份验证或管理 Docker 服务。

4. **配置（可选）：**安装完成后，脚本可能会提示您确认或修改 `dify` 服务的配置，例如端口和密钥。

**注意:** 考虑提及任何所需的特定 Docker 守护进程配置（例如，设置 Docker 注册表登录）。

### 常用操作

以下是用于管理 `dify` 服务的一些命令：

* **启动：**
  ```bash
  zmicro service start dify
  ```
* **停止：**
  ```bash
  zmicro service stop dify
  ```
* **查看日志：**
  ```bash
  zmicro service logs dify -f --tail 100
  ```
    - `-f`： 实时跟踪日志输出。
    - `--tail 100`： 显示最后 100 行日志。
* **编辑配置：**
  ```bash
  zmicro service edit config dify
  ```
* **重启：**
  ```bash
  zmicro service restart dify
  ```
* **升级：**
  ```bash
  zmicro service upgrade dify
  ```

## 常见问题解答

**1. 安装过程中出现网络错误**

如果您遇到类似 `curl: 连接失败...` 的网络错误，则可能需要配置终端使用代理服务（例如，`clash`）。 以下是如何操作：

1. 运行以下命令设置代理环境变量（将 `7890` 替换为您实际的代理端口）：

   ```bash
   export HTTPS_PROXY=http://127.0.0.1:7890 HTTP_PROXY=http://127.0.0.1:7890
   ```

2. 设置代理后，重新运行安装命令。

**2. 密码提示**

安装过程中的 `Password:` 提示符可能要求您输入容器注册表或 Docker 服务管理工具的登录凭据。 输入您的有效密码以继续。

**3. 读取配置文件失败：读取 /etc/api-gateway/config.yaml: 是一个目录**

为您的 Docker Desktop 添加目录权限，目录是 `/opt`

## 许可

* MIT
