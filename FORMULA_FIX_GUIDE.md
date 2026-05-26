# GitHub 数学公式显示指南

## 问题

GitHub Issue中的LaTeX公式（如 `\Omega`, `P_i(\omega)`）显示为原始代码，而非美化的数学符号。

## 解决方案

### 使用 `$$` 分隔符

**Block Formula（块级，单独一行）：**
```markdown
$$E_g = -\sum_{i} p_i \log p_i$$
```

渲染效果：
$$E_g = -\sum_{i} p_i \log p_i$$

**Inline Formula（行内）：**
```markdown
熵定义为 $S = -\sum p \log p$，其中...
```

渲染效果：
熵定义为 $S = -\sum p \log p$，其中...

---

## 常见问题与解决

| 问题 | 原因 | 解决 |
|------|------|------|
| 公式显示为代码 | 缺少`$$`分隔符 | 改为 `$$公式$$` |
| 公式中文混乱 | 转义字符冲突 | 中文与公式分离：`$公式$ 中文说明` |
| 下标上标不显示 | 需要空格隔离 | `$P_{i}$ 或 $P^{(t)}$` |
| 特殊符号错误 | 转义不完整 | 使用 `\backslash`, `\alpha`, `\Omega` 等 |

---

## GitHub 支持的 LaTeX 命令

✅ **支持**：
- 希腊字母：`$\alpha, \beta, \Omega, \Sigma$`
- 上下标：`$P_{i}^{(t)}$`
- 求和积分：`$\sum, \int, \prod$`
- 分数：`$\frac{a}{b}$`
- 矩阵：`$\begin{matrix} a & b \\ c & d \end{matrix}$`
- 花括号集合：`$\{x | x > 0\}$`
- 偏导数：`$\nabla, \partial$`

❌ **不支持**：
- TikZ 绘图
- `\begin{align}` 多行公式（需改用 `$$...$$`）
- 自定义宏定义
- 某些复杂的化学/物理符号包

---

## 示例修改

### Issue #13 中的公式修改

**原文：**
```markdown
S_i = -\sum_{\omega \in \Omega_i} P_i(\omega) \log P_i(\omega)
```

**改为：**
```markdown
$$S_i = -\sum_{\omega \in \Omega_i} P_i(\omega) \log P_i(\omega)$$
```

---

### Issue #1 中的公式修改

**原文：**
```markdown
P_{inst} = \lambda_e \cdot E_g^{w_g} \cdot E_s^{w_s} \cdot E_c^{w_c} \cdot E_m^{w_m} \cdot E_{su}^{w_{su}}
```

**改为：**
```markdown
$$P_{\text{inst}} = \lambda_e \cdot E_g^{w_g} \cdot E_s^{w_s} \cdot E_c^{w_c} \cdot E_m^{w_m} \cdot E_{su}^{w_{su}}$$
```

---

### Issue #15 中的公式修改

**原文：**
```markdown
定义1 全态宇宙空间：记为\mathcal{U}，是包含...
```

**改为：**
```markdown
定义1 全态宇宙空间：记为 $\mathcal{U}$，是包含...
```

---

## 快速检查清单

使用以下清单确保所有公式都正确显示：

- [ ] 所有独立公式都用 `$$...$$` 包裹
- [ ] 行内公式用 `$...$` 包裹
- [ ] 检查特殊符号：`\Omega, \mathcal{U}, \lambda, \alpha` 等
- [ ] 检查下标：`P_{i}, E_{su}, P_{\text{max}}` 等
- [ ] 检查上标：`P^{(t)}, E^{w_g}` 等
- [ ] 检查求和/积分：`\sum, \int` 等

---

## 如何批量更新

### 使用 Python 脚本自动转换

```python
import re

def add_formula_delimiters(text):
    # 匹配未被 $$ 包围的 LaTeX 公式
    # 这只是示例，实际使用需更精确的正则
    pattern = r'(?<!\$)(\\\w+|\d+_\{.*?\}|[\w\d_\{\}\\]+)'
    return re.sub(pattern, r'$$\1$$', text)

# 对每个 Issue 的 body 进行处理
issue_body = """你的Issue内容"""
fixed_body = add_formula_delimiters(issue_body)
```

---

## 验证公式是否正确

访问你的Issue，检查：

1. **数学符号**是否显示为美化字体（不是代码字体）
2. **上下标**是否正确排版
3. **希腊字母**（α, β, Ω等）是否显示
4. **分数/矩阵**是否正确排版

---

## 参考资源

- [GitHub Blog: Math support in Markdown](https://github.blog/2022-05-19-math-support-in-markdown/)
- [LaTeX 数学符号完全手册](https://www.ctan.org/tex-archive/info/symbols/comprehensive/)
- [在线 LaTeX 公式测试](https://www.latex4technics.com/)
