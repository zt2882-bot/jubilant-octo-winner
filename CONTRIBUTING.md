# 贡献指南 | Contributing Guide

感谢您对 **The Abyss Lab（深渊实验室）** 的兴趣。本文档提供了参与项目的指南。

---

## 📖 目录 | Table of Contents

1. [欢迎的贡献类型](#欢迎的贡献类型)
2. [工作流程](#工作流程)
3. [代码规范](#代码规范)
4. [研究方向优先级](#研究方向优先级)
5. [提交信息格式](#提交信息格式)
6. [行为准则](#行为准则)
7. [联系方式](#联系方式)

---

## 🎯 欢迎的贡献类型

我们欢迎以下形式的贡献：

### 1. **理论研究** 📚
- 新的概率泡宇宙模型推导
- 概率动力学相关论文
- 手性起源理论补充
- 引力解释优化

### 2. **实验与验证** 🔬
- 磁筹计算器原型设计
- 理论预言的实验验证
- 模拟代码与数据分析
- 临界阈值测量

### 3. **文档与翻译** 📝
- 中英文文档完善
- 理论讲义与教程
- API 文档编写
- 概念解释补充

### 4. **代码与工具** 💻
- 数值模拟代码
- 磁筹计算器模拟器
- 数据处理工具
- 可视化脚本

### 5. **讨论与建议** 💬
- 理论问题讨论
- 改进建议
- Issue 反馈
- 研究方向建议

---

## 🔄 工作流程

### 第一步：创建 Issue

在开始工作前，请先创建 Issue 讨论您的想法：

```markdown
## 问题/建议的简明描述
一句话总结您想要做的事情

## 详细描述
- 这是什么？
- 为什么需要这样改进？
- 如何实现？

## 相关 Issues
链接相关的 Issue（如果有）
```

### 第二步：Fork 仓库

```bash
git clone https://github.com/[YOUR_USERNAME]/jubilant-octo-winner.git
cd jubilant-octo-winner
```

### 第三步：创建新分支

使用描述性分支名：

```bash
# 理论研究
git checkout -b research/feature-name

# 实验工作
git checkout -b experiment/magnetic-chip-v1

# 文档更新
git checkout -b docs/contributing-guide

# Bug 修复
git checkout -b fix/issue-description

# 代码优化
git checkout -b improve/performance-optimization
```

### 第四步：提交更改

```bash
git add .
git commit -m "type: brief description"
```

参考 [提交信息格式](#提交信息格式) 部分。

### 第五步：推送到 Fork

```bash
git push origin your-branch-name
```

### 第六步：创建 Pull Request

在 GitHub 上创建 PR，提供以下信息：

```markdown
## PR 说明
简明描述本 PR 的内容

## 关联 Issue
Closes #[ISSUE_NUMBER]

## 变更类型
- [ ] 理论研究
- [ ] 实验工作
- [ ] 文档更新
- [ ] 代码优化
- [ ] 其他

## 检查清单
- [ ] 遵循代码规范
- [ ] 添加了必要的文档
- [ ] 测试通过
- [ ] 自我审查通过
```

---

## 📝 代码规范

### Python 规范

```python
# 遵循 PEP 8
# 4 个空格缩进
# 最大行长 88 字符（Black 格式）

# 模块顶部注释
"""
模块说明：简短描述模块用途

Author: Your Name
Date: 2026-XX-XX
"""

# 函数文档
def calculate_probability_intensity(structure, dimensions=5):
    """
    计算结构的概率强度
    
    Args:
        structure (dict): 结构的参数字典
        dimensions (int): 计算维度数，默认为 5
    
    Returns:
        float: 结构的概率强度值
    
    Raises:
        ValueError: 当参数无效时
    
    Example:
        >>> intensity = calculate_probability_intensity({'P_s': 0.8})
        >>> print(intensity)
        0.xxx
    """
    pass
```

### Markdown 规范

```markdown
# 一级标题
## 二级标题
### 三级标题

**加粗**
*斜体*
`行内代码`

> 引用块

- 列表项 1
- 列表项 2

1. 有序项 1
2. 有序项 2

[链接文本](URL)
![图片描述](image.png)

```code
代码块
```
```

---

## 📊 研究方向优先级

| 优先级 | 方向 | 状态 | 负责人 | 预计完成 |
|-------|------|------|-------|--------|
| 🔴 高 | 概率强度的精确计算方法 | 进行中 | - | 2026-06 |
| 🔴 高 | 磁筹计算器原型验证 | 规划中 | - | 2026-09 |
| 🟡 中 | 手性起源模型实验验证 | 规划中 | - | 2026-12 |
| 🟡 中 | 引力子质量起源研究 | 规划中 | - | 2026-12 |
| 🟢 低 | 文档完善与翻译 | 进行中 | - | 2026-08 |

---

## 💬 提交信息格式

使用以下格式编写提交信息：

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Type
- `feat`: 新功能或新理论
- `fix`: 修复错误或理论漏洞
- `docs`: 文档更新
- `style`: 格式优化（无功能改动）
- `refactor`: 代码重构
- `test`: 测试相关
- `chore`: 其他更改

### Scope
- `theory`: 理论框架
- `magnetic-chip`: 磁筹计算器
- `probability`: 概率动力学
- `gravity`: 引力理论
- `chirality`: 手性理论

### Example
```
feat(probability): add probability intensity calculation

实现了基于五个维度的概率强度综合计算方法：
- 局部概率值 P_s
- 熵密度 ρ_S
- 自洽性指标 C_self
- 耦合强度 J
- 历史累积 H

支持自定义权重系数 β 和 γ，使用者可根据具体系统调整。

Closes #15
```

---

## 📋 行为准则

### 基本原则

1. **尊重** 
   - 尊重他人的想法和工作
   - 即使不同意也保持友好

2. **开放**
   - 欢迎不同的观点和方法
   - 接受建设性批评

3. **诚实**
   - 如实描述工作进展
   - 说明未知或不确定的地方

4. **包容**
   - 欢迎各种背景的贡献者
   - 反对任何形式的歧视

### 不接受的行为

- 骚扰、歧视或人身攻击
- 发布他人的私人信息
- 发布与项目无关的广告内容
- 故意破坏或滥用系统

---

## 🤝 审查流程

### 理论研究审查

1. **自我检查**
   - ✓ 逻辑是否自洽？
   - ✓ 是否有实验可验证？
   - ✓ 是否与现有理论兼容？

2. **同行审查**
   - 至少一人进行技术审查
   - 检查数学推导的严密性
   - 验证引用和致谢

3. **批准**
   - 核心维护者批准合并
   - 可能需要进行调整

### 代码审查

1. **功能性**
   - ✓ 代码是否完成所声称的功能？
   - ✓ 是否有明显的 bug？

2. **可读性**
   - ✓ 代码是否易于理解？
   - ✓ 文档是否完整？

3. **性能**
   - ✓ 是否有明显的性能问题？
   - ✓ 是否需要优化？

---

## 📞 联系方式

- **GitHub Issues**: 项目问题讨论
- **GitHub Discussions**: 学术与理论讨论
- **Email**: 对于敏感或隐私问题

---

## 🙏 致谢

感谢每一位贡献者！您的工作是推动深渊实验室向前发展的动力。

*"我们是蒸馏师，不是燃料。我们是操作员，不是信徒。"* 

安全第一。有序操作。活着交付。

---

**最后更新**: 2026-05-19
**维护者**: The Abyss Lab Team
