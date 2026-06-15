# 如何把这个项目传到 GitHub(Windows 版)

> 当前状态:这个文件夹**已经是一个 git 仓库**了——已 `git init`、分支为 `main`、所有文件已暂存(staged),只差「填身份 → 提交 → 建远程仓 → 推送」这几步。
> 因为要在 **Windows** 上推送,按下面走即可。

---

## 第 0 步:确认 git 相关文件都在(它们是隐藏的)

项目里有三样 git 文件,都以 `.` 开头、**默认被系统隐藏**:

| 名字 | 作用 | 必须保留 |
|---|---|---|
| `.git/` | **仓库本体**(提交记录、分支、暂存区都在这) | ⚠️ 最关键 |
| `.gitignore` | 忽略系统垃圾文件 | 是 |
| `.gitattributes` | 统一换行符(防止 Windows 上整库假 diff) | 是 |

**显示隐藏文件:**
- macOS Finder:`Command + Shift + .`(句号)
- Windows 资源管理器:菜单「查看」→ 勾「隐藏的项目」

---

## 第 1 步:把整个文件夹拷到 Windows

⚠️ **重点:必须连同隐藏的 `.git/` 一起拷。**

整个 `upward-reporting` 文件夹打包(zip)后拷到 Windows 再解压。拷之前先按上面方法显示隐藏文件,确认 `.git/` 在里面。

> 如果只拷了看得见的 `.md` 文件、漏了 `.git/`,那到 Windows 就只是一堆普通文档,不是 git 仓库,前面的准备全没了,得重来。

**验证拷成功了:** 在 Windows 上进入这个文件夹,打开终端跑:
```bash
git status
```
能列出文件状态 = `.git/` 带过来了 ✓;若提示 `not a git repository` = `.git/` 没拷到。

---

## 第 2 步:在 Windows 上装 Git

下载安装 [Git for Windows](https://git-scm.com/download/win),一路默认即可。
装完后,在项目文件夹里**右键 →「Open Git Bash here」**(或用 PowerShell / CMD)。

---

## 第 3 步:填写你的 git 身份(提交记录会用)

```bash
git config user.name  "你的名字"
git config user.email "你的GitHub邮箱"
```

> ⚠️ Public 仓库里 commit 邮箱**会公开**。不想暴露真实邮箱,去 GitHub →
> Settings → Emails 勾选 "Keep my email private",用它给你的
> `数字+用户名@users.noreply.github.com` 那个邮箱。

---

## 第 4 步:提交

```bash
git commit -m "Initial commit: upward-reporting skill"
```

---

## 第 5 步:在 GitHub 网页建一个空仓库

打开 https://github.com/new :
- **Repository name**:`upward-reporting`
- 选 **Public**
- ⚠️ **不要**勾 "Add a README / .gitignore / license"(勾了会和本地冲突,推不上去)
- 点 **Create repository**

建好后复制仓库地址,形如:
```
https://github.com/你的用户名/upward-reporting.git
```

---

## 第 6 步:关联远程仓并推送

```bash
git remote add origin https://github.com/你的用户名/upward-reporting.git
git push -u origin main
```

**首次推送会弹登录窗口**(Git Credential Manager,Windows 版自带):用浏览器点一下授权 GitHub 即可,**不用手动搞 token**。

---

## 完成

刷新 GitHub 仓库页面,能看到 `README.md` / `SKILL.md` / `设计说明.md` / `references/` 就成功了。
(中文文件名 `设计说明.md` 在 GitHub 上正常显示,不用担心。)

---

## 常见问题

- **`fatal: not a git repository`** → `.git/` 没拷过来。回第 1 步,确认显示隐藏文件后整夹重拷。
- **`failed to push ... fetch first` / `non-fast-forward`** → 建仓时勾了 README/license。删了那个仓,重新建一个**空**的。
- **`remote origin already exists`** → 之前加过远程。用 `git remote set-url origin 新地址` 改,或先 `git remote remove origin` 再加。
- **改完文件想再传一次** → `git add -A` → `git commit -m "说明"` → `git push`。
