# meeting-minutes-generator# 📋 会议纪要整理器

> 速记 / 录音转写稿 → 结构化纪要，一键生成可直接发送的会议记录

**在线使用** → [jotarou.com/tools/meeting-minutes/](https://jotarou.com/tools/meeting-minutes/)

---

## 功能概览

### 📝 结构填写（免费，无需 Key）

- **6 种会议类型**：周会 / 项目例会 / 复盘会 / 评审会 / 临时沟通 / 自定义，自动展开对应附加字段
- **双模式议题录入**：卡片逐条填写 或 大文本极速录入（空行/`–` 分隔自动解析）
- **待办事项表格**：自然语言快捷解析（"张三下周五前提交方案"→ 拆解填入）+ ⚠️ 遗留问题自动并入待办
- **草稿自动保存**：议题卡片、待办事项、基本信息全部实时存入本地，刷新不丢

### ✨ AI 整理（需 API Key）

- **流式输出**：逐字实时渲染，Markdown 模式下边生成边排版，无等待焦虑
- **发言人映射**：`说话人1=张总, 说话人2=小李` → 精准分配待办责任人
- **3 档详细度**：详细版 / 精简版 / 仅决议+待办
- **内容保留策略**：保留分歧与讨论过程 或 仅合并最终共识（评审会场景必备）
- **长文本支持**：Token 进度条实时提示，支持 2 小时以上录音转写稿

### 📤 输出与复制

| 格式 | 说明 |
|------|------|
| 纯文本 | 直接粘贴进钉钉 / 飞书 / 微信群 |
| Markdown | 粘贴进 Notion / 飞书文档 / 语雀 |
| 邮件版 | 自动生成主题行 `【会议纪要】日期 - 类型`，含开头称谓与结尾 |

- **待办事项双格式复制**：Markdown 表格 或 Task List（`- [ ] [🔴高] 任务 @负责人 （截止日）`）
- **✏️ 自由编辑**：一键开启 contenteditable，微调后再复制
- **深色 / 浅色模式**：记忆主题偏好

---

## 技术说明

- 纯前端单文件，无后端依赖
- Markdown 渲染：[marked.js](https://marked.js.org/) + [DOMPurify](https://github.com/cure53/DOMPurify)（本地内联，无外部 CDN）
- AI 接口：通过 [jotarou.com](https://jotarou.com) API 网关转发，网关不持久化对话内容
- 草稿持久化：localStorage（仅本地存储，不上传）

---

## 部署

```bash
# 服务器拉取
mkdir -p /var/www/html/tools/meeting-minutes
curl -o /var/www/html/tools/meeting-minutes/index.html \
  https://raw.githubusercontent.com/jotaroustar/meeting-minutes-generator/main/index.html
```

---

© 2026 jotarou.com. All rights reserved. Unauthorized copying or commercial use is prohibited.
