# ack-repo 部署到 GitHub Pages

## 现状
- 本地仓库：`H:\ios-repo`，分支 `main`，已提交 153 个 deb + `Packages` + `Release`。
- 远端已配置：`git@github.com:AppleMac13/ack-repo.git`
- SSH 已通（`ssh -T git@github.com` 返回 Hi AppleMac13）。

## 步骤
1. 浏览器登录 GitHub，新建空仓库：
   - 名字 `ack-repo`，Public。
   - **不要**勾选 Add README / .gitignore / license（保持空仓库，否则推送要先合并）。
2. 本机推送：
   ```powershell
   H:\ios-repo\push-to-pages.ps1
   ```
   或在 `H:\ios-repo` 下执行 `git push -u origin main`。
3. 仓库网页 Settings → Pages：
   - Source: `Deploy from a branch`
   - Branch: `main`，文件夹 `/(root)`，Save。
4. 等 1–2 分钟，验证：
   - `https://applemac13.github.io/ack-repo/Release`
   - `https://applemac13.github.io/ack-repo/Packages`
5. Sileo / Zebra 添加源：
   ```
   https://applemac13.github.io/ack-repo/
   ```

## 注意
- 免费版 Pages 只能用 Public 仓库；仓库内包含破解/付费类插件，公开前自行确认。
- 单文件 GitHub 硬上限 100MB；当前最大 deb 约 54MB，未超限。
- 以后更新 deb 后：替换文件 → 重算 `Packages`/`Release` → `git add -A; git commit; git push`。
