# 钢4 Mod 开发文档

## 目录结构

```
The-Dark-Ages/
├── descriptor.mod          # mod信息
├── localisation/           # 本地化 (多语言)
├── common/                 # 核心数据
│   ├── countries.txt       # 国家定义
│   ├── technologies.txt    # 科技树
│   ├── ideas.txt           # 国家精神
│   ├── units.txt           # 单位模板
│   ├── building_plans.txt  # 建筑
│   └── ...
├── history/                # 历史状态
│   ├── states/             # 省份
│   ├── countries/          # 国家初始状态
│   └── ...
├── events/                 # 事件链
├── decisions/              # 决策
├── gfx/                    # 图形资源
└── interfaces/             # 界面定义
```

## 文件格式

### descriptor.mod
```
name = "Mod名称"
path = "mod/Mod名称"
supported_version = "1.19.x"
tags = {
    "Category"
}
```

### 本地化 (localisation/english.yml)
```yaml
l_english:
 TAG: "国家名称"
 TAG_desc: "国家描述"
 EVENT_NAME: "事件标题"
```

### 国家 (common/countries.txt)
```
TAG = {
    graphical_culture = western_european_gfx
    culture = western_european
    color = { 0.2 0.4 0.8 }
    # 国家定义...
}
```

### 科技 (common/technologies.txt)
```
tech_name = {
    research_cost = x
    effect = { ... }
    icon = technology_icon
}
```

### 事件 (events/xxx.txt)
```
country_event = {
    id = "mod.1"
    title = "事件标题"
    desc = "事件描述"
    option = {
        name = "选项"
        effect = { ... }
    }
}
```

## 常用标签

| 类型 | 文件 | 格式 |
|------|------|------|
| 国家 | countries.txt | `TAG = { ... }` |
| 科技 | technologies.txt | `tech_id = { ... }` |
| 国家精神 | ideas.txt | `idea_id = { ... }` |
| 事件 | events/*.txt | `country_event = { ... }` |
| 决策 | decisions/*.txt | `decision = { ... }` |
| 建筑 | building_plans.txt | `building = { ... }` |

## 调试

- 使用 Paradox Art 验证文件格式
- 游戏内按 ` 打开控制台
- 使用 `notify "消息"` 测试事件
