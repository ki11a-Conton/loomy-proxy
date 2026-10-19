# loomy-proxy v2.1.1

Loomy（龙虾）桌面客户端的**本地网关反代**，把客户端授权转成 OpenAI 兼容接口，供本机工具（如 DeepSeek Harness）调用。

> 个人自用项目，与讯飞 / Loomy 官方无关。仅转发**你自己账号**的授权，请勿用于批量注册、共享账号或违反服务条款的用途。

## 下载

| 文件 | 大小 | SHA256 |
| --- | --- | --- |
| [`dist-zip/loomy-proxy-v2.1.1.zip`](dist-zip/loomy-proxy-v2.1.1.zip) | 69,706 B | `33A7273804111944C621CFAB604CE9D87577A27F22603659B78DAC9CFBE5CB3A` |

## 快速开始

1. 解压 zip，进入目录；
2. `start-all.cmd`（一键：反代 `http://127.0.0.1:8790/v1` + 网页登录 `127.0.0.1:8791`，幂等，已在跑就跳过）；
3. 也可以分开启动：`start-loomy-proxy.cmd`（只启反代）、`start-loomy-login.cmd`（网页短信登录换 session）；
4. `start-loomy-daily.cmd`（可选：每日任务/签到，默认只读，`--apply` 才领取）；
5. 详细说明见包内 `README.md`（部署/使用/致谢/免责声明）与 `README.detailed.md`（实现与验证记录）。

## 版本

- **v2.1.1**：新增 `start-all.cmd` 一键启动（反代 + 网页登录一起拉起，按 `/health` 探测幂等）+ 文档更新；代码逻辑与 v2.1.0 相同（`/health` 里的 `version` 仍是 `2.1.0`）。
- v2.1.0：账号池 + 额度感知选号 + 故障转移 + 流式透传 + 管理面板（含「今日签到」卡片）+ 网页登录 + 签到脚本。