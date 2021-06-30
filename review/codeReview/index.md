# 代码评审

当前我们代码评审机制使用的是Gitlab平台，受限于平台，目前代码评审流程机制及使用体验上有一些不完善的地方

- 平台无法设置CI不通过的情况下允许MR合并
- 平台评论及反馈不友好，无法直观对比不同提交版本之间的差异及针对评论的修复情况
- 平台问题管理及PR绑定没有Github平台强大
- 平台发起1个MR，无法指定多人参与代码评审

## 代码评审目标和原则

- 提高代码质量，及早发现潜在缺陷，降低修改/弥补缺陷的成本
- 促进团队内部知识共享，提高团队整体水平
- 评审过程对于评审人来说，也是一种思路重构的过程，帮助更多的人理解系统
- 是一个传递知识的手段，可以让其它并不熟悉代码的人知道作者的意图和想法，从而可以在以后轻松维护代码
- 鼓励相关学习对方的长处和有点和高效迅速完成代码评审
- 可以被用来确认自己的设计和实现是一个清楚的和简单的设计

## 利用 Gitlab 做代码评审

常见的一些 Review 工具

- Phabircator （Facebook)
- Gerrit (Google)
- Gitlab / Github
- ...

### 一次完整的代码评审

- 提交合并请求PR
- 触发代码评审提醒和CI pipeline执行
- 代码评审者执行评审过程，代码评审者可以提交评论，其他人也可以参与针对问题进行持续跟进，一个MR手动设置多人参与CR
- 代码评审开发者收到评审意见，修改代码，回复评论，关闭问题
- 代码评审者确认问题是否修复，允许合并

### 代码评审流程

![代码评审流程图](../../graph/code-review.svg)

### 代码评审者应该关注什么？

- 代码风格: 代码风格是否遵循数栈代码风格指南?
- 设计：配置、接口类的设计问题（合理性、友好性)？错误、重复的 API 调用或者封装？
- 功能性: 代码功能是否和开发者预期一致？逻辑的遗漏缺陷？
- 复杂性: 代码能不能更简单？ 其他开发者能否快速理解并在未来很容易地使用这段代码？
- 测试: 是否缺少应有的单元测试或者文档
- 命名: 开发者有没有正确地对变量、类、方法等命名？
- 文档: 开发者是否更新了相关文档？
- 注释：无用的代码或者注释

### 挑选最适合的代码评审者

- 优先选择熟悉该业务域，技术域的开发，事先定好人选
- 指定模块最近参与修改的单个或多个同学作为 Reviewer
- 指定参与相关模块讨论和设计过的人作为 Reviewer
- 指定项目核心开发者作为 Reviewer
- 如有必要，Reviewer 可分配给多个相关人

### 开发者需遵循的工程规范

- Git Workflow：[Git Workflow](https://dtstack.yuque.com/rd-center/sm6war/vzg2xd)
- Git Commit:[Git Commit](https://dtstack.yuque.com/rd-center/sm6war/dnt36o)
- SemVer：[SemVer](https://dtstack.yuque.com/rd-center/sm6war/cmdl2z)
- CSS编码规范(SASS/BEM)：[SASS/BEM](https://dtstack.yuque.com/rd-center/sm6war/clgpb7)
- Code Style Guide@基建组和团队资深成员协同

### 开发者需要知道的CI/CD流程

- Static Checking
  - ESlint
  - Type Checking
  - MDLint
  - Prettier
  - Stylelint
  - Unit Testing
- Build
  - Lock Yarn
  - Unify yarnrc
  - Migrate gitlab-runner to Jenkins

### 配合工具最佳

  为了提升工作效率，我们可以在我们的编辑器工具中安装相关的各种插件，提升整个评审效率，由于我们大部分同学都在使用 VSCode，这里我就列举部分插件以作参考：

- ESLint 代码静态检测, 解决基本的代码风格不统一的问题，避免一些低级 bug。当然 ESLint 最好集成到 dev 构建环节中去
- GitLens 非常好的 git 可视化管理插件
- Gitlab MR 协助快速创建 MR 请求

## 参考

- **[评审者指南](Reviewers/)**: 代码评审者的详细指南。
- **[开发者指南](Owner/)**: 提交变更评审的开发者的详细指南。
- **[代码评审机制保障](Mechanism/)**: 代码评审机制保障
