# 评分系统重构检查清单

## 代码删除检查

- [ ] 已删除 `currentRating` 变量
- [ ] 已删除 `insertRatingComponent` 函数
- [ ] 已删除 `setRating` 函数
- [ ] 已删除 `highlightStars` 函数
- [ ] 已删除 `updateRatingText` 函数
- [ ] 已删除 `interceptCommentSubmission` 函数
- [ ] 已删除 `observeComments` 函数
- [ ] 已删除 `processExistingComments` 函数
- [ ] 已清理 `setupEditorLabel` 函数
- [ ] 已清理 `setupInputOccupied` 函数
- [ ] 已清理 `initWaline` 中的评分相关调用

## 新功能实现检查

- [ ] `RatingManager` 类已创建
- [ ] 评分 UI 组件正确显示在输入面板中
- [ ] 星星点击事件正常工作
- [ ] 星星悬停效果正常工作
- [ ] 评分文字提示正常显示
- [ ] 评论提交时评分被正确注入
- [ ] 评论列表中评分正确显示
- [ ] 样式符合 MD3 设计规范

## 功能测试检查

- [ ] 可以选择 1-5 星评分
- [ ] 选择评分后视觉反馈正确
- [ ] 不选择评分时评论正常提交
- [ ] 选择评分后评论内容包含评分标记
- [ ] 评论列表中星星评分正确渲染
- [ ] 多次打开不同餐厅评论功能正常
- [ ] 关闭弹窗后状态正确重置

## 兼容性检查

- [ ] 在桌面浏览器正常工作
- [ ] 在移动端浏览器正常工作
- [ ] 深色模式下样式正确
- [ ] 与现有 Waline 功能无冲突
