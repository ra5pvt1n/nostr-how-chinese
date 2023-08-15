---
title: Nostr 客户端是什么？
description: Nostr 客户端的概要和一些我们推荐的客户端。
---

## [§](#客户端是什么) 客户端是什么？

Nostr 中的客户端是一个用来访问协议和跟协议互动的应用程序。就像用推特的 iOS 应用或网络应用来与推文互动一样。

由于 Nostr 协议本身非常简单而灵活，不同的客户端侧重于以略有不同的方式实现协议的不同方面。例如，一些客户端专注于美观而可用的用户界面，而其他客户端更专注于启用闪电支付，还有更多的创意用例，例如用 Nostr 下棋 （没错，你能用 Nostr [下棋](https://jesterui.github.io/)）。

很多现有的客户端都专注于社交媒体应用。但我们也开始看到一些更有趣的用途。

一些例子：

-   [Jester](https://jesterui.github.io/): 在 Nostr 上下棋
-   [Habla](https://habla.news/): 长篇内容 -- 类似 Medium
-   [Nostrgram](https://nostrgram.co/): 专注媒体的社交客户端

## [§](#可以切换客户端) 我可以切换客户端吗？

可以。因为客户端只是呈现中继器持有的数据的一个方式，你可以切换客户端或登陆多个客户端。只要每个客户端都从同一套中继器获取数据，你在每个客户端中所看到的会是同样的信息。

## [§](#客户端私钥) 我是否应该在客户端上输入我的私钥？

通常，最好不要在任何客户端上输入你的私钥。大多数要求提供私钥的客户端都尽全力保护你的密钥，但考虑到软件的性质，总会存在可能暴露你的私钥的漏洞和错误。

请记住，你的私钥是你在 Nostr 上的身份。如果它被泄露，你将不得不从头开始重建你的身份。而且你将丢失你的粉丝列表和所有私信。

## [§](#推荐客户端) 一些我们推荐的客户端

### 网络

-   [Iris](https://iris.to) – 这是我们推荐给新用户的客户端。 [在此查看我们的指南](/cn/guides/iris).
-   [Snort](https://snort.social/)
-   [Nostrgram](https://nostrgram.co/)

### 桌面

-   [Gossip](https://www.github.com/mikedilger/gossip) – Gossip 是一个非常武断的桌面客户端，需要更多技术知识才能使用。回报是它让用户能够更好的控制他们与 Nostr 的交互方式。

### iOS

-   [达摩](https://apps.apple.com/app/damus/id1628663131) – 这是 Nostr 的第一个也是最好的 iOS 客户端。[在此查看我们的指南](/cn/guides/damus)。

### 安卓

-   [Amethyst](https://play.google.com/store/apps/details?id=com.vitorpamplona.amethyst) – 一个漂亮的安卓客户端。 [在此查看我们的指南](/cn/guides/amethyst)。
