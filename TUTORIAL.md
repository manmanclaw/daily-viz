# Daily Viz 使用教程

## 安装

```bash
clawhub install daily-viz
```

## 基础用法

### 1. 记录日常

打开终端，输入：

```bash
# 记录心情和运动
node ~/.agents/skills/daily-viz/scripts/record.js 心情:开心 运动:30分钟

# 记录睡眠和工作
node ~/.agents/skills/daily-viz/scripts/record.js 睡眠:8小时 工作:6小时

# 记录任意内容
node ~/.agents/skills/daily-viz/scripts/record.js 学习:2小时 阅读:30分钟
```

**支持的字段：**
- 心情：开心、一般、很好、糟糕等
- 运动：30分钟、1小时等
- 睡眠：7小时、8小时等
- 工作：6小时、8小时等
- 学习：2小时等
- 任意自定义字段

### 2. 查看数据可视化

```bash
# 查看本周统计
node ~/.agents/skills/daily-viz/scripts/visualize.js week

# 查看本月统计
node ~/.agents/skills/daily-viz/scripts/visualize.js month
```

### 3. 查看原始数据

```bash
# 查看所有记录
cat ~/.daily-viz/data/records.json | jq .
```

## 实际使用场景

### 场景1：晨间记录
每天早上记录：
```bash
node ~/.agents/skills/daily-viz/scripts/record.js 心情:很好 睡眠:8小时
```

### 场景2：晚间复盘
每天晚上记录：
```bash
node ~/.agents/skills/daily-viz/scripts/record.js 运动:45分钟 工作:8小时 学习:1小时
```

### 场景3：周末回顾
```bash
node ~/.agents/skills/daily-viz/scripts/visualize.js week
```

## 数据存储位置

所有数据保存在：
```
~/.daily-viz/data/records.json
```

你可以随时备份这个文件。

## 进阶技巧

### 创建快捷命令

在 `~/.zshrc` 或 `~/.bashrc` 中添加：

```bash
alias 记录='node ~/.agents/skills/daily-viz/scripts/record.js'
alias 查看='node ~/.agents/skills/daily-viz/scripts/visualize.js'
```

然后使用：
```bash
记录 心情:开心 运动:30分钟
查看 week
```

### 定时提醒

设置每天定时提醒记录：
```bash
openclaw cron add --name "晨间记录" --cron "0 9 * * *" --message "记得记录今天的心情和睡眠哦"
```

## 故障排除

**问题1：命令找不到**
```bash
# 检查 skill 是否安装
ls ~/.agents/skills/daily-viz/
```

**问题2：没有图表显示**
- 需要先记录一些数据才能生成图表
- 至少记录3-5条数据

**问题3：数据丢失**
- 检查 `~/.daily-viz/data/records.json` 是否存在
- 定期备份这个文件

## 下一步计划

- [ ] 支持更多图表类型（折线图、饼图）
- [ ] 导出 PDF 报告
- [ ] AI 智能分析和建议
- [ ] 云同步功能

---

有问题？在 GitHub 提 Issue 或联系作者！
