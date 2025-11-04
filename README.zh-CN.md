# tiktok-api
TikTok,tiktok,TikTok API,tiktok API,tiktok api
---

[English](README.md) | [简体中文](README.zh-CN.md)

# Just One API - Python SDK

官方 Python SDK，用于访问 [Just One API](https://justoneapi.com) —— 一个统一的数据服务平台，提供来自小红书、淘宝、抖音、快手、哔哩哔哩、微博等社交、电商平台的结构化数据。

该 SDK 简化了 API 调用与签名流程，让开发者能够以最少的配置快速获取各平台数据。

---

## 🚀 安装

通过 PyPI 安装：

```bash
pip install justoneapi
```

---

## 🛠 快速开始

```python
from justoneapi.client import JustOneAPIClient

# 默认使用 “cn”（中国大陆）环境
client = JustOneAPIClient(token="your_token")
# 若您位于中国大陆以外地区，访问速度较慢，可切换至 “global” 环境以获得更佳性能：
# client = JustOneAPIClient(token="your_token", env="global")

# 示例：获取抖音视频详情
result, data, message = client.douyin.get_video_detail_v2(video_id="7428906452091145483")
print(result)
print(data)
print(message)

# 示例：抖音视频搜索
result, data, message, has_next_page = client.douyin.search_video_v4(keyword="deepseek", sort_type="_0", publish_time="_0", duration="_0", page=1)
print(result)
print(data)
print(message)
print(has_next_page)
```

### 📦 返回值说明

每个 API 方法会返回以下一个或多个值：

| 变量名 | 类型 | 说明 |
|--------|------|------|
| `result` | `bool` | 请求是否成功。`True` 表示成功，`False` 表示失败。 |
| `data` | `dict` / `list` | 实际返回的数据，结构因接口而异。 |
| `message` | `str` | 服务器返回的信息；当请求失败时包含错误说明。 |
| `has_next_page` | `bool` | 仅分页接口返回，表示是否还有下一页数据。 |

---

## 🔐 身份认证

所有 API 请求均需携带有效的 API Token。  
👉 [注册获取 Token](https://justoneapi.com/register)

---

## 📚 文档中心

👉 完整 API 文档：[接口文档](https://doc.justoneapi.com)

内容包括：
- 请求参数
- 返回字段
- 错误码说明

---

## 🏠 官方网站

👉 [官方网站](https://justoneapi.com)

了解更多项目介绍、数据来源及商业集成方案。

---

## 📬 联系我们

如有任何问题、反馈或合作意向，欢迎联系：  
👉 [联系我们](https://justoneapi.com/contact)

---

## 🪪 许可证

本项目基于 MIT 开源许可证发布。  
详情参见 [LICENSE](./LICENSE) 文件。
