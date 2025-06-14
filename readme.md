# Weibo Blacklist Enhanced Lite

轻量版微博黑名单增强工具 - 专注于黑名单功能的油猴脚本

---

## 项目简介

## **Weibo Blacklist Enhanced Lite** 是一个专注于黑名单功能的轻量版微博增强工具。通过全接口劫持技术，确保您在微博的任何地方都看不到黑名单用户的任何内容，包括原创微博、转发、评论等。

## 核心功能

| 功能类别       | 详细说明                                                                                                                                                     |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **黑名单同步** | • 首次运行：可选择全量同步（约 300ms 节流，自动重试 418 错误）<br>• 日常使用：增量同步（仅第一页，约 2.5KB）<br>• 三种同步模式：增量更新、五页同步、全量同步 |
| **全接口过滤** | • Fetch/XHR/WebSocket 全覆盖拦截<br>• 实时过滤微博流、评论区、转发列表<br>• MutationObserver 监听动态内容                                                    |
| **数据持久化** | • UID 列表存储在油猴本地存储<br>• SPA 路由自动重连<br>• 支持黑名单增删操作实时同步                                                                           |
| **Star 提醒**  | • 时间间隔策略：首次安装 →7 天 →30 天 →90 天<br>• 智能弹窗拦截处理<br>• 用户可手动关闭提醒                                                                   |

---

## 安装方法

1. 在浏览器中安装 **[Tampermonkey](https://www.tampermonkey.net/)**
2. 访问 [Greasyfork](https://greasyfork.org/) 搜索 "Weibo Blacklist Enhanced Lite" 并安装
3. 或者访问 [GitHub Releases](https://github.com/DanielZenFlow/Weibo-Blacklist-Enhanced-Lite/releases) 下载最新版本
4. 刷新微博页面即可使用

---

## 使用说明

### 油猴菜单命令

| 命令               | 功能                 | 使用场景           |
| ------------------ | -------------------- | ------------------ |
| **🔄 更新黑名单**  | 增量同步（第一页）   | 日常使用           |
| **📄 同步前五页**  | 获取前五页数据       | 频繁拉黑时使用     |
| **🔄 全量同步**    | 完整重新扫描         | 新账号或大量变更后 |
| **⭐ 给我们 Star** | 打开 GitHub 项目页面 | 支持项目发展       |

### 可调整参数

| 变量          | 默认值 | 用途                  |
| ------------- | ------ | --------------------- |
| `THROTTLE_MS` | `300`  | API 调用间隔（毫秒）  |
| `MAX_RETRIES` | `3`    | 连续 418 错误重试上限 |

---

## 常见问题

<details>
<summary>为什么节流间隔设置为300ms？</summary>

测试显示，20-30 个快速连续请求经常触发微博的反爬虫机制，返回 HTTP 418 错误。
300ms 的延迟可以有效避免这些限制。如果仍然遇到 418 错误，可以增加这个值。

</details>

<details>
<summary>数据存储在哪里？</summary>

黑名单数据存储在油猴脚本的本地存储中，不会上传到任何服务器。
浏览器重装后数据会丢失，建议定期备份油猴设置。

</details>

---

## 技术特点

- **轻量化设计**：专注核心功能，减少冲突风险
- **全接口覆盖**：Fetch/XHR/WebSocket 三重拦截
- **性能优化**：防抖 MutationObserver，智能节流
- **错误处理**：完善的重试机制和降级策略
- **用户友好**：简洁的菜单设计，智能提醒系统

---

## 贡献指南

欢迎提交 Pull Request 和 Issue 报告。  
请确保代码通过 ESLint/Prettier 检查，并包含简洁的测试说明。

---

## 许可证

本项目采用 **MIT License** 许可证。详见 `LICENSE` 文件。

---

## 致谢

感谢所有使用和支持本项目的用户！如果这个工具对您有帮助，请考虑给我们一个 ⭐ Star！

# Weibo Blacklist Enhanced Lite

Lightweight Weibo blacklist enhancement tool - Tampermonkey userscript focused on blacklist functionality

---

## Project Summary

**Weibo Blacklist Enhanced Lite** is a lightweight version of Weibo enhancement tool that focuses solely on blacklist functionality. Through comprehensive API interception, it ensures that blacklisted users' content is completely hidden from your Weibo experience, including original posts, reposts, and comments.

---

## Key Features

| Category                      | Details                                                                                                                                                                                                     |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Blacklist Synchronization** | • First run: optional full sync (~300ms throttling, auto-retry on HTTP 418)<br>• Daily use: incremental sync (first page only, ~2.5KB)<br>• Three sync modes: incremental update, five-page sync, full sync |
| **Complete API Filtering**    | • Full coverage of Fetch/XHR/WebSocket interception<br>• Real-time filtering of timeline, comments, repost lists<br>• MutationObserver for dynamic content monitoring                                       |
| **Data Persistence**          | • UID list stored in Tampermonkey local storage<br>• Auto-reconnection on SPA navigation<br>• Real-time sync of blacklist add/remove operations                                                             |
| **Star Reminder System**      | • Time-interval strategy: first install → 7 days → 30 days → 90 days<br>• Smart popup blocking handling<br>• User can manually disable reminders                                                            |

---

## Installation

1. Install **[Tampermonkey](https://www.tampermonkey.net/)** in your browser
2. Visit [Greasyfork](https://greasyfork.org/) and search for "Weibo Blacklist Enhanced Lite"
3. Or visit [GitHub Releases](https://github.com/DanielZenFlow/Weibo-Blacklist-Enhanced-Lite/releases) to download the latest version
4. Refresh your Weibo tabs to activate the script

---

## Usage

### Tampermonkey Menu Commands

| Command                      | Function                      | Use Case                           |
| ---------------------------- | ----------------------------- | ---------------------------------- |
| **🔄 Update Blacklist**      | Incremental sync (first page) | Daily routine                      |
| **📄 Sync First Five Pages** | Fetch five pages of data      | When frequent blocking is expected |
| **🔄 Full Blacklist Sync**   | Complete rescan               | New account or major changes       |
| **⭐ Give us Star**          | Open GitHub project page      | Support project development        |

### Adjustable Parameters

| Variable      | Default | Purpose                          |
| ------------- | ------- | -------------------------------- |
| `THROTTLE_MS` | `300`   | API call interval (milliseconds) |
| `MAX_RETRIES` | `3`     | Consecutive HTTP 418 retry limit |

---

## FAQ

<details>
<summary>Why is the throttling interval set to 300ms?</summary>

Testing shows that 20-30 rapid consecutive requests often trigger Weibo's anti-bot mechanisms, returning HTTP 418 errors.
A 300ms delay effectively eliminates these blocks. Increase this value if you continue to receive 418 errors.

</details>

<details>
<summary>Where is the data stored?</summary>

Blacklist data is stored in Tampermonkey's local storage and is never uploaded to any server.
Data will be lost if you reinstall your browser, so regular backup of Tampermonkey settings is recommended.

</details>

---

## Technical Features

- **Lightweight Design**: Focus on core functionality, reduced conflict risk
- **Complete API Coverage**: Triple interception of Fetch/XHR/WebSocket
- **Performance Optimized**: Debounced MutationObserver, intelligent throttling
- **Error Handling**: Comprehensive retry mechanism and fallback strategies
- **User Friendly**: Clean menu design, intelligent reminder system

---

## Contributing

Pull requests and issue reports are welcome.  
Please ensure code passes ESLint/Prettier checks and include concise test notes.

---

## License

Released under the **MIT License**. See `LICENSE` for details.

---

## Acknowledgments

Thanks to all users who use and support this project! If this tool helps you, please consider giving us a ⭐ Star!
