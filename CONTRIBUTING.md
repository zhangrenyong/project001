# 贡献者指南

感谢您对项目贡献感兴趣！本指南将帮助您了解如何有效地参与本项目。

开始之前

• 在开始任何工作之前，请先查看现有的 Issues 和 Pull Requests，避免重复工作

• 对于较大的功能改动，建议先创建 Issue 讨论，得到核心维护者认可后再开始编码

• 确保您已签署贡献者许可协议（如有需要）

开发环境设置

1. 环境要求

• JDK 17+（推荐使用 Amazon Corretto 17 或 Temurin 17）

• Maven 3.6+ 或 Gradle 7.x+（根据项目实际构建工具选择）

• Git 2.20+

2. 项目克隆与导入

# 1. Fork 本仓库到您的账户
# 2. 克隆您 Fork 的仓库
git clone https://github.com/YOUR-USERNAME/REPO-NAME.git
cd REPO-NAME

# 3. 添加上游远程仓库
git remote add upstream https://github.com/ORIGINAL-OWNER/REPO-NAME.git

# 4. 同步最新代码
git fetch upstream
git checkout main
git merge upstream/main


3. IDE 配置

• 推荐使用 IntelliJ IDEA 或 VS Code

• 导入项目后，请确保：

  • 使用项目定义的代码风格（如已包含 editorconfig 文件）

  • 启用注解处理器（如使用 Lombok、MapStruct 等）

  • 安装并配置 Lombok 插件（如使用 Lombok）

开发流程

1. 创建功能分支

# 从最新的 main 分支创建
git checkout -b feat/your-feature-name
# 或
git checkout -b fix/issue-number-description


分支命名规范：
• feat/: 新功能

• fix/: Bug修复

• docs/: 文档更新

• style/: 代码格式调整（不影响功能）

• refactor/: 重构

• test/: 测试相关

• chore/: 构建过程或辅助工具变更

2. 代码规范

Java 代码风格

• 遵循 Google Java Style Guide 或项目定义的 checkstyle 规则

• 使用 4个空格缩进，不使用 Tab

• 行宽限制在 120个字符以内

• 类和方法必须有 Javadoc 注释

提交信息规范

使用约定式提交（Conventional Commits）格式：

<类型>[可选 范围]: <描述>

[可选 正文]

[可选 页脚]


类型：
• feat: 新功能

• fix: Bug修复

• docs: 文档

• style: 格式

• refactor: 重构

• test: 测试

• chore: 维护

示例：

feat: 添加用户登录功能

- 实现基于JWT的认证
- 添加登录接口
- 编写单元测试

Closes #123


3. 测试要求

• 所有新功能必须包含单元测试

• Bug修复必须包含回归测试

• 测试命名：被测试类名 + Test

• 使用 Given-When-Then 模式编写测试

• 测试覆盖率要求：行覆盖率 > 80%，分支覆盖率 > 70%

运行测试：
# Maven
mvn clean test
mvn clean verify  # 包含集成测试

4. 代码质量检查

提交前请运行：
# 代码格式化
mvn spotless:apply

# 静态代码分析
mvn checkstyle:check pmd:check spotbugs:check


提交更改

1. 推送分支

git push origin feat/your-feature-name


2. 创建 Pull Request

1. 在 GitHub/GitLab 上创建 Pull Request/Merge Request
2. 使用 PR 模板填写描述
3. 确保勾选以下选项：
我已阅读贡献者指南

我已添加测试

所有测试通过

代码已通过静态检查

我已更新相关文档

3. PR 审查流程

• 至少需要 1名 核心维护者批准

• CI/CD 流水线必须全部通过

• 代码审查意见必须在原分支解决，不要创建新PR

• 使用 "Squash and Merge" 或 "Rebase and Merge" 合并

文档规范

1. API 文档

• 所有公共类、方法必须有完整的 Javadoc

• REST API 使用 OpenAPI 3.0 规范

• 接口文档位于 src/main/resources/api-docs/

2. 代码注释

• 复杂逻辑必须添加注释说明

• 使用 // TODO: 标记待办事项

• 使用 // FIXME: 标记已知问题

依赖管理

1. 添加新依赖

1. 在 pom.xml 或 build.gradle 中添加依赖
2. 提供添加该依赖的合理理由
3. 检查许可证兼容性
4. 避免添加仅用于单个工具类的大型依赖

2. 版本升级

• 次要版本和补丁版本可定期更新

• 主版本升级需要讨论和充分测试

• 在 CHANGELOG.md 中记录重大变更

故障排除

常见问题

1. 构建失败
   • 清理本地 Maven/Gradle 缓存

   • 检查网络连接（下载依赖）

   • 确认 JDK 版本匹配

2. 测试失败
   • 在本地运行失败测试

   • 检查测试数据是否完整

   • 确认环境变量设置正确

3. 代码风格检查不通过
   • 运行格式化工具

   • 参考项目代码风格配置

行为准则

请阅读我们的 CODE_OF_CONDUCT.md，以了解我们对所有贡献者的期望。

获取帮助

• 对于代码问题，请在相关 Issue 或 PR 中讨论

• 对于使用问题，请查阅文档或创建 Issue

• 紧急问题可联系维护者（具体联系方式见项目主页）

注意：维护者保留对不符合本指南的贡献进行修改或拒绝的权利。感谢您的理解与合作！

最后更新：2026年3月5日
