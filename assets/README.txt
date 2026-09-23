素材目录说明
=================================

assets/images/   58 张 —— 网络检索所得，仅作排版演示，上线前需替换为自有版权图片
assets/videos/   21 个 —— 7 段花枝透明视频（取自原站）+ 7 首帧海报 + 备份
assets/fonts/    Maison Neue Extended（原站字体）
assets/*.svg     版式用矢量图形（logo / 海岸线 / 楼栋图解 / 地图）
assets/placeholder.svg   留白占位图

花枝视频（7 段，透明通道）
---------------------------------
flower-01.webm ~ flower-07.webm   VP9 + alpha   1080x1080  10s   Chrome/Edge/Firefox
flower-01.mov  ~ flower-07.mov    HEVC + alpha  720x720   10s   Safari
flower-01-poster.avif ~ ...       首帧海报

页面里已接好，播放由原站 ScrollTrigger 控制。

★ 验证 alpha 的坑：ffprobe / ffmpeg 读不出 VP9 的 alpha（存在 BlockAdditional 里，
  不是独立轨道），会误报成 yuv420p。要验证必须实际渲染到彩色背景上看。

替换图片
---------------------------------
1. 把图放进 assets/images/，命名随意
2. HTML 里找到 <img ...>，把 src 指过去，删掉 data-asset-placeholder
3. <video> 换 poster / <source> 即可

待补：3 张云层图
---------------------------------
搜 class="clouds"，要求带透明通道的单独云朵（不是整片天空）。
补完删掉 css/pending.css 里的 img.clouds 隐藏规则。
详情见项目根目录「待替换清单.md」。

版权提醒
---------------------------------
assets/videos/ 里的花枝视频是原站（ERA Residence）的版权素材，
assets/images/ 里的图片来自公开网页，都没有商用授权。
正式上线前请全部替换为自有版权素材。