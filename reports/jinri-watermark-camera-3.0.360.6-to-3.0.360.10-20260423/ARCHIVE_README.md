# 今日水印相机 版本监控归档

- 版本范围：v3.0.360.6 -> v3.0.360.10
- 包名：com.xhey.xcamera
- 生成时间：2026-04-23 18:11:59
- 主报告入口：`index.html`

## 摘要

- 功能变化：1
- UI 变化：2
- 新增资源字符串：78
- 新增 API/类线索：2
- 新增埋点/UI key：5
- 新增图片资源：0
- 删除图片资源：1

## 页面级 UI Diff

- 新增 layout：0
- 删除 layout：0
- 变更 layout：2
- 新增资源值：5
- 变更资源值：38
- 新增资源文件：3
- JADX layout 映射：2100

## 静态页面预览

- 预览图数量：1
- 预览说明：这些图是基于 apktool layout XML、strings、colors、drawable 引用生成的静态近似还原，不是真机运行截图。

- `layout/layout_group_desktop_widget`：工作组/桌面组件，`static-ui-previews/layout_layout_group_desktop_widget.svg`，关联类：sources.com.xhey.xcamera.businessmodule.desktopwidget.WorkGroupDesktopWidget

## 主要功能结论

### 工作组桌面组件视觉样式调整

- 类型：UI 改版
- 置信度：中
- 影响：桌面组件卡片背景、明暗色值和文案颜色有静态资源变化，可能影响工作组入口的桌面展示一致性。
- 新增 5 个 `workgroup_desktop_widget_*` 色值/资源 key，集中在桌面组件背景和文案颜色。
- `layout_group_desktop_widget` 与 `layout-v22/layout_group_desktop_widget` 均发生属性级变化，关联类映射到 `WorkGroupDesktopWidget`。
- 旧版 `bg_group_desktop_widget_card_colorful.png` 被移除，新版改为 drawable XML；另有 widget preview 图片变化。
- 建议在真机桌面添加工作组组件，分别验证浅色/深色模式、团队同步开启态和点击跳转链路。

## 底层变化

- PreviewSettingDrawerCoordinator 小幅重构：新增两个 `obtainDrawer` 内部类线索、移除一个旧内部类；未伴随明确页面新增，倾向实现重构或局部状态处理调整。（置信度 低）
- Native/加固文件重签和微调：native 库集合无新增删除，但 6 个 native/加固相关文件变更；需要运行态验证是否只是构建产物差异。（置信度 低）
- Manifest 对外能力未扩张：权限、Activity 数量未变化，未发现新增 URL；本次更像资源和局部实现迭代。（置信度 高）

## 文件说明

- `index.html` / `app.js` / `styles.css`：可离线打开的 Web 报告快照。
- `report-data.json`：功能、底层、证据统计主数据。
- `static-ui-data.json`：静态 UI key、素材和证据链。
- `ui-layout-data.json`：页面级 layout/resource diff。
- `ui-preview-data.json`：静态页面预览索引。
- `static-ui-previews/*.svg`：静态页面近似还原图。
- `archive-manifest.json`：归档清单和计数。
