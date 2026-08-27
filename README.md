# Verra-Voile 图片资源仓库

独立管理所有爬取的图片资源，与主代码仓库分离。

## 目录结构

```
crawled/
├── photographers/      # 摄影师图片
├── wedding-teams/      # 婚礼团队图片
├── florists/          # 花卉商品图片
├── venues/            # 场地图片
├── travel-attractions/ # 旅拍景点图片
└── {module-slug}/     # 其他模块
```

## 使用方式

### 本地开发
后端通过符号链接引用此目录：
```bash
cd Verra-Voile-End/uploads
ln -s /Users/hongli/WorkSpace/Verra-Voile-Uploads/crawled crawled
```

### 部署同步
```bash
# 从本地同步到服务器
rsync -avz crawled/ user@server:/var/www/verra-voile-end/uploads/crawled/

# 从服务器恢复到本地
rsync -avz user@server:/var/www/verra-voile-end/uploads/crawled/ crawled/
```

## 注意事项

1. 新增图片后必须 commit 并 push
2. 部署前必须确保最新代码已 push
3. 删除图片前需确认无其他地方引用
