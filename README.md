# 提示词增强器 · Prompt Enhancer

纯前端、零依赖的提示词增强网站。把粗糙、模糊的提示词一键重写为结构清晰、约束明确、可被 AI 稳定高质量执行的提示词。

## 特性
- ☁️ 云端 API 增强（OpenAI 兼容：DeepSeek / 硅基流动 / 智谱 / AgnesAI 等，无需本地显卡）
- 🎨 三种增强风格：通用（结构化）/ 严谨技术（约束可验证）/ 创意发散（多方案）
- 🚀 一键增强、🔁 迭代优化、📋 复制、💾 导出 Markdown、🕘 本机历史记录
- 🔒 设置（含 API Key）仅保存在**本机浏览器**，不会上传到任何服务器
- 🆓 内置两个免费模型预设：智谱 glm-4-flash、AgnesAI agnes-2.5-flash

## 使用
1. 打开网站（或本地直接双击 `index.html`）
2. 在「设置」中选择服务商预设，或手动填写：
   - 云端 Base URL（OpenAI 兼容，如 `https://api.deepseek.com/v1`）
   - API Key
   - 模型（如 `deepseek-chat`）
3. 左侧粘贴原始提示词 → 点「🚀 一键增强」

> 支持用 `{{变量名}}` 声明运行时变量，增强后原样保留。

## 免费模型申请方法

### 智谱 glm-4-flash（长期免费，中文强）
1. 打开 [open.bigmodel.cn](https://open.bigmodel.cn) 用手机号注册 / 登录；
2. 右上角点头像 → 选「API Keys」→ 点「创建 API Key」，名字随便填；
3. 生成后**立即复制保存**（Key 只显示这一次）；
4. 站点预设选「智谱 glm-4-flash」，自动填入：
   - Base URL：`https://open.bigmodel.cn/api/paas/v4`
   - 模型：`glm-4-flash`
5. 填入 Key 即可使用。适合中文长文、定时任务、需要工具调用的场景。

### AgnesAI agnes-2.5-flash（免费，免实名免绑卡）
1. 打开 [platform.agnes-ai.com](https://platform.agnes-ai.com) 用邮箱注册 / 登录；
2. 左侧菜单找到「API 密钥」→ 点创建，系统弹出完整 Key（**只显示这一次**，赶紧复制）；
3. 站点预设选「AgnesAI agnes-2.5-flash」，自动填入：
   - Base URL：`https://api.agnes-ai.cn/v1`（注意是 `api.agnes-ai.cn`，不是 `apihub.agnes-ai.com`）
   - 模型：`agnes-2.5-flash`
4. 填入 Key 即可使用。适合日常问答、改稿、快速出短文案。

> 通用坑：Key 只显示一次务必先存；接口地址多一个字母 / 少一个 `/v1` 都会连接失败；免费模型通常有速率限制，批量任务记得错峰。

## 常用云端服务
| 服务商 | Base URL | 模型示例 | 备注 |
| --- | --- | --- | --- |
| DeepSeek | `https://api.deepseek.com/v1` | `deepseek-chat` | 付费按量 |
| 硅基流动 | `https://api.siliconflow.cn/v1` | `deepseek-ai/DeepSeek-V3` | 付费按量 |
| 智谱 | `https://open.bigmodel.cn/api/paas/v4` | `glm-4-flash` | 🆓 长期免费 |
| AgnesAI | `https://api.agnes-ai.cn/v1` | `agnes-2.5-flash` | 🆓 免费免绑卡 |

## 部署
纯静态站点，根目录 `index.html` + `favicon.ico`，可直接托管到任意静态托管平台（根目录即入口）。

## 说明
- 若浏览器报 CORS 错误，请换用支持跨域的服务商，或用本地代理 / 云函数转发。
- 增强策略为通用模板，可按需在源码 `META` 对象中替换为你的真实逻辑。
- 站点接入了访问统计脚本（第三方 CDN），仅统计访问量，不上传提示词内容；如不需要可删除 `<head>` 中的统计片段。
