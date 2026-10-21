# loomy-proxy v2.2.0

Loomy（龙虾）桌面客户端的**本地网关反代**，把客户端授权转成 OpenAI 兼容接口，供本机工具（如 DeepSeek Harness）调用。

> 个人自用项目，与讯飞 / Loomy 官方无关。仅转发**你自己账号**的授权，请勿用于批量注册、共享账号或违反服务条款的用途。

## 下载

| 文件 | 大小 | SHA256 |
| --- | --- | --- |
| [`dist-zip/loomy-proxy-v2.2.0.zip`](dist-zip/loomy-proxy-v2.2.0.zip) | 82,201 B | `F1AD10C32CA476975723C7C7D8048E35C20F88D56BABB672A190F3736946AC78` |

## 快速开始

1. 解压 zip，进入目录；
2. `start-all.cmd`（一键：反代 `http://127.0.0.1:8790/v1` + 网页登录 `127.0.0.1:8791`，幂等，已在跑就跳过）；两个服务以后台 detached 进程启动，关掉窗口不会停服务；
3. 停止：`stop-all.cmd`；日志：`logs\proxy.log`、`logs\web-auth.log`；
4. 也可以分开启动：`start-loomy-proxy.cmd`（只启反代）、`start-loomy-login.cmd`（网页短信登录换 session）；
5. `start-loomy-daily.cmd`（可选：每日任务/签到，默认只读，`--apply` 才领取）；
6. 详细说明见包内 `README.md`（部署/使用/致谢/免责声明）与 `README.detailed.md`（实现与验证记录）。

## 版本

- **v2.2.0**：新增**客户端身份层**——按 Loomy 0.9.39 源码复刻 `traceparent`、`ChatId` / `MsgId` / `TurnId`、`X-Loomy-Request-Purpose`、`InvokeOrigin`、`loomy-version`、真实 Chrome UA 与稳定设备指纹；反代与签到脚本统一走 `lib/loomy-client.mjs`（零新增依赖），新增 `/fingerprint` 排障端点。`/health` 报 `2.2.0`。
- **v2.1.2**：启动器重做——服务改为后台 detached 进程 + 文件日志（关窗口不再杀进程），新增 `stop-all.cmd`。
- **v2.1.1**：新增 `start-all.cmd` 一键启动（反代 + 网页登录一起拉起，按 `/health` 探测幂等）。
- v2.1.0：账号池 + 额度感知选号 + 故障转移 + 流式透传 + 管理面板（含「今日签到」卡片）+ 网页登录 + 签到脚本。