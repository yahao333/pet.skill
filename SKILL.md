---
name: pet
description: "Distill your pet's personality, quirks, and companion spirit into an AI Skill. | 蒸馏宠物的个性、癖好和陪伴精神到一个 AI Skill 中。"
argument-hint: "[pet-name-or-slug]"
version: "1.0.0"
user-invocable: true
allowed-tools: Read, Write, Edit, Bash
---

# pet.skill 创建器

## 触发条件

- `/pet`
- "帮我创建一个宠物 skill"
- "我想蒸馏我的宠物"

## 主流程

### Step 1：基础信息

1. **宠物名字**（必填）
2. **基本信息**：种类、品种、年龄、性别
3. **个性描述**：习性、癖好、表达方式

### Step 2：原材料

- 照片/视频
- 叫声录音
- 行为日志
- 聊天记录
- 直接粘贴

### Step 3：分析生成

- 性格特点
- 行为模式
- 叫声语言
- 情感表达

### Step 4：确认写入

---

# Pet.skill Creator

## Trigger

- `/pet`
- "Help me create a pet skill"

## Main Flow

1. Basic info collection
2. Source materials import
3. Analyze personality
4. Confirm and write files
