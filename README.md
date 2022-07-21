# 袋鼠云数栈前端团队代码评审工程实践文档

## 代码评审指南介绍

* [代码评审指南指引](review/index.md), 包含 4 个子章节：
  * [代码评审指南](review/CodeReview/index.md)
  * [代码评审者指南](review/Reviewers/index.md)
  * [代码开发者指南](review/Developer/index.md)
  * [代码评审机制保障](review/Mechanism/index.md)

## 术语

部分文档中会用到一些术语，特在此说明:

* **MR**: "Merge Request."的缩写，代表正在进行代码评审的变更
* **LGTM**: "Looks Good to Me."的缩写，评审者批准**MR**时会这么说
* **SGTM**: “Sounds Good To Me."的缩写，评审者批准**MR**时会这么说
* **WIP**: “Work In Progress.”的缩写，如果你有个改动很大的 **MR**，可以在写了一部分的情况下先提交，但是在标题里写上 WIP，以告诉项目维护者这个功能还未完成，方便维护者提前 review 部分提交的代码

## 注意事项

* 经常进行代码评审
* 代码评审不要太正式，要短
* 尽可能让不同的人评审你的代码
* 保持积极的正面态度

## 常见问题

* **代码评审者提出的都是一些编码风格和代码规范的东西？**
  
   编码规范应该交给工具去做，代码需遵循数栈代码风格指南

* **为什么要鼓励为主而不是责罚并举？**
  
  众所周知代码评审并不容易施行，因为它是团队和个人长期才能感受到好处的过程，即使不做似乎也看不到啥影响，业务也照跑，而惩罚是阶段性的反馈，所以现阶段还是以鼓励为主，但是由于对代码提交人和代码评审人要求不同，对提交人的责任要求更大点。对审核覆盖率有要求，也有责任推进评审进度。
对于代码评审主要是鼓励，因为代码评审是利他行为。在某些情况下会有一些惩罚要求：该模块很重要，引发了故障。而此问题是可以通过明显的评审发现的，此时也要承担责任

* **某个需求（项目）留给开发时间非常紧张时怎么办？**
  
  可以不进行代码评审，优先保证按时需求（项目）上线
* **周末出现线上紧急 bug 要遵循代码评审流程吗？**
  
  可以不进行代码评审，以快速修复 bug 为主，或者采取 onCall 的方式让维护者尽快评审

## 路线图

* [x] [评审模版](https://github.com/DTStack/devops/blob/main/.github/merge_request_template.md)
* [x] **代码评审指南 2.0**达成共识
* [x] **代码评审指南 2.0**宣讲&落地
* [x] 整理输出团队自身的 Checklist
* [x] [代码风格指南落地](https://github.com/DTStack/Code-Style-Guide)
* [x] [输出ko-lint-config & eslint-plugin-dt-react package](https://github.com/DTStack/ko/tree/master/packages/ko-lint-config)
