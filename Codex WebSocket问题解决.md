WebSocket协议跳过：

#### 方案1：
    在.codex目录（windows对应目录C:\Users\Administrator.codex）新建一个.env文件内容为：

```bash
HTTP_PROXY="http://127.0.0.1:10809"
HTTPS_PROXY="http://127.0.0.1:10809"
ALL_PROXY="socks5://127.0.0.1:10808"
```

#### 方案2：
    在 ~/.codex/config.toml（windows对应目录C:\Users\Administrator.codex）中加入以下几行：

```bash
model_provider = "openai_http"     
 
[model_providers.openai_http]
name = "OpenAI HTTP only"
wire_api = "responses"
supports_websockets = false
```

 **或者：**

```bash
model_provider = "openai_https"
 
[model_providers.openai_https]
name = "OpenAI"
requires_openai_auth = true
supports_websockets = false
```

**ps** : model_provider="openai_http"要放在配置文件开头，保证层级在最外侧。

