# Echo Live
![banner](https://sheep-realms.github.io/images/project/echo-live/banner.png)

![](https://img.shields.io/github/license/sheep-realms/Echo-Live?style=for-the-badge)
![](https://img.shields.io/github/v/release/sheep-realms/Echo-Live?style=for-the-badge)
![](https://img.shields.io/github/downloads/sheep-realms/Echo-Live/total?style=for-the-badge)
![](https://img.shields.io/github/stars/sheep-realms/Echo-Live?style=for-the-badge)

这是一款基于 [Echo](https://github.com/sheep-realms/Echo) 的用于无声系虚拟主播直播的仿视觉小说对话框 OBS 插件。该插件无需部署本地服务器，下载后开箱即用。

下文为帮助文档摘要，如需阅读完整帮助文档请见 [Echo-Live 在线帮助文档](https://sheep-realms.github.io/Echo-Live-Doc/)（另有 [CloudFlare 镜像](https://echo-live-doc.pages.dev/)）。

您还可以加入我们的 [Discord 服务器](https://discord.gg/XuPQBw6tHC) 与我们交流。

## 快速参考
[使用指南](https://sheep-realms.github.io/Echo-Live-Doc/main/how-to-use/) · 
[主题样式](https://sheep-realms.github.io/Echo-Live-Doc/custom/theme/) · 
[消息格式](https://sheep-realms.github.io/Echo-Live-Doc/message/) · 
[配置文件](https://sheep-realms.github.io/Echo-Live-Doc/custom/config/) · 
[API 文档](https://sheep-realms.github.io/Echo-Live-Doc/dev/broadcast/)

## 使用方法
### 方法一：通过 OBS 内置浏览器广播传递消息（推荐）
1. 打开 OBS，将 `live.html` 作为浏览器源 **（不要勾选 “本地文件”）** 添加到您的场景中。如果您不知道如何正确填写地址，请直接使用浏览器打开 `live.html`，然后复制地址栏里的地址。
2. 点击 OBS 菜单中的 停靠窗口 > 自定义浏览器停靠窗口，将 `editor.html` 添加到停靠窗口中。如果您不知道如何正确填写地址，同上。
3. 在弹出的编辑窗口中，根据指引填写对话数据，点击 “发送”。（注：如果您关闭了广播功能则不会有发送按钮）
4. 若要继续制作下一条对话，重复步骤 3。

注：如需修改启动后的初始消息，请编辑文件 `start.js`。

### 方法二：通过轮询传递消息
如果因 OBS 更新等原因导致上述方法失效，请尝试此方法。
1. 使用文本编辑器打开配置文件 `config.js`, 将配置项 `echolive` 中的 `broadcast_enable` 改为 `false`，`messages_polling_enable` 改为 `true`。建议您使用 [VSCode](https://code.visualstudio.com/) 等专业文本编辑器作为您的文本编辑器，不建议使用 Windows 内置的记事本。
2. 打开 OBS，将 `live.html` 作为浏览器源（勾选 “本地文件”）添加到您的场景中。
3. 使用文本编辑器打开 `start.js` 备用。
4. 通过浏览器打开 `editor.html`，根据网页指引生成对话数据并复制。
5. 将 `start.js` 中的内容全部替换成复制的内容并保存。
6. 对话框将会自动打印修改后的消息。如果没有启用消息轮询，则需手动在 OBS 中选中浏览器源，点击 “刷新”。如果您自定义了一串消息列表，点击 “交互”，在弹出的窗口中点击任意内容区域即可开始打印下一条消息。
7. 若要继续制作下一条对话，重复步骤 3 ~ 5。当您熟悉语法格式后，您也可以直接编辑 `start.js`。

## 注意事项
- 您可以在 `config.js` 中修改配置来开关一些功能和调整参数。
- 富文本不适合快节奏的直播活动，更适合用作预先准备好的演出。
- 您可能需要准备足够大的屏幕或副屏以获得更方便的操作体验。
- 在浏览器中预览效果时，一些浏览器的自动播放音频政策会导致您在未点击网页的情况下听不到打字音效，这是正常现象，OBS 内置浏览器无此限制。
- 请注意控制每一段话的字数，否则会溢出。
- 对话框网页不可见时会进入休眠状态以防止意料之外的演出，此机制可以在 `config.js` 中关闭，但不建议你这么做。

## 扩展
Echo-Live 支持扩展，可用于增加额外资源。

**注意：Echo-Live 的扩展仅作规范导入分享资源之用，虽然目前仅支持增加额外音频资源，但实际上可以被用来做任何事，因此请谨慎安装来路不明的扩展。**

### 安装
1. 将扩展（是一个文件夹）放入 `extensions` 文件夹。
2. 在 `extensions.js` 中插入该扩展的文件夹名称。

### 开发
见[开发文档](https://sheep-realms.github.io/Echo-Live-Doc/custom/extension/)。

## 另见
- [如何为 Echo-Live 项目作出贡献？](CONTRIBUTING.md)
- [授权协议与声明](copyright.md)
- [GPL（GNU General Public License，GNU通用公共许可协议）第3版](LICENSE)

### 姊妹项目
- [Echo](https://github.com/sheep-realms/Echo)
- [Echo-Live-Doc](https://github.com/sheep-realms/Echo-Live-Doc)

### 第三方项目
- [Echo-Client](https://github.com/Rickyxrc/echo-client)
- [Echo-Live-Tauri](https://github.com/LuiScreaMed/Echo-Live-Tauri)
- [Echo-Live-Typetool](https://github.com/RaySky-Rt/Echo-Live-Typetool)

## 相关资源
建议您安装可免费商用字体以规避版权纠纷，Echo-Live 默认使用思源黑体。

- [思源黑体](https://github.com/adobe-fonts/source-han-sans)
