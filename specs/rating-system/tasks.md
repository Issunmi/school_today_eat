# 评分系统重构任务列表

## 任务

- [ ] 1. 删除现有评分相关代码
  - [ ] 1.1 删除 `insertRatingComponent` 函数
  - [ ] 1.2 删除 `setRating` 函数
  - [ ] 1.3 删除 `highlightStars` 函数
  - [ ] 1.4 删除 `updateRatingText` 函数
  - [ ] 1.5 删除 `interceptCommentSubmission` 函数
  - [ ] 1.6 删除 `observeComments` 函数
  - [ ] 1.7 删除 `processExistingComments` 函数
  - [ ] 1.8 删除 `currentRating` 变量
  - [ ] 1.9 删除 `setupEditorLabel` 和 `setupInputOccupied` 中的评分相关代码

- [ ] 2. 重新实现评分组件
  - [ ] 2.1 创建 `RatingManager` 类封装所有评分逻辑
  - [ ] 2.2 实现 `createRatingUI()` - 创建评分 UI 组件
  - [ ] 2.3 实现 `bindEvents()` - 绑定星星点击和悬停事件
  - [ ] 2.4 实现 `injectRatingToComment()` - 将评分注入评论内容

- [ ] 3. 实现可靠的评论提交拦截
  - [ ] 3.1 使用 MutationObserver 监听编辑器 DOM
  - [ ] 3.2 识别实际的输入元素类型
  - [ ] 3.3 在提交前正确修改内容

- [ ] 4. 实现评分显示功能
  - [ ] 4.1 监听评论列表变化
  - [ ] 4.2 解析评论内容中的评分标记
  - [ ] 4.3 渲染星星评分组件

- [ ] 5. 集成和测试
  - [ ] 5.1 在 Waline 初始化后调用评分组件
  - [ ] 5.2 测试评分选择功能
  - [ ] 5.3 测试评论提交功能
  - [ ] 5.4 测试评分显示功能

## 执行顺序

1. 先删除旧代码，确保代码干净
2. 实现新的 `RatingManager` 类
3. 集成到 Waline 初始化流程
4. 测试验证
