# 「每日英语单词」iOS App · App Store 上架指南

## 一、两个硬性门槛（必须由你完成，我无法代办）

### 1. 安装 Xcode（免费）
- 从 Mac App Store 搜索「Xcode」下载安装（约 10GB+），安装后在终端跑一次：
  ```
  sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer
  ```
- 首次打开 Xcode 会提示安装额外组件，按提示完成。

### 2. 注册 Apple Developer Program（付费，$99/年）
- 打开 https://developer.apple.com/programs/ 用你的 Apple ID 注册
- 个人开发者即可（不需公司资质），需身份证件验证，通常 1-2 个工作日开通

## 二、工程文件说明（我已生成好）

```
words-app-ios/
├── package.json          # Capacitor 工程配置
├── capacitor.config.json # 应用名、包 ID、Web 目录
├── app-web/              # Web 资源（App 本体，每日推送自动更新此副本）
└── ios/                  # 完整 Xcode 工程（双击 App.xcworkspace 打开）
```

- 应用名：每日英语单词
- 包 ID：com.dailywords.app（上架后不可更改，请确认）
- 部署目标：iOS 15.0+
- App 图标：已配置（1024px 单尺寸，Xcode 自动生成全尺寸）

## 三、构建 + 上架步骤（Xcode 装好后）

1. 双击打开 `words-app-ios/ios/App/App.xcworkspace`
2. 左侧选中 App 项目 → Signing & Capabilities
3. 勾选 Automatically manage signing，Team 选你的开发者账号
4. 顶部菜单 Product → Archive（等待打包完成）
5. Organizer 窗口出现后点 Distribute App → App Store Connect → Upload
6. 到 https://appstoreconnect.apple.com 填写上架信息（见下）→ 提交审核

## 四、App Store Connect 上架信息（建议直接复制使用）

- **名称**：每日英语单词 - 雅思托福词汇
- **副标题**：每天 8:30 五个实用词
- **描述**：
  > 每天推送 5 个雅思 7-8 分、托福高频的实用英语单词，覆盖生活与职场场景。每个单词配有国际音标、中英释义、贴近真实场景的权威例句（附中文翻译）和记忆提示。支持按日期复习全部历史单词、搜索、翻转卡自测和掌握进度追踪，学习记录保存在本机，无需注册账号。
- **关键词**：英语, 单词, 雅思, 托福, 四六级, 背单词, 词汇, 听力, 口语
- **分类**：教育 / 语言学习
- **年龄分级**：4+
- **价格**：免费（可后续加内购）
- **隐私政策网址**：见下方第五节文本，可粘贴到任意免费托管页或直接提交文本

## 五、隐私政策（可直接使用）

> 隐私政策
>
> 「每日英语单词」尊重并保护您的隐私。
>
> 1. 数据收集：本应用不收集、不上传任何个人数据。所有单词学习数据（包括您的掌握进度）仅保存在您设备的本地存储中。
> 2. 网络使用：本应用仅在您主动更新单词数据时需要网络连接，不进行任何后台数据上传。
> 3. 第三方：本应用不集成任何第三方广告、统计或追踪 SDK。
> 4. 未成年人：本应用不面向未成年人收集任何信息。
>
> 联系我们：如有任何隐私相关问题，请通过 App Store 评论或开发者邮箱与我们联系。

## 六、审核截图要求（App Store Connect 提交时上传）

- 6.7 英寸（iPhone 15 Pro Max / 14 Pro Max）：1290×2796
- 6.5 英寸（iPhone 11 Pro Max）：1242×2688
- 5.5 英寸（iPhone 8 Plus）：1242×2208
- 方法：iPhone 模拟器运行 App → 截图（Command+S）→ 上传，或用真机截图

## 七、注意事项

- 包 ID（com.dailywords.app）上架后不可更改，确定后请勿修改
- 每日定时推送更新的是 Web 端；App 端单词数据在发布时已内置，后续可在新版本中随推送同步更新（我会在每次推送后同步 app-web/words-data.js，重新 Archive 即可发新版）
- 审核通常 1-3 天；学习工具类 App 通过率很高
