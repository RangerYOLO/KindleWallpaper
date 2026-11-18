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

- AI 娘角色与插画：ZipZipPipe 的 AI 娘系列，署名 **ZipZipPipe**。
- 授权：**CC BY-NC-SA 4.0（署名-非商业性使用-相同方式共享）**，仅限非商业使用。
- 请勿用于商业用途；转载需保留署名并遵循相同方式共享。

## 状态

这是一个**本地备份仓库**：已 `git init` 并完成首次提交，**未添加 remote、未推送、未登录 GitHub CLI**。
