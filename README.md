# Weirdhost Auto Renew

自动为 [Weirdhost](https://hub.weirdhost.xyz/) 服务器续期的小工具，支持使用 Cookie 或邮箱/密码登录，并在续期成功后发送 Telegram 通知，包括最新到期时间。

---

## 功能

- ✅ 优先使用 Cookie 登录（`REMEMBER_WEB_COOKIE`），Cookie 失效自动回退邮箱/密码登录
- ✅ 支持邮箱/密码登录（`PTERODACTYL_EMAIL` + `PTERODACTYL_PASSWORD`）
- ✅ 自动点击服务器页面上的 “시간 추가” / “Add Time” 按钮完成续期
- ✅ 获取续期后的最新到期时间（基于页面文本匹配 `유통기한`）
- ✅ 支持 Telegram 通知（文本 + 异常截图）
- ✅ 异常处理完善，失败时截图并发送通知

---

## 环境变量说明

| 变量名 | 描述 | 是否必需 |
|--------|------|-----------|
| `REMEMBER_WEB_COOKIE` | Cookie 的值，用于优先登录（可选） | 否 |
| `REMEMBER_WEB_COOKIE_NAME` | Cookie 名称，默认 `remember_web` | 否 |
| `PTERODACTYL_EMAIL` | 邮箱，用于回退登录 | 如果 Cookie 不可用则必需 |
| `PTERODACTYL_PASSWORD` | 密码，用于回退登录 | 如果 Cookie 不可用则必需 |
| `SERVER_URL` | 目标服务器 URL（默认脚本内有默认值） | 否 |
| `TG_BOT_TOKEN` | Telegram Bot Token，用于发送通知 | 否 |
| `TG_CHAT_ID` | Telegram Chat ID，用于发送通知 | 否 |
| `TWOCAPTCHA_API_KEY` | 可选，用于未来打码服务 | 否 |

---

## 使用方法

### 1. 克隆仓库

```bash
git clone <repo-url>
cd weirdhost-auto-add-time
