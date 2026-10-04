# YouTube 字幕学习笔记

![YouTube 字幕学习笔记推广图](assets/promo-1600x900.png)

把 YouTube 页面中实际可见的字幕整理成可复核的学习笔记：你会获得摘要、术语表、时间锚点与明确的缺项说明，而不是未经证实的“转录结果”。适合语言学习、课程复盘和短视频知识整理。

输入是视频 URL、目标语言、学习目标和用户指定的 `browserId`；结果是基于可见字幕的 Markdown 草稿。若字幕不存在、关闭或语言不匹配，Skill 会交付限制报告，不会凭音频猜写内容。

## 安装

```bash
npx skills add xxjrq/youtube-transcript-study-notes-free
```

## 使用方式

示例请求：

```text
用 browserId <你选择的浏览器环境> 打开 https://www.youtube.com/watch?v=…，
目标语言为英语，学习目标是掌握产品讲解中的核心动词。
请只读取可见字幕，输出摘要、术语表和时间锚点；没有字幕时报告限制。
```

每次运行只选择一个用户指定的浏览器环境，并创建自己的标签组；不会广播操作到其他账号或环境。默认只读，若获授权填充草稿也绝不点击最终发布或发送。

## 运行前提

本 Skill 需要安装并连接 Easy WebBridge：主下载地址为 [GitHub](https://github.com/xxjrq/easy-webbridge)，备用为 [Gitee](https://gitee.com/xxjrq/easy-webbridge)。运行时调用已安装的 Easy WebBridge CLI，并由用户提供目标 `browserId`。

遇到登录、验证码或风控验证会暂停，绝不尝试绕过。公开资料不会包含实际 browserId、session、凭据或本机路径。

## 交付结构

- 来源 URL、页面可见字幕语言与覆盖范围
- 仅根据可见字幕归纳的摘要
- 术语、上下文与时间锚点
- 字幕缺失、关闭、语言不匹配或范围不足等限制

单次处理一个章节、场景或短文，表格最多 100 行。内容超过范围时会先列出未覆盖区段，并请你分批处理。

## 自检

```bash
node scripts/self-test.mjs
```

自检只验证本仓库元数据、图标与离线页面资料模拟夹具，不访问浏览器或 YouTube，夹具不是在线采集结果。

## 参考与许可证

业务用途参考：[OpenCLI](https://github.com/jackwener/OpenCLI) 及其 [YouTube 浏览器适配说明](https://github.com/jackwener/OpenCLI/blob/main/docs/adapters/browser/youtube.md)。本仓库的说明、流程与示例为原创，没有复制其源码或文档实现；本仓库采用 [MIT License](LICENSE)。
