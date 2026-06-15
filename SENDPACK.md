# Send-Pack 更新说明

这个仓库使用 `git send-pack` 发布到 GitHub：

```text
git@github.com:Jasmine-Liu-min/upward-reporting.git
```

## 日常更新

进入本地仓库：

```bash
cd /Users/insta360/Desktop/学校/作业/skill/upward-reporting
```

提交改动：

```bash
git add .
git commit -m "Update upward reporting skill"
```

发送到 GitHub：

```bash
git send-pack git@github.com:Jasmine-Liu-min/upward-reporting.git HEAD:refs/heads/main
```

## SSH Key

当前仓库使用这把专用 SSH key：

```text
/Users/insta360/.ssh/upward_reporting_github
```

公钥已经添加到 GitHub 仓库的 Deploy keys，并开启了写权限。

如果当前仓库已经配置过 `core.sshCommand`，日常更新时不需要手动指定 key。检查方式：

```bash
git config --get core.sshCommand
```

如果没有输出，可以重新配置：

```bash
git config core.sshCommand "ssh -i /Users/insta360/.ssh/upward_reporting_github -o IdentitiesOnly=yes"
```

## 什么时候需要重新配置

通常不需要重新生成 SSH key。只有这些情况需要重新配置：

- 换了电脑
- 删除了 `/Users/insta360/.ssh/upward_reporting_github`
- GitHub 仓库里的 Deploy key 被删除
- Deploy key 没有勾选 `Allow write access`
- 要把另一个仓库也改成独立的 deploy key
- 怀疑私钥泄露，需要废弃重建

## 验证远端

发送后可以检查远端 `main`：

```bash
git ls-remote git@github.com:Jasmine-Liu-min/upward-reporting.git refs/heads/main
```
