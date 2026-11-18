# Kindle Paperwhite 2 锁屏壁纸备份（灰度）

本仓库用于**备份 Kindle Paperwhite 2（KPW2）的锁屏壁纸及原始素材**，是一个**本地备份仓库**，尚未推送到任何远程。

## 两种用途 / 两个壁纸库

- **彩色壁纸**存放在同级的 `..\ColorfulWallpaper\`（另一个目录），**不在本仓库内**。
- **本仓库只存 Kindle 灰度壁纸**：KPW2 是 16 级灰度电子墨水屏，这里的壁纸全部为灰度版本。

## 目录结构

```
KindleWallpaper\
├── 原图\                # 42 张壁纸原图：Post/comment/Pixiv 共 40 张 + Claude/Gemini 首批 2 张
├── 成品\                # 42 张 758×1024 灰度成品：40 张灰度转换 + Claude/Gemini 首批 2 张
│   └── takagi\          # 高木同学（非 AI 娘）灰度壁纸预留目录，见其内 README
├── README.md            # 本说明
├── manifest.json        # 40 张灰度壁纸的取景/配对参数（source / output）
├── PREVIEW.png          # 40 张灰度壁纸的总览拼图
└── config.json          # 逐图取景覆盖配置（当前为空 {}）
```

原图与成品均按扁平方式存放，不再按来源分子目录。原来分散的 `Post\`、`comment\`、`Pixiv\` 已全部并入 `原图\`。

## 原图 ↔ 成品 命名对应

`成品\` 中每张壁纸由 `原图\` 中对应原图转换而来，一般规则为「原图主文件名 + `_758x1024`」，例如
`原图\AWS.jpg` → `成品\AWS_758x1024.png`。`manifest.json` 的 `source` / `output` 字段逐条记录这种对应关系，
两者都是**相对本仓库根目录**的路径：`source` 指向 `原图\<文件名>`，`output` 指向 `成品\<文件名>`。

- 例外 1：`原图\GeminiAr.png`（原 Post 来源）与 `原图\GeminiAr.jpg`（原 Pixiv 来源）主文件名相同，
  为区分二者，成品分别命名为 `成品\Post_GeminiAr_758x1024.png` 与 `成品\Pixiv_GeminiAr_758x1024.png`。
  配对请以 `manifest.json` 为准。
- 例外 2：Claude / Gemini 首批 2 张成品 `成品\Claude_成品_758x1024.png`、
  `成品\Gemini_成品_758x1024.png` 分别对应 `原图\Claude_原图.png`、`原图\Gemini_原图.jpg`，
  由同一脚本重制，未纳入 40 条 manifest。

取景/灰度转换的具体原理与字段说明见 `成品\README.md`。

## 壁纸规格

- 尺寸：**758 × 1024 像素**（KPW2 屏幕分辨率）
- 格式：**PNG8 / 16 级灰度**，索引色模式（P），抖动到约 16 灰阶、不强制索引到 16 色
- 使用 Rec.709 亮度转换，保留 e-ink 显示效果

## 素材来源与授权

本仓库中的 AI 娘角色插画（DeepSeek 鲸鱼娘「大肥鱼」、Claude 娘、Gemini 娘等）均为 B 站 UP 主
**ZipZipPipe**（胖次狐）创作/二创的「AI 娘」系列同人形象，原图按其公开发布整理，仅作个人非商业备份。

- 原作者 / 二创作者：**ZipZipPipe**
  - B 站：https://space.bilibili.com/4168597 （UID 4168597）
  - Pixiv：https://www.pixiv.net/users/18604994 （账号 @wonderful12138）
- 特别说明：**DeepSeek 鲸鱼娘**的原型来自 B 站创作者 **上善无形**的原创角色「溟月」（CC BY-NC-SA 4.0）；
  ZipZipPipe 在此基础上加入 DeepSeek 元素二创为女仆装鲸鱼娘。引用该角色时请同时署名上善无形与 ZipZipPipe。
- 授权：这些角色形象以 **CC BY-NC-SA 4.0（署名-非商业性使用-相同方式共享）** 提供，
  协议全文：https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh-hans
  - 必须署名（原作者及二创作者）、仅限非商业使用、衍生作品须以相同协议共享。
  - 本仓库公开的仅为原图备份与灰度转换成品，未做二次绘制；转载/再使用请遵守上述协议并保留署名与协议链接。
- 本仓库内的灰度壁纸是对上述原图的技术性转换（尺寸缩放与灰度抖动），不构成新的创作，版权仍归原作者所有。
- 请勿用于任何商业用途，也不要将这些形象当作对应厂商的官方形象。

**首批 Claude / Gemini 壁纸的授权**：`原图\Claude_原图.png`、`原图\Gemini_原图.jpg` 及对应成品同为 ZipZipPipe
创作/二创的 AI 娘形象，授权同上（CC BY-NC-SA 4.0：需署名、非商业使用、衍生同协议共享）；此处仅作个人
非商业备份，版权归原作者所有，请勿商用或当作官方形象。（原 `Claude-Gemini\README.md` 的素材来源与授权
说明已并入本节，文件夹已撤销。）

**素材来源补充**：`comment\` 已并入 `原图\`。其中部分评论配图并非 ZipZipPipe 本人作品，而是从 B 站 ZipZipPipe 动态的**评论区**下载的粉丝评论图片（含其评论中的配图）；仅作个人备份，版权归各自评论者所有。为便于追溯，原 `comment\` 来源的 6 张图为：`2f5a6ac398721cbddebd47faeb189bf69c1f988fbbd3a39342ab76b41200dd05.png`、`318d5b9b6fd184cc36434eb15422fc8de755b191264cbcd0640fff4eb1cccafd.png`、`44154f9119d5ddec2ecd7a36f27e6cc45ce5f54696532f64bbfe98dfd8152899.png`、`54a68b96a1bf37cf52815f0ee37109d1d1f1f349e5f6271c093c6b7ccf73ffe3.png`、`952e6ea699a4bb4b5909a8f328fd766d1441a3a101d72d2b4fb1053b4cd3e737.png`、`a4e7a49e6da150424b6c90c43f38cba2da882c299d7d00f14b44d291d3db11b0.jpg`。

## 状态

这是一个**本地备份仓库**：已 `git init` 并完成提交，**未添加 remote、未推送、未登录 GitHub CLI**。
