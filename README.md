# meeting-conflict-diagnoser

会议逐字稿 → 沟通问题、核心矛盾、根因与改进的 AI Skill。

## 它解决什么

会议纪要能告诉你「讨论了什么」，但不能告诉你「为什么这个会开不下去」。

这个 skill 只看互动结构，不看议题内容：谁在追、谁在逃、哪个问题被问了很多次却没人回答、哪句话让标准悄悄降了一级、散会后谁更沉默了。

## 输出什么

1. **诊断三问** —— task / process / status；急性 / 慢性；结构 / 人际
2. **事实层校准** —— 事实、观点、未说出口的假设；双方是否在同一个事实底座上
3. **矛盾地图** —— 含关系冲突伪装成任务冲突的识别
4. **立场 → 利益 → 底层需求** —— 他说要什么，他为什么想要，他真正缺什么
5. **冲突行为模式**（Thomas-Kilmann）—— 谁竞争、谁回避、谁在迁就，是否匹配情境
6. **根因链**（5 Whys）—— 追问到角色、流程、激励、决策权这一层
7. **无效沟通清单** —— 每条带位置、证据、后果
8. **团队层断点**（Lencioni 五障碍）—— 断在信任还是断在承诺，决定改进优先级
9. **改进设计** —— 会前 / 会中 / 会后，结构层 / 关系层
10. **一张诊断思维导图** —— 六支（矛盾 / 利益 / 行为 / 根因 / 失效点 / 改进），每个矛盾支带一个「反向张力」节点

## 安装

通用（Claude Code 及兼容 skills 目录的 agent）：

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/chase1960/meeting-conflict-diagnoser.git \
  ~/.claude/skills/meeting-conflict-diagnoser
```

其他 agent：把 `SKILL.md` 放进你的 skills 目录，目录名用 `meeting-conflict-diagnoser`。

## 用法

把逐字稿贴进来，然后说：

> 帮我诊断这场会：我们沟通中的问题是什么，为什么会出现这些问题

- 带说话人标签、带时间戳的逐字稿效果最好
- 补上参会人角色和最终决策，诊断会更准
- 只说「总结一下会议」它不会给你内容摘要——那是另一个 skill 的事

## 设计来源

- 三层冲突模型（Task / Process / Relationship）
- Fisher & Ury, *Getting to Yes* (1981)：position → interest
- Thomas-Kilmann 五种冲突模式 (1974)
- Lencioni 团队五障碍
- 5 Whys
- 中心问句与张力节点：导图中心应是「要回答的问题」，每支须带 tension 节点，防止单向论证
- StructSum（arXiv 2401.06837）：导图生成分事实性 / 局部结构 / 全局结构三层校验
- AAR 复盘图：节点须带触发条件与可复用产物

## 边界

不做会议纪要、内容摘要、行动项整理。

## License

MIT
