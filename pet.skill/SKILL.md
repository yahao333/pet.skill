---
name: pet
description: "Distill your pet's personality, quirks, and companion spirit into an AI Skill. | 蒸馏宠物的个性、癖好和陪伴精神到一个 AI Skill 中。"
argument-hint: "[pet-name-or-slug]"
version: "1.0.0"
user-invocable: true
allowed-tools: Read, Write, Edit, Bash
---

# 宠物.skill 创建器（Claude Code 版）

## 触发条件

当用户说以下任意内容时启动：
- `/pet`
- "帮我创建一个宠物 skill"
- "我想蒸馏我的宠物"
- "新建宠物"
- "给我做一个宠物的 skill"

---

## 主流程：创建新宠物 Skill

### Step 1：基础信息录入

问 3 个问题：

1. **名字**（必填）：宠物叫什么名字？
2. **基本信息**（一句话）：种类、品种、年龄、性别
   - 示例：`金毛犬，3岁，公狗，活泼热情爱撒娇`
3. **特别个性**（可选）：最标志性的癖好、习惯或表达方式

### Step 2：原材料导入

询问用户提供原材料：

```
原材料怎么提供？

  [A] 照片/视频
      生活照、搞笑瞬间、互动视频

  [B] 叫声录音
      吠叫、呜咽、撒娇时的叫声

  [C] 行为日志
      日常作息、习惯动作、特殊行为

  [D] 聊天记录
      与宠物相关的家人对话、兽医记录

  [E] 直接粘贴
      复制文字粘贴进来

可以混用，也可以跳过（仅凭手动信息生成）。
```

### Step 3：分析生成

将收集到的材料按三条线分析：

**线路 A（性格特点）**：
- 活泼程度：好动 vs 安静
- 亲人程度：粘人 vs 独立
- 表达方式：撒娇、讨好、傲娇

**线路 B（行为模式）**：
- 日常习惯：吃饭、睡觉、散步的固定模式
- 社交行为：见人、见其他动物的反应
- 特殊癖好：吃草、舔人、藏东西

**线路 C（情感语言）**：
- 叫声含义：不同叫声代表什么
- 肢体语言：摇尾巴、耳朵、姿势的含义
- 与主人的特殊默契

### Step 4：确认并写入

向用户展示摘要，确认后写入文件到 `./pets/{slug}/`。

---

## 进化模式

用户追加新材料时，分析增量内容并 merge 到对应部分。

用户纠正时说「它不会这样」「它应该是」，更新对应内容。

---
---

# Pet.skill Creator (Claude Code Edition)

## Trigger Conditions

Activate when the user says:
- `/pet`
- "Help me create a pet skill"
- "I want to distill my pet"
- "New pet"

---

## Main Flow: Create a New Pet Skill

### Step 1: Basic Info (3 questions)

1. **Name** (required): What is your pet's name?
2. **Basic Info** (one sentence): Species, breed, age, gender
   - Example: `Golden Retriever, 3 years old, male, energetic and affectionate`
3. **Special Personality** (optional): Their most iconic quirks, habits, or ways of expression

### Step 2: Source Materials

```
How would you like to provide materials?

  [A] Photos/videos
      Daily photos, funny moments, interaction videos

  [B] Sound recordings
      Barks, whines, sounds when seeking attention

  [C] Behavior logs
      Daily routine, habitual actions, special behaviors

  [D] Chat records
      Family conversations about the pet, vet records

  [E] Paste text
      Copy-paste directly
```

### Step 3: Analyze & Generate

Analyze collected materials along three tracks:

**Track A (Personality Traits)**:
- Energy level: Active vs calm
- Affection level: Clingy vs independent
- Expression style: Spoiled,讨好, proud

**Track B (Behavior Patterns)**:
- Daily habits: Eating, sleeping, walking routines
- Social behavior: Reactions to people, other animals
- Special quirks: Eating grass, licking people, hiding things

**Track C (Emotional Language)**:
- Sound meanings: What different barks mean
- Body language: Tail wagging, ears, posture meanings
- Special bond with owner

### Step 4: Confirm & Write

Show summary to user, write files to `./pets/{slug}/` after confirmation.

---

## Evolution Mode

When user adds new materials, analyze delta and merge into relevant sections.

When user corrects with "they wouldn't do that" / "they should be", update content.
