
# 代码评审

当前我们代码评审机制使用的是Gitlab平台，受限于平台，目前代码评审流程机制及使用体验上有一些不完善的地方

- 平台无法设置CI不通过的情况下允许MR合并
- 平台comments及feedback不友好，无法直观对比不同commit版本之间的diff及针对comments的修复情况
- 平台issue管理及PR绑定没有Github平台强大
- 平台发起1个MR，无法指定多人参与代码评审

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

### 代码评审流程图

![code review workflow](../graph/code-review.svg)

### 代码评审者应该关注什么？

### 挑选最适合的代码评审者

### 代码评审机制保障
