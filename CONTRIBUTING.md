# 欢迎来到贡献指南

本项目遵循开源协议 AGPL-3.0 license，任何想要参与到本项目中的个人或团体均可以按照本指南提交您的贡献。

您可以选择：
- [为自定义规则提交贡献](#为自定义规则提交贡献)
- [为在线规则页面提交贡献](#为在线规则页面提交贡献)

## 为自定义规则提交贡献
### 1. 提交规则前您需要检查的事项

提交规则前，你需要确认以下事项：
- 本项目是否已经存在相同规则
- 规则是否经过实际测试，确保不影响 App 的正常使用
- 规则是否通用（请勿提交基于控件 bounds 的规则，同一控件在不同设备上 bounds 都是不同的，基于 bounds 的规则通常只能适用于特定型号的设备）

### 2. 提交规则的流程

在您完成步骤 1 中的 [前置确认工作](#1-提交规则前您需要检查的事项) 后，您可以按照以下流程提交您的规则：
- Fork 本项目
- 从 main 分支创建一个新的分支
- 在新的分支上添加或修改相关文件
- 提交 Pull Request，并注明您修改的内容
- 等待合并入 main 分支

您需要了解本项目的文件夹结构：通常来说，App 包名是唯一的，而 App 名称有可能发生变更，因此本项目文件夹结构遵循包名规则。根目录下文件夹 A\~Z 代表存放的是包名首字母为 A\~Z 的 App 规则，例如：包名为 `tv.danmaku.bili` 的 App 规则文件存放在文件夹 `T/tv.danmaku.bili` 中。

一般情况下，包名根据域名反转而来，因此，大多数 App 的包名都是以 .com 或 .cn 开头。文件夹 C 中，有两个单独的子文件夹 cn 和 com，其中文件夹 cn 存放的是以 cn. 开头的包名的 App 规则，文件夹 com 存放的是以 com. 开头的包名的 App 规则；文件夹 com 下又细分 com.A ~ com.Z 文件夹。例如：包名为 `com.netease.cloudmusic` 的 App 规则文件存放在文件夹 `C/com/com.N/com.netease.cloudmusic` 中。

⚠ 由于目前以 cn. 开头的包名较少，因此暂时不需要在文件夹 cn 下细分 cn.A ~ cn.Z。

您需要根据提交的规则对应的 App 包名，找到相应文件夹(如果没有，您可以创建一个文件夹)，然后修改文件夹内的 readme.md 文件，如果您需要提供截图以方便对规则进行详细说明，请在文件夹内的 assets 子文件夹中新增或修改图片。

readme.md 文件的编写可参考 [模版](./Template.md)，您也可以参考现有 App 规则的 readme.md 文件。

### 3. 注意事项

1. 请务必在代码块中书写规则，代码块不需要设置语言，以 ``` 作为开头和结尾即可，以便自动导出规则的 java 程序可以以正确识别 readme.md 文件中规则所在的段落；
2. 代码块中的规则必须符合李跳跳的语法规则，否则会出现导入格式错误的问题；
3. 提供截图时请注意保护个人隐私，尤其是涉及金融和支付的 App，您应当自行处理关键信息，**本项目不对提交者由于意外泄露隐私导致的任何后果承担任何责任**；
3. 请谨慎删除已有规则，它们可能不适用于您设备上的 App 版本，但可能对其他版本的 App 有用。除非您有足够的理由说明此 App 曾经被错误提交，或者这条规则影响到了 App 的正常使用。

### 3. 相关链接

- [李跳跳进阶指南](https://juejin.cn/post/6938590373740544007)
- [李跳跳自定义规则参数说明](https://www.timeit.cn/post-543.html#:~:text=%E8%AE%BE%E7%BD%AE%E5%85%A5%E5%8F%A3%EF%BC%9A%E9%95%BF%E6%8C%89%E9%A6%96%E9%A1%B5%20%E6%9B%B4%E5%A4%9A%20%E6%8C%89%E9%92%AE%E3%80%82%20%E4%BF%AE%E6%94%B9%E8%B7%B3%E8%BF%87%E6%8F%90%E7%A4%BA%EF%BC%9A%20%7B%223%22%3A%22%E5%B0%8F%E7%8C%AA%E4%BD%A9%E5%A5%87%22%7D%20%E9%9A%90%E8%97%8F%E8%B7%B3%E8%BF%87%E6%8F%90%E7%A4%BA%EF%BC%9A%20%7B%224%22%3Atrue%7D,%E9%9A%90%E8%97%8F%E8%B7%B3%E8%B7%B3%E5%90%8E%E5%8F%B0%EF%BC%9A%20%7B%225%22%3Atrue%7D%20%E4%B8%80%E9%94%AE%E5%81%9C%E7%94%A8%E6%89%80%E6%9C%89APP%E7%9A%84%E6%9C%8D%E5%8A%A1%EF%BC%9A%20%7B%226%22%3Afalse%7D%20%E5%BC%80%E5%90%AF%E5%89%8D%E5%8F%B0%E6%9C%8D%E5%8A%A1%EF%BC%9A%20%7B%227%22%3Atrue%7D%20%E4%BF%AE%E6%94%B9%E5%89%8D%E5%8F%B0%E6%9C%8D%E5%8A%A1%E6%96%87%E6%A1%88%EF%BC%9A%20%7B%2210%22%3A%22%E6%B4%BE%E5%A4%A7%E6%98%9F%3A%E6%88%91%E4%BB%AC%E4%B8%80%E8%B5%B7%E5%8E%BB%E6%8A%93%E6%B0%B4%E6%AF%8D%E5%90%A7~%22%7D)

## 为在线规则页面提交贡献
本项目的 [pages](https://github.com/Snoopy1866/LiTiaotiao-Custom-Rules/tree/pages) 分支提供了一个 [在线规则页面](https://snoopy1866.github.io/LiTiaotiao-Custom-Rules/)，您可以提交 Pull Request 帮助完善此页面。