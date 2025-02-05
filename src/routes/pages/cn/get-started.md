---
title: 开始使用 Nostr
description: 本指南将帮助你了解 Nostr 的基础知识，并帮助你完成所有设置并通过新帐户使用 Nostr。 我们将介绍如何创建新的闪电钱包、创建帐户以及安全登录客户端。
---

## [§](#了解密钥) 了解密钥

每个 Nostr 帐户都基于公钥/私钥对。 简而言之，你的公钥是你的用户名，你的私钥是你的密码。但有一个重要的区别：与密码不同，你的私钥丢失后将无法重置。

让我重复：**丢失私钥等于丢失你的帐户。如果别人获得对你的私钥的访问权，他们则可以控制你的帐户。**

确保你把私钥存储在安全的地方，例如密码管理器。我们推荐[1Password](https://1password.com/)。

## [§](#协议与客户端) 协议与客户端

Nostr 本身只是一个协议； 一套大家合意的在互联网上传递消息的步骤。

你将通过客户端访问 Nostr（协议）。 客户端可以是网络、桌面或移动应用程序。 一些 Nostr 客户端允许你通过粘贴你的私钥来登录。 在网络上，通常不推荐这样做——因为这样既不安全也不方便。 我们建议使用基于网络的加密钱包，这是一款专门设计用于管理私钥的软件。

[Alby](https://chrome.google.com/webstore/detail/alby-bitcoin-lightning-wa/iokeahhehimjnekafflcihljlcjccdbe) 是一款支持 Nostr 的比特币闪电钱包。 对于新用户来说，这是一个不错的选择。 我们将在下面针对各个客户端的指南中介绍如何安装 Alby。

## [§](#创建帐户) 创建帐户

以下是我们推荐的一些不同客户端的分步指南：

-   [Iris](/cn/guides/iris) （网络）
-   [达摩](/cn/guides/damus) (iOS)
-   [Amethyst](/cn/guides/amethyst) （安卓）

还有一些我们喜欢但没有指南的客户端：

-   [Snort](https://snort.social/) （网络） 超级干净和快速的网络客户端。
-   [Nostrgram](https://nostrgram.co) （网络） 有趣的 Instagram 启发客户端，专注于图像、视频和音频。

## [§](#找到朋友) 找到并关注朋友

-   如果你知道某人已经在使用 Nostr，你可以用他们的公钥搜索他们的帐户。
-   许多推特用户会把他们的公钥用带 #nostr 的推文公布。因此搜索此标签可以为你提供一个不错的开端。
-   [nostr.directory](https://nostr.directory) 是一个把推特用户跟他们的 Nostr 公钥配对的资料库。

## [§](#签署是什么) “签署”是什么意思？

跟 Nostr 协议交互的每一个操作都必须产生一个加密签名。这个签名可以比喻为一个验证步骤，以证明你的确是你声称的身份。

大部分 Nostr 客户端都试图把这一步变得简单快捷（或者允许你在客户端储存你的私钥，以便它们在你执行任何操作的时候代表你签署）。

如果我们只提供我们的公钥的话，我们每次想跟帖子互动或编辑个人档案的时候都会被客户端提示签署。当提示发生的时候，Alby 会自动弹出（就像注册那步一样）而你可以确认你的确想要签署.。

## [§](#可以使用其他客户端吗) 我可以使用其他客户端吗?

当然!你现在已经创建了你的公/私钥对，这意味着你可以在任何 Nostr 客户端上访问你的帐户。切记，客户端只是一个用于查看在 Nostr 协议上传播的信息的界面。

## [§](#下一步) 下一步

太好了，现在你已经设置了一个闪电钱包、一个身份（你的密钥对），并且已经尝试了一个客户端。当你进一步探索 Nostr 的时候，这里有一些方便链接：

-   [验证身份](/cn/verify-your-identity)
-   [中继器是什么？它们是怎么运作的？](cn/relays)
-   [了解关于 NIP 和协议开发的更多信息](/cn/the-protocol)
