# loomy-proxy v2.1.0

Loomy（龙虾）桌面客户端的**本地网关反代**，把客户端授权转成 OpenAI 兼容接口，供本机工具（如 DeepSeek Harness）调用。

> 个人自用项目，与讯飞 / Loomy 官方无关。仅转发**你自己账号**的授权，请勿用于批量注册、共享账号或违反服务条款的用途。

## 下载

| 文件 | 大小 | SHA256 |
| --- | --- | --- |
| [`dist-zip/loomy-proxy-v2.1.0.zip`](dist-zip/loomy-proxy-v2.1.0.zip) | 68,301 B | `5522ECB22E3414845971931EC2C5D54636D4231AA917D003BA6E438B3BE43BEB` |

## 快速开始

1. 解压 zip，进入目录；
2. `start-loomy-proxy.cmd`（反代，`http://127.0.0.1:8790/v1`）；
3. `start-loomy-login.cmd`（可选：网页短信登录换 session，`127.0.0.1:8791`）；
4. `start-loomy-daily.cmd`（可选：每日任务/签到，默认只读，`--apply` 才领取）；
5. 详细说明见包内 `README.md`（部署/使用/致谢/免责声明）与 `README.detailed.md`（实现与验证记录）。

## 版本

v2.1.0：账号池 + 额度感知选号 + 故障转移 + 流式透传 + 管理面板（含「今日签到」卡片）+ 网页登录 + 签到脚本。