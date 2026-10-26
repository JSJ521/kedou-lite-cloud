# 轻解析 · 云端版（GitHub 免费算力）

手机随时用，不依赖自己的电脑：前端在 GitHub Pages（静态），下载任务跑在 GitHub Actions（免费 runner，含 ffmpeg + yt-dlp），产出发布到 Release 供手机直接下载。

## 部署（已完成的部分）

- Pages：从 `main` 分支的 `/docs` 目录发布
- 工作流：`.github/workflows/fetch.yml`（`workflow_dispatch` 手动触发，可传 `url` / `format`）

## 首次使用

1. 打开 Pages 地址；
2. 生成一次 GitHub Token（Settings → Developer settings → Personal access tokens (classic) → 勾 `repo` + `workflow`）；
3. 粘贴到页面里保存（只存本机 localStorage）；
4. 粘贴视频链接 → 开始 → 等 1–3 分钟 → 点下载。

## 已知限制

- GitHub 出口是数据中心 IP：YouTube 可能要求人机验证；B站/优酷等国内站受地区限制（需要代理，本方案未内置）。
- 免费 runner 排队 1–3 分钟，不是秒出。
- Release 资产公开可下载（公开仓库），不要下隐私内容。
