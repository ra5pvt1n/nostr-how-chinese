---
title: 获取 NIP-05 验证
description: 如何在 Nostr 上验证你的身份并获取验证标记和更简易的分享你的帐户的方法。
---

## [§](#你会学到什么) 你将在本指南中学到什么

你可能已经注意到，在许多不同的客户端上，有些用户有标记，就像在推特上一样。

NIP-05 指定了 Nostr 用户如何验证他们的身份。不同的客户端显示验证的方式略有不同，但这是向 Nostr 社区表明你是真实用户的重要方式。

![Snort 验证](/images/snort-verified.webp)

Nostr 的验证过程在名为 [NIP-05](https://github.com/nostr-protocol/nips/blob/master/05.md) 的 Nostr 实现可能性 (NIP) 中记录。

NIP-05 使 Nostr 用户能够将他们的公钥映射到基于 DNS 的互联网标识符。验证机制类似于谷歌要求你使用 DNS 记录验证你对域名的所有权的方式。

验证的主要好处是它允许通过人类可读的名称来识别 Nostr 用户，而不是通过长而难以记忆的公钥来识别。这使经过验证的 Nostr 用户能够轻松地与他人分享他们的身份。

为了利用 NIP-05，Nostr 用户将 nip05 url 添加到他们的个人档案中（大多数客户端都支持这一点）。NIP-05 网址看起来像电子邮件 – bob@example.com。让我们分部解释：

1. `@` 符号之前的所有内容（在我们的示例中为“bob”）。 这必须与你的 Nostr 配置文件中名称字段值相匹配。
1. `@` 符号后的所有内容（在我们的示例中为“example.com”）。这是客户端可以在其中查找包含用户名和公钥的“/.well-known/nostr.json”文件的域名。

当客户端看到 nip05 url 时，他们将在指定域中查找 `/.well-known/nostr.json` 文件。此文件必须包含指定用户的 nostr 公钥。阅读 NIP-05 规范了解的更多细节。

虽然这听起来很技术性，但获得验证却并不难。让我们看看如何完成。

## [§](#免费验证) 通过免费服务获取验证

目前，有几家供应商正在帮助人们免费获取验证。如果你的闪电钱包中还没有聪，这是一个很好的选择。如果可能，请通过捐款支持这些项目。⚡🤙

-   [Bitcoin Nostr](https://bitcoinnostr.com/)
-   [Nostrcheck.me](https://nostrcheck.me)
-   [Nostr.industries](https://nostr.industries/)

## [§](#付费验证) 支付提供商进行验证

如果你没有自己的域名或不想自己设置，你可以利用免费或付费（通常只花费几个[聪](https://coinmarketcap.com/alexandria/glossary/satoshi-sats)) NIP-05 服务。以下有几个：

-   [Nostrplebs](https://nostrplebs.com)
-   [Nostr Verified](nostrverified.com)
-   [Alby](getalby.com)
-   [Nostr Directory](https://nostr.directory)
-   [Nostr.band](https://nip05.nostr.band)
-   [Nostr.com.au](https://nostr.com.au)
-   [Vida](https://Vida.page)
-   [Stacker News](https://stacker.news)

## [§](#自托管) 自托管验证

如果你已经拥有自己的域名，这是一个免费选项。你只需将 .well-known/nostr.json 文件添加到你的域。该文件的内容应如下所示：

```json
{
    "names": {
        "你的_NOSTR_名称": "你的_NOSTR_十六进制公钥"
    }
}
```

你还可以选择添加一个部分，让客户端知道它们能在哪些中继器上找到你：

```json
{
  "names": {
    "你的_NOSTR_名称": "你的_NOSTR_十六进制公钥"
  },
  "relays": {
    "你的_NOSTR_十六进制公钥": [
      "wss://relay.one",
      "wss://relay.two",
      ...
    ]
  }
}
```

确保在 `nostr.json` 文件中使用十六进制版本的公钥。这是**不**以 `npub` 开头的密钥版本。

你可以在 [Nostr.band](https://nostr.band) 上转换你的密钥。

![获取你的十六进制公钥](/images/get-hex-key.webp)

最后，确保此文件的 `Access-Control-Allow-Origin` 标头设置为 `*`，因为它需要可供客户端访问。