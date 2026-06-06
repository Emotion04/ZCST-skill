# ZCST Skill

ZCST Skill 是一个面向珠海科技学院在读学生的 Skill。通过 `/zcst` 命令，学生可以快速获取关于校园生活、餐饮、宿舍、教务、设施等各方面的信息。

🚧 Still WIP.

## 手动安装

### 方法 1：直接克隆

```bash
git clone https://github.com/ZCST-OpenCS/ZCST-skill.git ~/.claude/skills/zcst
```

### 方法 2：手动复制

```bash
# 创建 skill 目录
mkdir -p ~/.claude/skills/zcst/docs

# 复制 skill 文件
cp SKILL.md ~/.claude/skills/zcst/
cp docs/*.md ~/.claude/skills/zcst/docs/
```

### 验证安装

安装完成后，在 Claude Code 中输入 `/zcst` 即可使用。

## 使用方法

在 Claude Code 中输入：

```
/zcst 食堂哪个好吃？
/zcst 宿舍有空调吗？
/zcst 怎么选课？
/zcst 毕业离校流程是什么？
```

## 支持的问题类型

| 分类 | 关键词示例 |
|------|------------|
| 餐饮 | 食堂、外卖、奶茶、吃饭、美食 |
| 宿舍 | 宿舍、几人间、空调、热水、住宿 |
| 教务 | 选课、考试、成绩、学分、转专业 |
| 设施 | 图书馆、校医院、打印店、快递站 |
| 娱乐 | 社团、活动、周边、好玩的 |
| 交通 | 校车、校门、公交、停车 |
| 毕业离校 | 毕业、离校、退宿、团组织关系 |
| 就业服务 | 求职、简历、面试、招聘会 |
| 新生入学 | 新生、入学、报到、行李、物品清单 |

## 贡献

欢迎参与！无论是纠错、补充新内容，还是完善缺失的知识库。

### 快速参与

- **发现信息过时或错误？** → 提 [Issue](https://github.com/ZCST-OpenCS/ZCST-skill/issues)，附上正确信息的来源链接
- **想直接动手改？** → Fork → 修改 → 提 PR，reviewer 会按验证标准审核
- **想贡献新知识库？** → 先看看有没有对应的 [Issue](https://github.com/ZCST-OpenCS/ZCST-skill/issues) 认领，避免重复劳动

详细规范见 [CONTRIBUTING.md](./CONTRIBUTING.md)。

## 开发者

本项目采用两层架构：

- **用户侧**：安装 skill 后直接用 `/zcst` 提问，skill 读取本地文档 + 必要时联网核实官方公告
- **开发者侧**：维护者使用 kimi-webbridge 采集小红书、贴吧等闭源平台信息，整理后更新知识库

### 维护节奏

| 时间点 | 检查内容 |
|--------|---------|
| 6 月 | 毕业离校流程、暑假安排 |
| 8 月 | 新生入学指南、新学年校历 |
| 12 月 | 转专业时间、寒假安排 |

大部分内容（床铺尺寸、食堂推荐、穿衣建议、邮寄地址）无需每学期更新。详见 [CONTRIBUTING.md](./CONTRIBUTING.md#开发者)。

## 许可证

- [MIT License](./LICENSE)
