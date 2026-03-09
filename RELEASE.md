# Daily Viz v1.0.0

## 功能
- 📊 记录日常数据（心情、运动、睡眠、工作等）
- 📈 自动生成可视化图表
- 💾 本地数据存储
- 🎯 习惯追踪

## 安装
```bash
# 方式1: 直接下载
wget https://github.com/军哥/daily-viz/releases/download/v1.0.0/daily-viz-1.0.0.zip

# 方式2: 手动安装
mkdir -p ~/.agents/skills/daily-viz
cp -r daily-viz-skill/* ~/.agents/skills/daily-viz/
```

## 使用
```
node ~/.agents/skills/daily-viz/scripts/record.js 心情:开心 运动:30分钟
node ~/.agents/skills/daily-viz/scripts/visualize.js week
```

## 截图
![心情分布图](screenshots/mood-chart.png)
