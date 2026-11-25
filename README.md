# Prompt Manager Pages

Prompt Manager 静态站点的数据仓库，包含作品内容、站点配置与 GitHub Pages 部署工作流。

- 站点：`https://vioaki.github.io/Prompt-Manager-Pages/`
- 引擎：[vioaki/Prompt-Manager (`pages`)](https://github.com/vioaki/Prompt-Manager/tree/pages)

## 上传

在站点点击「上传」，登录 GitHub 后提交作品，系统会自动创建一条 Pull Request，合并后自动部署上线。

## 启用步骤

1. 先推送引擎仓 `pages` 分支并发布 `pages-v1.0.0` 标签（建议设为受保护标签），再推送本数据仓；也可将三个工作流的 `uses`、`engine_ref` 与 `site.config.json` 的 `engineRef` 同步改为同一完整提交 SHA。
2. 在 **Settings → Pages** 将 Source 设为 **GitHub Actions**。
3. 部署 Cloudflare Worker 后，将地址填入 `site.config.json` 的 `workerApiUrl`。
4. *(可选)* 在 Actions Secrets 配置 `AI_API_KEY`（及 `AI_BASE_URL`、`AI_MODEL`）启用 PR 自动建议。
