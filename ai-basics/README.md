# AI 基础认知课使用说明

## 入口

直接打开 `index.html`。课程是离线自包含 HTML；三份课时页面只读取同目录下的本地图片，不需要安装依赖或启动服务。

## 手机上看与公开访问

发布完成后，手机浏览器打开：<https://renyubin2014.github.io/ai-learning-courseware/ai-basics/>

当前工作树未发布；只有在用户确认 commit / push 且 GitHub Pages 生效后，该地址才可用。GitHub Pages 是公开访问页面，任何获得链接的人都可以打开；课程不包含登录、个人数据或密钥。

## 课时

- `01_AI是怎样学会的.html`：AI 是怎样“学会”的？
- `02_LLM怎样生成一句话.html`：LLM 是怎样生成一句话的？
- `03_模型怎样走向Agent.html`：模型怎样从聊天走向 Agent？

## 学习方式

1. 从目录页选择课时。
2. 使用页面上方模块路线或底部“上一步 / 下一步”导航。
3. 在“关键词学习”中点击词条查看释义、例子和边界。
4. 在“自测”中先自行作答，再展开参考答案。
5. 完成课内实验，并按本课产物要求输出概念图、诊断或系统边界方案。

禁用 JavaScript 时，所有模块正文、关键词说明与自测答案仍可阅读；模块切换、实验反馈等交互不可用。

## 本地验证

在项目根目录运行：

```bash
node scripts/generate_ai_basics_courseware.mjs
node tests/validate_ai_basics_content.mjs
node tests/validate_ai_basics_courseware.mjs
NODE_PATH=/Users/xiaobinbin/.cache/codex-runtimes/codex-primary-runtime/dependencies/node/node_modules node tests/visual_check_ai_basics_courseware.mjs
git diff --check
```

浏览器交互与视觉验证由 `tests/visual_check_ai_basics_courseware.mjs` 执行；截图总路径模式为 `output/playwright/ai-basics-*.png`，六张验收图为：

- `output/playwright/ai-basics-index-desktop.png`
- `output/playwright/ai-basics-lesson-01-desktop.png`
- `output/playwright/ai-basics-lesson-02-experiment.png`
- `output/playwright/ai-basics-lesson-03-glossary.png`
- `output/playwright/ai-basics-index-mobile.png`
- `output/playwright/ai-basics-lesson-02-mobile.png`

## 内容与来源

- 内容日期：2026-07-22
- 课程主命题：AI 不是一个会思考的人，而是一套从数据中学习规律、根据上下文计算概率，并借助外部知识与工具完成任务的系统。
- 课内事实来源记录在每课页尾；在线来源链接不是页面运行依赖。

## GPT Image 2 资产

以下原创概念插画均使用 built-in image generation 生成，并保存在 `assets/generated/`：

- `training-factory.png`：表现训练样本经抽象学习机器沉淀为参数场，再由独立推理站使用；深色实验室、蓝紫环境光与橙色高光、16:9 横向连续流程，无文字、公式、界面、标识或拟人意识意象。
- `token-probability-paths.png`：表现语言积木在三个概率分支时刻选择路径并继续生成；深蓝紫概率地形、橙色选中路径、16:9 横向层级，无文字、数字、骰子、神秘符号或人物。
- `agent-workshop.png`：表现中央语言模型引擎连接文档库、只读观察仪器与受人工审批保护的行动工具；受控技术工作间、三条清晰通道、橙色审批门、16:9 横向构图，无文字、界面、品牌或完全自治暗示。
