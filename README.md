
# deeplx-pro-go


[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fxiaozhou26%2Fdeeplx-pro-go&env=DEEPL_COOKIES&project-name=deeplx-pro-go&repository-name=deeplx-pro-go)


使用 DeepL Pro的翻译服务

# 直接使用，畅行无阻。

## 如何使用这个镜像

### 拉取镜像

你可以使用以下命令从Docker Hub拉取这个镜像：

```bash
docker pull xiaoxiaofeihh/deeplx-pro-go:latest
```

### 运行镜像

你可以使用以下命令运行这个镜像：

![DeepL翻译API示例代码](https://jsd.cdn.zzko.cn/gh/xiaozhou26/tuph@main/images/2024-03-07%20120245.png)

```bash
docker run -d --name deeplx-pro -p 9000:9000 -e DEEPL_COOKIES="" xiaoxiaofeihh/deeplx-pro-go:latest
```
### 注：多并发只要有一个cookie失效都会影响服务
DEEPL_COOKIES=你的dl_seesion值，用,隔开
列如DEEPL_COOKIES="1560565165-1811-481,515156-561561-11651"

### 使用

- [使用API教程](https://github.com/xiaozhou26/deeplx/blob/main/API.md)


1. 替换代码中的 `cookie` 变量为你自己的 DeepL Pro cookie。
2. 运行代码，启动 Express 服务器。
3. 使用 POST 请求向 `http://localhost:9000/translate` 发送翻译请求，请求体包含以下字段：
   - `text`：要翻译的文本
   - `source_lang`：源语言（可选，默认为 'AUTO'）
   - `target_lang`：目标语言（可选，默认为 'ZH'）
   - `quality`: (字符串, 可选): 翻译质量。可以是 'normal' 或 'fast'。默认为 'normal'。

4. 服务器将返回翻译结果的 JSON 响应。

## 注意事项

- 请不要频繁发送大量请求，否则可能会被 DeepL 暂时阻止 IP。
- 本代码仅供学习和参考，请勿用于商业用途。
- 使用 DeepL 时，请遵守其使用条款和限制。

