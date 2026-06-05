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

欢迎提交 Issue 和 Pull Request 来改进这个项目。

## 许可证

- [MIT License](./LICENSE)
