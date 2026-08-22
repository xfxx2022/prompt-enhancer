# 提示词增强器 · Prompt Enhancer

纯前端、零依赖的提示词增强网站。把粗糙、模糊的提示词一键重写为结构清晰、约束明确、可被 AI 稳定高质量执行的提示词。

## 特性
- ☁️ 云端 API 增强（OpenAI 兼容：DeepSeek / 硅基流动 等，无需本地显卡）
- 🎨 三种增强风格：通用（结构化）/ 严谨技术（约束可验证）/ 创意发散（多方案）
- 🚀 一键增强、🔁 迭代优化、📋 复制、💾 导出 Markdown、🕘 本机历史记录
- 🔒 设置（含 API Key）仅保存在**本机浏览器**，不会上传到任何服务器

## 使用
1. 打开网站（或本地直接双击 `index.html`）
2. 在「设置」中填写：
   - 云端 Base URL（如 `https://api.deepseek.com/v1`）
   - API Key（如 DeepSeek / 硅基流动 的 `sk-...`）
   - 模型（如 `deepseek-chat`）
3. 左侧粘贴原始提示词 → 点「🚀 一键增强」

> 支持用 `{{变量名}}` 声明运行时变量，增强后原样保留。

## 部署到 Vercel
一键导入本仓库即可：
https://vercel.com/new/clone?repository-url=https://github.com/xfxx2022/prompt-enhancer

导入后在 Vercel 中保持默认（根目录即为静态站点，框架选 `Other` 亦可），直接 **Deploy**。

## 常用云端服务
| 服务商 | Base URL | 模型示例 |
| --- | --- | --- |
| DeepSeek | `https://api.deepseek.com/v1` | `deepseek-chat` |
| 硅基流动 | `https://api.siliconflow.cn/v1` | `deepseek-ai/DeepSeek-V3` |

## 说明
- 若浏览器报 CORS 错误，请换用支持跨域的服务商，或用本地代理 / 云函数转发。
- 增强策略为通用模板，可按需在源码 `META` 对象中替换为你的真实逻辑。
