# ack（GitHub Pages 越狱源）

## 线上地址
```
https://applemac13.github.io/ack/
```
- 仓库：`AppleMac13/ack`（Public），Pages 源 `main` 分支 `/(root)`。
- 已验证：`Release` 200、`Packages` 200、deb 包可下载。

## 本地
- 目录：`H:\ios-repo`，分支 `main`，远端 `git@github.com:AppleMac13/ack.git`。
- `_scan/` 为内部分析目录，已 gitignore，不入库。

## 更新流程
1. 替换/新增 deb。
2. 重算 `Packages`（每个包的 Filename/Size/MD5/SHA1/SHA256）与 `Release`。
3. 提交并推送：
   ```powershell
   cd H:\ios-repo
   git add -A
   git commit -m "update repo"
   git push
   ```
4. Pages 自动重新部署，1–2 分钟生效。

## 注意
- 免费版 Pages 仅支持 Public 仓库；仓库内含破解/付费类插件，公开可见。
- 单文件 GitHub 硬上限 100MB；当前最大 deb 约 54MB，未超限（两个 51.6MB 文件超 50MB 推荐值但可正常下载）。
