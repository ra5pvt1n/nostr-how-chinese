---
title: 开始使用达摩
description: 通过达摩 iOS 客户端开始使用 Nostr 的分步指南。
---

## 第一步 - 获取达摩

这是一份开始使用 Nostr 和[达摩](https://damus.io/) 的具体指南。达摩是一个漂亮、易于使用的 iOS 客户端，由[@jb55](https://snort.social/p/npub1xtscya34g58tk0z605fvr788k263gsu6cy9x0mhnm87echrgufzsevkk5s)建造。

1. 从 iOS 应用商店[安装达摩](https://apps.apple.com/app/damus/id1628663131)。
1. 当你打开应用程序时，你可以选择创建一个新帐户或使用已经生成的私钥登录。
1. 如果你已经通过 Alby 扩展程序或其他客户端创建了私钥，则可以点击“登录”。否则，点击“创建帐户”。
   ![达摩登录页面](/images/damus-login.webp)

## 第二步 - 创建新帐户

1. 点击“创建帐户”。
1. 阅读并接受用户条款。
1. 然后选一个用户名（以后可以更改）并且可以选择添加其他个人档案详细信息。达摩在这一步会自动为你生成密钥。你的公钥将以“帐户 ID”呈现。![达摩注册页面](/images/damus-signup.webp)
1. 完成后，点击“创建”，你就可以开始使用 Nostr 了！ 🤙
1. 最后一个**极其重要**的步骤。你必须将私钥备份到安全的地方。
1. 点击左上角的头像进入菜单。然后点击设置，再点击密钥 ![达摩设置](/images/damus-settings.webp)
1. 你会看到你的“公开帐户 ID”。这是你的公钥。还有你的“帐户私钥”。这是你的私钥。
1. 将这两个字符串复制到**非常**安全的地方。1Password 或另一个密码管理器是不错的选择。切记，如果你不保存这些字符串的话，你将无法恢复你的帐户。你可以在此查阅 [更多关于密钥的信息](/cn/get-started#了解密钥).

## 使用现有密钥登录

1. 点击“登录”。
1. 阅读并接受用户条款。
1. 然后你会被要求提供你的私钥。输入你的密钥，就完成了。 🤙 **重要**：你的私钥在本地存储，不会以任何方式被达摩服务器收集或存储。
