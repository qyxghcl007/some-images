# some-images

这个仓库用来存放图片资产，已按照常见图片工作流进行结构化。

目录结构

- images/
  - originals/    # 原始来源文件（不压缩、不裁剪）
  - optimized/    # 针对 web/应用优化后的文件（压缩、调整尺寸、不同格式）
  - thumbnails/    # 小尺寸缩略图（用于列表/预览）

推荐流程

1. 将相机/设计师提供的原始文件放入 images/originals/。
2. 在 images/optimized/ 中保存为适合发布或部署的版本（例如 WebP、较小分辨率）。
3. 生成 thumbnails/ 用于展示和节省带宽。

Git LFS

如果你会存放较大或大量二进制图片，强烈推荐在本地启用 Git LFS：

```bash
# 在本地执行一次
git lfs install
# 如果你还没有克隆仓库，先克隆：
git clone https://github.com/qyxghcl007/some-images.git
cd some-images
# Git LFS 在仓库内的 .gitattributes 已配置常见图片格式；如果你想手动添加：
git lfs track "*.png" "*.jpg" "*.jpeg" "*.webp" "*.gif" "*.tif" "*.tiff"
git add .gitattributes
git commit -m "Track images with Git LFS"
git push origin main
```

注意

- 请避免将大量逐帧或原始相机 RAW 文件直接提交到普通 Git（使用 LFS 或外部对象存储）。
- 对于矢量文件（如 .svg），通常不需要 LFS，因为它们是文本文件且可差异化。

如果你希望我也：
- 在仓库中加入自动化脚本（例如生成缩略图的脚本），
- 或者立刻把示例图片上传到 images/originals/，
告诉我你想要哪一项，我会继续处理。