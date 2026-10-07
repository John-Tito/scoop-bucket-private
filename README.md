# scoop-pure-live

[![Tests](https://github.com/John-Tito/scoop-pure-live/actions/workflows/ci.yml/badge.svg)](https://github.com/John-Tito/scoop-pure-live/actions/workflows/ci.yml)
[![Excavator](https://github.com/John-Tito/scoop-pure-live/actions/workflows/excavator.yml/badge.svg)](https://github.com/John-Tito/scoop-pure-live/actions/workflows/excavator.yml)

A [Scoop](https://scoop.sh) bucket for **[Pure Live (纯粹直播)](https://github.com/liuchuancong/pure_live)** — a clean
multi-platform live streaming client for Bilibili, Huya, Douyu, Kuaishou, Douyin, NetEase CC, YY, Twitch, SOOP and
custom M38 sources.

## Install

```pwsh
scoop bucket add pure-live https://github.com/John-Tito/scoop-pure-live
scoop install pure-live
```

Update or uninstall:

```pwsh
scoop update pure-live
scoop uninstall pure-live
```

## Manifests

| Manifest                           | Version | Notes                                                                                                |
| ---------------------------------- | ------- | ---------------------------------------------------------------------------------------------------- |
| [`pure-live`](bucket/pure-live.json) | 3.1.17  | Windows x64 portable build (`PureLive-<version>-<build>-windows-x64-portable.zip`)                    |

### 说明 / Notes

- 使用上游官方 **portable** 压缩包，解压即用，不需要运行安装程序。
- 应用的用户数据位于程序目录下的 `AppData` 文件夹。清单通过 `persist` 将其映射到 Scoop 的 `persist` 目录，
  因此 `scoop update` 不会丢失配置、订阅源与播放记录。
- `checkver` / `autoupdate` 会自动跟踪上游新版本。由于下载文件名同时包含版本号和构建号
  （例如 `3.1.17-4106`），清单通过 GitHub Releases API + JSONPath 同时解析两者，并自动更新 SHA256。
- Start Menu 快捷方式名称为 **Pure Live**，同时提供 `pure-live` 命令行 shim。

## Auto-update

The [Excavator workflow](.github/workflows/excavator.yml) checks upstream every 4 hours and updates the manifest
(including the hash) automatically. It can also be triggered manually from the repository's **Actions** tab.

## Contributing

Issues and pull requests are welcome. Please read the
[Contributing Guide](https://github.com/ScoopInstaller/.github/blob/main/.github/CONTRIBUTING.md) and the
[App Manifests](https://github.com/ScoopInstaller/Scoop/wiki/App-Manifests) wiki page first.

## Credits

- [Pure Live](https://github.com/liuchuancong/pure_live) by [liuchuancong](https://github.com/liuchuancong) — licensed under AGPL-3.0.
- This bucket is based on the [ScoopInstaller/BucketTemplate](https://github.com/ScoopInstaller/BucketTemplate).
