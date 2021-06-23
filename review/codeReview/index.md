
# 代码评审

当前我们代码评审机制使用的是Gitlab平台，受限于平台，目前代码评审流程机制及使用体验上有一些不完善的地方

- 平台无法设置CI不通过的情况下允许MR合并
- 平台comments及feedback不友好，无法直观对比不同commit版本之间的diff及针对comments的修复情况
- 平台issue管理及PR绑定没有Github平台强大
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

- 提交合并请求pull request
- 触发代码评审提醒和CI pipeline执行
- 代码评审者执行评审过程，代码评审者可以提交评论，其他人也可以参与针对问题进行持续跟进，一个MR手动设置多人参与CR
- 代码评审开发者收到评审意见，修改代码，回复评论，关闭问题
- 代码评审者确认问题是否修复，允许合并

### 代码评审流程

![code review workflow](../graph/code-review.svg)

### 代码评审者应该关注什么？

- 设计： 代码是否设计良好并且适合你们的系统？
- 功能性: 代码功能是否和开发者预期一致？这种方式是否对用户友好？
- 复杂性: 代码能不能更简单？ 其他开发者能否快速理解并在未来很容易地使用这段代码？
- 测试: 这段代码是否有正确和设计良好的自动化测试样例？
- 命名: 开发者有没有正确地对变量、类、方法等命名？
- 注释: 注释是否清晰有用？
- 代码风格: 代码风格是否遵循数栈代码风格指南?
- 文档: 开发者是否更新了相关文档？

### 挑选最适合的代码评审者

- 优先选择熟悉该业务域，技术域的开发，事先定好人选
- 其他人主动申请加入