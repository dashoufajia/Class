# 李宸睿 · 个人简历网站（Li Chenrui — Personal Résumé Site）

一个自包含的中英双语个人简历网站，基于原生 HTML / CSS / JavaScript 构建，无需任何构建工具或依赖，可直接托管在 **GitHub Pages** 上。

## 文件说明

| 文件 | 说明 |
| --- | --- |
| `index.html` | 网站本体（单文件自包含，含全部样式与逻辑） |
| `README.md` | 本说明 |

## 本地预览

直接用浏览器打开 `index.html` 即可。页面右上角有「中文 / EN」切换按钮，语言偏好会自动保存在浏览器中。

## 部署到 GitHub Pages

### 方式 A：作为个人主页（username.github.io）

1. 在 GitHub 新建仓库，仓库名必须是 `你的用户名.github.io`（例如 `chenrui-li.github.io`）。
2. 将 `index.html`（和 `README.md`）上传到仓库根目录。
3. 无需额外设置，访问 `https://你的用户名.github.io/` 即生效。

### 方式 B：作为独立项目页

1. 在 GitHub 新建任意名称的仓库（例如 `my-resume`）。
2. 将 `index.html` 上传到仓库根目录并推送。
3. 打开仓库 **Settings → Pages**：
   - **Source** 选择 `Deploy from a branch`
   - **Branch** 选择 `main`，目录选择 `/ (root)`
   - 点击 **Save**
4. 等待 1–2 分钟，访问 `https://你的用户名.github.io/my-resume/`。

### 后续更新

修改 `index.html` 后 `git commit` + `git push`，GitHub Pages 会自动重新发布。

## 个性化修改

所有内容（中英文）集中存放在 `index.html` 底部 `<script>` 内的 `DATA` 对象中：

- `DATA.zh` / `DATA.en`：中文 / 英文两套完整内容
- 修改姓名、邮箱、电话、经历、项目等，直接改对应字段即可，两套语言同步维护
- 如需添加 GitHub 主页链接，可在 `hero.meta` / `contact.meta` 中新增一项（`icon` 可使用 `mail` / `phone` / `pin` / `cap`）

## 技术要点

- 单文件自包含，无外部 JS / CSS 依赖（仅字体走自托管 CDN 镜像，加载失败时自动回退系统字体）
- 响应式适配桌面与移动端
- 尊重 `prefers-reduced-motion`，减弱动画
- 原生 JS 实现语言切换（localStorage 记忆偏好）
