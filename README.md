# scoop-bucket-private

[![CI](https://github.com/John-Tito/scoop-bucket-private/actions/workflows/ci.yml/badge.svg)](https://github.com/John-Tito/scoop-bucket-private/actions/workflows/ci.yml)
[![Excavator](https://github.com/John-Tito/scoop-bucket-private/actions/workflows/excavator.yml/badge.svg)](https://github.com/John-Tito/scoop-bucket-private/actions/workflows/excavator.yml)

个人使用的 [Scoop](https://scoop.sh) bucket, 收录我日常需要的 Windows 应用.

---

## 📦 安装

```powershell
scoop bucket add private https://github.com/John-Tito/scoop-bucket-private
```

查看本 bucket 收录的应用：

```powershell
scoop search --bucket private
```

按需安装：

```powershell
scoop install private/<app-name>
```

---

## 🔄 自动更新

本 bucket 使用官方 [ScoopInstaller/GithubActions](https://github.com/ScoopInstaller/GithubActions) 驱动的 **Excavator** 工作流, 每 **4 小时** 检查一次上游 Releases.发现新版本后自动更新 manifest 中的 `version`, 下载 URL 和 SHA256 哈希.

每个 manifest 都配置了 `checkver` 和 `autoupdate`, 无需手动维护版本号.也可在仓库 **Actions** 标签页手动触发 `Excavator`.

---

## ✅ CI

每次 push / PR 会在 **windows-latest** 上运行测试：

- PowerShell 语法检查
- 文件编码与换行规范(UTF-8/CRLF/末尾换行)
- Manifest JSON Schema 校验

---

## 🤝 贡献

个人 bucket, 主要供自己使用.如果发现 manifest 有问题(版本过时/哈希错误/安装失败等), 欢迎提 Issue 或 PR.

新 manifest 请从 [`bucket/app-name.json.template`](https://github.com/John-Tito/scoop-bucket-private/blob/main/bucket/app-name.json.template) 开始, 并确保通过 CI.

参考文档：

- [Scoop App Manifests Wiki](https://github.com/ScoopInstaller/Scoop/wiki/App-Manifests)
- [ScoopInstaller/.github CONTRIBUTING](https://github.com/ScoopInstaller/.github/blob/main/.github/CONTRIBUTING.md)

---

## 📄 Credits

基于 [ScoopInstaller/BucketTemplate](https://github.com/ScoopInstaller/BucketTemplate) 构建.各应用的版权与协议归其上游作者所有, 详见对应 manifest 的 `license` 与 `homepage` 字段.
