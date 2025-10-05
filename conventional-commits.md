# 🧾 Git Commit Message Cheat Sheet

### ✅ 格式格式（标准模板）

```bash
<type>(<scope>): <subject>
```

示例：
```bash
feat(login): add user authentication logic
fix(api): correct null pointer in product controller
```

---

## 🏷️ 常见 type 类型

| type | 含义 |
|------|------|
| **feat** | ✨ 新功能（feature） |
| **fix** | 🐛 修复 bug |
| **docs** | 📝 文档修改（README、注释等） |
| **style** | 💅 样式调整（空格、格式化、缩进） |
| **refactor** | 🔧 代码重构（不影响功能的重写） |
| **perf** | ⚡ 性能优化 |
| **test** | 🧪 添加或修改测试 |
| **build** | 🏗️ 构建系统或依赖调整（webpack、maven、npm） |
| **ci** | 🤖 持续集成配置（GitHub Actions、Travis、Jenkins） |
| **chore** | 🧹 杂项（不影响功能的维护操作） |
| **revert** | ⏪ 回滚上一次提交 |

---

## 🧩 规则速查

| 规则 | 示例 |
|------|------|
| ✅ **type 小写** | `fix: correct typo` |
| ✅ **subject 简短清晰（≤72字符）** | `feat: add search bar in header` |
| ✅ **使用动词开头** | `add`, `fix`, `update`, `remove`, `optimize` |
| ❌ **不要句号或大写首字母** | `Fix: Added feature.` ❌ |
| ✅ **scope 可选但推荐** | `feat(auth): add login` |
| ✅ **英文书写（国际化通用）** | 避免中英文混合 |

---

## 🧠 提交思考顺序（写 commit 前问自己）：

1. 我改了什么？ → **type**
2. 改的是哪个模块？ → **scope**
3. 改动目的是什么？ → **subject**

例如：

| 改动 | Commit 示例 |
|------|---------------|
| 增加注册功能 | `feat(register): add new user registration` |
| 修复登录按钮失效 | `fix(login): correct button click handler` |
| 优化接口性能 | `perf(api): reduce query response time` |
| 修改 README | `docs(readme): update installation guide` |
| 格式化代码 | `style: format files with prettier` |

---

## ⚙️ 进阶工具推荐（团队必备）

| 工具 | 用途 |
|------|------|
| **commitlint** | 检查 commit 是否符合规范 |
| **husky** | 在 git commit 前自动触发检查 |
| **standard-version** | 自动生成 changelog 与版本号 |
| **semantic-release** | 自动发布版本到 npm / GitHub |

---

## 🖨️ 打印建议

- 使用 A4 竖版打印  
- 字体：`Consolas` 或 `Roboto Mono`  
- 缩放：90%（留白适中）  
- 纸张放桌旁，一眼查阅 🧠
