# MHWA-Pocket

[苍雾世界](https://github.com/yeluo2022/MHWA) 的安卓资源包（MaaFwApp 打包用）。

由上游 [yeluo2022/MHWA](https://github.com/yeluo2022/MHWA) 迁移而来：

- Pipeline 迁移至 MaaFramework v5.1 语法（官方 migrate_pipeline_v5.py，`interrupt` → `[JumpBack]`）
- interface 由 V1 升级为 Project Interface V2（option 补 `type`，任务补 `controller`）
- OCR 模型：MaaCommonAssets ppocr_v4/zh_cn（装配进 `resource/base/model/ocr/`）
- 三资源按游戏安装渠道选择：官服 `com.feimo.hazeworld.main`（官网/APK 站直装的主流官服包）/ 官网直装包 `com.feimo.hazeworld`（旧官网包名）/ B 服 `com.feimo.hazeworld.bilibili`
  ——上游硬编码的 MuMu 渠道包 `com.feimo.hazeworld.mumu` 仅适用于模拟器，手机端不可用

## 更新流程

1. 改动本仓库内容 → commit + push
2. 打 semver tag（需大于手机上已安装的 versionName）
3. 建 Release 并上传对应 `.apk` 资产
4. 手机端 MaaFwApp 应用内「检查更新」即可自更新（interface.json 的 `github` 字段指向本仓库）

## 致谢

- 上游资源与流水线：[yeluo2022/MHWA](https://github.com/yeluo2022/MHWA)（MIT）
- 应用底座：[Aliothmoon/MaaFwApp](https://github.com/Aliothmoon/MaaFwApp)（AGPL-3.0）
- [MaaFramework](https://github.com/MaaXYZ/MaaFramework) 与 MaaCommonAssets

上游适配的是 PC + MuMu 模拟器环境；手机端问题（分辨率适配、包名、亮屏要求）在本仓库处理。
