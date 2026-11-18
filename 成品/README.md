# 成品壁纸目录（758×1024 灰度，最小留白取景版）

本目录存放 42 张 758×1024 KPW2 灰度壁纸：40 张由 `..\原图\` 中的源图转换而来（取景参数见根目录 `..\manifest.json`，
总览拼图见 `..\PREVIEW.png`），另有 Claude / Gemini 首批 2 张成品。转换脚本为
`D:\projects\scripts\make_kindle_greyscale.py`，输出规格为 758×1024 PNG8（模式 P / 256 项灰调色板 /
16 级灰度 Floyd-Steinberg 抖动 / Rec.709 / autocontrast cutoff=1 / Contrast×1.2 / 无 ICC）。
硬性规格与 `D:\projects\wallpapers\AI-gijinka\make_wallpapers.py` 完全一致。

本目录原为 `AI-gijinka\KindlePaperWhite2\greyscale\`，重构后其上移为仓库根目录下的内容，
`config.json` / `manifest.json` / `PREVIEW.png` 已移至仓库根目录，`takagi\` 预留目录移入本目录。

## 取景原则（2026-11-18 更新，取代原 AI-gij 纯 contain 做法）

用户要求：**壁纸尽可能包含原图关键信息；单角色立绘边角空白尽量小，但必须保持比例、
不切头/脚/尾巴/道具。**

原脚本对 40 张图里 39 张直接 `contain` 整张原图：白底立绘自带的白边 + 等比缩放留下的
两侧白条叠在一起，角色显得小、留白偏大（用户指出 Gemini 那版最明显）。

新做法（默认自动，无需配置）：

1. **先裁空白背景**：近白/纯色边框按四角估背景色（RGB 容差 40），透明图按 alpha 通道，
   算出紧贴角色的内容框，四周再加约 7% 安全边距；绝不切到角色本体。
2. **再按角色位置装框（不拉伸）**：
   - 宽/方图（裁完后 w/h ≥ 0.740）：`cover` 放大铺满整屏，取景窗口以角色为中心裁掉溢出，
     不留白边（Claude 这种角色偏右的图，窗口自动落到右侧，并保留头顶余量）。
   - 竖版全身立绘：按高度铺满 + 两侧补白；只在刚加的“空白 padding”范围内适度放大
     （每侧最多吃掉空白的 45%），把白条压到最小，**但不动角色一根汗毛**。
3. 头顶、脸、脚、尾巴、四角星/咖啡杯等关键内容必须完整并留在安全区内；
   “留白最小”不等于贴脸裁切。

## manifest 新增字段

根目录 `..\manifest.json` 中：

- `source` / `output`：改为相对仓库根目录的路径，分别指向 `原图\<文件名>` 与 `成品\<文件名>`。
- `mode`：`crop`（对应 cover 铺满）/ `contain`（对应 fit 按高度铺满）
- `framing`：`cover` / `fit`，说明实际装框方式
- `content_box`：裁白边后（含安全边距）的框，源图/ROI 像素坐标 `[左,上,右,下]`
- `content_box_raw`：检测到的紧贴内容框（未加边距）
- `blank_trimmed`：是否真的裁掉了空白（true 表示该图有白边被去掉）
- `blank_frac` / `blank_frac_before`：输出图近白像素占比，便于对比留白变化

## 配置覆盖

根目录 `..\config.json` 可逐图覆盖（键为相对路径或文件名）：`mode` / `box`（源坐标 ROI）/ `out` /
`pad` / `headroom` / `note`。当前为空 `{}`。

## 特别说明：Claude / Gemini 首批成品

`Claude_成品_758x1024.png` / `Gemini_成品_758x1024.png` 由同一脚本用 `..\原图\Claude_原图.png` /
`..\原图\Gemini_原图.jpg` 重制：Claude 收紧到右侧角色+咖啡杯（保留头顶余量），Gemini 全身+
四角星/尾巴完整保留、只裁掉白边。原图文件不改动。这 2 张未纳入 40 条 manifest。
