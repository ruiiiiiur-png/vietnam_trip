# 越南行程页（GitHub Pages）

本文件夹可单独作为一个 Git 仓库发布到 GitHub Pages，在微信里分享链接即可打开。

**说明：** `ruiiiiiur@gmail.com` 是登录邮箱；在 Git 和网址里要用的是 **GitHub 用户名**：`ruiiiiiur-png`（来自你的仓库链接）。

**你的仓库：** [https://github.com/ruiiiiiur-png/vietnam_trip](https://github.com/ruiiiiiur-png/vietnam_trip)  
**发布成功后，分享给朋友的链接一般是：**  
**[https://ruiiiiiur-png.github.io/vietnam_trip/](https://ruiiiiiur-png.github.io/vietnam_trip/)**  
（在仓库 **Settings → Pages** 里开启并保存后，等 1～3 分钟生效。）

---

## 一次性操作

### 1. 确认 GitHub 上已有该仓库

若还没有，打开 [新建仓库](https://github.com/new)，**Repository name** 填 **`vietnam_trip`**（须与上面链接里的名字一致），选 **Public**，创建即可。若创建时勾选了 README，见下文「推送被拒绝」处理。

### 2. 在本机推送代码

在 **PowerShell** 里执行（路径已按你当前工程写好）：

```powershell
cd "c:\Users\jiang\Desktop\project\claude\vietnam-trip-github-pages"
git init
git branch -M main
git add index.html .nojekyll README.md
git commit -m "Add Vietnam trip page"
git remote add origin https://github.com/ruiiiiiur-png/vietnam_trip.git
git push -u origin main
```

若提示 `remote origin already exists`，先改地址再推送：

```powershell
git remote set-url origin https://github.com/ruiiiiiur-png/vietnam_trip.git
git push -u origin main
```

**登录说明：** GitHub 已不再支持用账户密码推送，请在提示输入密码时使用 **Personal Access Token**（[创建 Token](https://github.com/settings/tokens)，勾选 `repo` 权限），把 Token 当作密码粘贴。

**若 `git push` 被拒绝**（例如远程已有 README）：先拉再推：

```powershell
git pull origin main --allow-unrelated-histories
# 若有合并说明，保存退出编辑器后再：
git push -u origin main
```

### 3. 打开 GitHub Pages

1. 打开 [https://github.com/ruiiiiiur-png/vietnam_trip/settings/pages](https://github.com/ruiiiiiur-png/vietnam_trip/settings/pages)  
2. **Build and deployment** → **Source** 选 **Deploy from a branch**  
3. **Branch** 选 **main**，目录选 **/ (root)** → **Save**  
4. 等约 1～3 分钟，用 **https://ruiiiiiur-png.github.io/vietnam_trip/** 在微信里分享即可。若打不开，点右上角 **在浏览器中打开**。

### 4. 在微信里分享

复制整段：**`https://ruiiiiiur-png.github.io/vietnam_trip/`** 发到聊天即可。

---

## 以后你改了行程页怎么更新？

若你仍在编辑 `vietnam-trip-apr29-may5.html`，发布前先覆盖到本目录：

```powershell
Copy-Item -Force "c:\Users\jiang\Desktop\project\claude\vietnam-trip-apr29-may5.html" "c:\Users\jiang\Desktop\project\claude\vietnam-trip-github-pages\index.html"
```

再推送：

```powershell
cd "c:\Users\jiang\Desktop\project\claude\vietnam-trip-github-pages"
git add index.html
git commit -m "Update trip page"
git push
```

几分钟后网页会自动更新。
