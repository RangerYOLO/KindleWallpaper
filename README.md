# Kindle Paperwhite 2 锁屏壁纸备份（灰度）

本仓库用于**备份 Kindle Paperwhite 2（KPW2）的锁屏壁纸及原始素材**，是一个**本地备份仓库**，尚未推送到任何远程。

## 两种用途 / 两个壁纸库

- **彩色壁纸**存放在同级的 `..\ColorfulWallpaper\`（另一个目录），**不在本仓库内**。
- **本仓库只存 Kindle 灰度壁纸**：KPW2 是 16 级灰度电子墨水屏，这里的壁纸全部为灰度版本。

## 目录结构

```
KindleWallpaper\
├── Post\                 # Kindle 源图：帖子配图（20 张）
├── comment\              # Kindle 源图：评论配图（6 张）
├── Pixiv\                # Kindle 源图：Pixiv 来源（14 张）
├── cover\                # Kindle 源图：封面（当前为空）
├── Claude-Gemini\        # 首批制作的 2 张 AI 娘壁纸（原图 + 成品）
└── AI-gijinka\
    └── KindlePaperWhite2\
        └── greyscale\    # 40 张 758×1024 灰度壁纸 + manifest.json + PREVIEW.png + config.json
            └── takagi\   # 高木同学（非 AI 娘）灰度壁纸预留目录，见其内 README
```

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

## 状态

这是一个**本地备份仓库**：已 `git init` 并完成首次提交，**未添加 remote、未推送、未登录 GitHub CLI**。
