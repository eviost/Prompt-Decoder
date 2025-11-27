Prompt Decoder (初音提示词解码器)

一款高颜值、零隐私风险的 AI 绘画元数据解析工具

专为 Stable Diffusion (WebUI) 和 ComfyUI 玩家打造。无需安装任何插件，无需上传图片给第三方，直接在浏览器中拖拽图片，即可瞬间提取咒语（Prompt）和生成参数。

✨ 核心亮点

🔒 极致隐私保护

100% 本地运行：所有解析逻辑均在您的浏览器内通过 JavaScript 完成。

零上传：您的图片数据绝不会被发送到任何服务器，断网状态下依然可以完美使用。

🎨 沉浸式初音 UI

Miku 配色：标志性的葱绿 (#39C5BB) 与洋红 (#E4007F) 撞色设计。

现代质感：采用流行的磨砂玻璃拟态 (Glassmorphism) 和丝滑的 Q 弹动画交互。

日夜模式：支持深色/浅色主题切换，护眼又好看。

⚡ 硬核解析引擎

Stable Diffusion (A1111)：完美提取 Positive Prompt、Negative Prompt 以及 Steps、Sampler、Seed、Model 等关键参数。

ComfyUI：能够深入解析复杂的节点工作流 (Workflow) JSON 数据，智能抓取文本节点信息。

🛠️ 贴心交互体验

一键复制：点击任意参数卡片即可复制内容。

原图导出：支持将解析出的原始元数据导出为 .txt 或 .json 文件，方便保存或分享工作流。

智能防呆：自动识别非 PNG 格式或元数据丢失的图片，并提供友好的错误提示。

📖 食用指南

启动：双击打开 index.html 文件（建议使用 Chrome, Edge, Firefox 等现代浏览器）。

导入：将 PNG 格式 的 AI 原图拖入网页中间的上传区域。

解析：

WebUI 图：正负向提示词会自动分离，参数整齐列出。

ComfyUI 图：由于节点自由度极高，所有提示词将汇总显示，请在文本框中手动区分负面词。

使用：点击复制按钮获取咒语，或点击底部的“导出”按钮保存完整参数。

⚠️ 兼容性说明 (必读)

为了确保成功解析，请注意以下几点：

支持格式

✅ PNG 原图

AI 生成器直接保存的原始 PNG 文件。

不支持

❌ JPG / WEBP

这些有损压缩格式通常不包含生成信息。

不支持

❌ 社交软件图

微信、QQ、等平台会自动压缩图片并抹除元数据。

关于 ComfyUI 的负面提示词：
ComfyUI 的工作流是基于节点连接的，"Negative Prompt" 只是一个文本框连接到了采样器的负面端口。静态解析器很难 100% 准确地反推哪个文本框是用作负面的。因此，本工具会将提取到的所有文本显示在正向框中，请您根据内容自行辨别（通常 embedding:, nsfw, worst quality 等词汇属于负面）。

🧠 技术原理

本项目不依赖任何笨重的后端或第三方库，实现了轻量级的 PNG 二进制流解析：

利用 FileReader 读取图片的 ArrayBuffer。

通过 DataView 扫描二进制数据，定位 PNG 的 tEXt (文本块) 或 iTXt (国际文本块)。

提取关键字为 parameters (WebUI 标准) 或 prompt/workflow (ComfyUI 标准) 的数据段。

使用 TextDecoder 进行解码并渲染到 UI。

📬 联系与反馈

由 Eviost 用 ❤️ 制作。

📧 Email: huiz3108@gmail.com

🐙 GitHub: https://github.com/eviost

如果您觉得好用，请不吝分享给您的朋友！
