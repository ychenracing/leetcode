# ChatGPT Project Brief

> 本文件只保存长期稳定、仓库级的信息。当前任务、临时分支、SHA、测试状态和执行进度应保存在当前 Pull Request 正文中。

## 1. Project

- 项目名称：leetcode
- GitHub 仓库：`ychenracing/leetcode`
- 默认分支：`master`
- 系统定位：以 Eclipse Java 工程组织的算法题解与编程练习集合。
- 项目最终目标：保存和演进 LeetCode、Cracking the Coding Interview 及公司分类的 Java 算法实现；更长期目标未在仓库文档中明确。

## 2. Purpose and Non-Goals

仓库按题目来源或分类保存独立算法实现，用于问题求解、学习和复用。README 只将其描述为 problems 集合。

长期非目标未在仓库文档中明确。仓库未定义可部署服务、稳定库 API、命令行产品或发布流程，不应自行假定这些职责。

## 3. Architecture and Module Boundaries

- `src/leetcode/`：LeetCode 题解。
- `src/ctci/`：Cracking the Coding Interview 练习。
- `src/companies/`：按公司分类的算法练习。
- `.project`：Eclipse Java 项目描述，项目名为 `algorithm`。
- `.classpath`：Eclipse 源目录、输出目录和 JavaSE-1.7 容器设置。
- `.settings/org.eclipse.jdt.core.prefs`：Eclipse JDT 编译设置。

各题解通常是独立实现；源文件是算法行为 Owner，Eclipse 元数据是现有工程结构 Owner。治理文件不得成为第二份算法规范或构建配置。

## 4. Non-Negotiable Constraints

- 题目输入、输出、复杂度和边界条件必须以目标实现及其题意为准，不得仅凭类名推断。
- 修改共享数据结构或辅助方法时，应检查所有直接调用者。
- 现有 Eclipse 配置指向 JavaSE-1.7；升级语言级别或工程结构属于独立兼容性变更。
- 不得把缺少测试的实现写成已证明正确。
- 仓库没有 Maven、Gradle 或声明的外部依赖管理，不得猜测对应命令。
- 题目平台内容和样例属于外部来源；治理文件不复制受限内容或账号信息。

## 5. Authoritative Sources

- 项目简介：`README.md`
- 工程约定：`AGENTS.md`
- 算法实现：`src/leetcode/`、`src/ctci/`、`src/companies/`
- Eclipse 项目结构：`.project`、`.classpath`
- Java 编译设置：`.settings/org.eclipse.jdt.core.prefs`
- 题目规格、测试、依赖、发布和部署权威来源：未在仓库文档中明确

## 6. Standard Commands

- 安装与依赖解析：未在仓库中定义。
- 构建：仓库配置为 Eclipse Java 工程，但未记录命令行构建命令。
- 运行：按具体题解而定；未在仓库中定义统一入口。
- 测试：未在仓库中定义自动化测试框架或统一命令。
- lint、格式检查、静态分析和完整验收命令：未在仓库中定义。

## 7. Important Paths

- `src/leetcode/`：LeetCode 算法实现。
- `src/ctci/`：CTCI 练习。
- `src/companies/`：公司分类练习。
- `.project`：Eclipse 项目元数据。
- `.classpath`：源目录、输出目录和 JavaSE-1.7 设置。
- `.settings/org.eclipse.jdt.core.prefs`：JDT 设置。
- `README.md`：项目简介。
- `AGENTS.md`：渐进式验证约定。

## 8. CI and Acceptance Entry Points

- 仓库没有 `.github/workflows/`，未定义 GitHub Actions 构建、测试、lint 或发布门。
- 本地验证应遵循 `AGENTS.md` 的影响范围驱动原则。
- Definition of Done 的项目特有部分未在仓库中定义；算法变更至少应使用相关题目的正常、边界和失败用例验证，并准确记录实际执行方式和结果。

## 9. Prohibited Actions

- 不得把未执行的题解样例或复杂度分析写成已验证结果。
- 不得在没有独立任务和兼容性验证时升级 Java 级别或引入构建系统。
- 不得猜测题目规格、统一运行命令或外部依赖。
- 不得擅自改写 Git 历史或 force push。
- 不得丢弃未知或未提交工作，也不得覆盖无关改动。
- 不得把计划执行写成已验证完成。
- 不得根据旧聊天猜测当前分支、SHA、PR 或 CI 状态。

## 10. Context Loading Protocol

1. 新开发任务可以直接使用自然语言提出，不要求预先填写固定 Prompt。
2. 开始任务时先读取本文件。
3. 搜索与任务相关的开放 PR、分支和 Issue。
4. 如果存在匹配工作，从现有现场原地继续。
5. 当前动态任务状态默认维护在 Pull Request 正文。
6. 不强制普通单 PR 任务创建 Issue。
7. 优先读取目标代码、直接调用者、相关测试和直接相关配置。
8. 只有证据不足、状态冲突或影响范围扩大时才扩大读取。
9. 不默认加载完整仓库、完整聊天、完整日志或全部 GitHub Actions 历史。
10. 长对话交接使用 `conversation-continuity-guard`，但 GitHub 当前现场仍是状态权威来源。

## 11. References

- `README.md`
- `AGENTS.md`
- `src/leetcode/`
- `src/ctci/`
- `src/companies/`
- `.project`
- `.classpath`
- `.settings/org.eclipse.jdt.core.prefs`
