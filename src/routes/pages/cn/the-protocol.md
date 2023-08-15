---
title: Nostr 协议
description: 这是对 Nostr 协议的高层面概述，其中详细介绍了事件类型以及 Nostr 实现可能性 (NIP) 的工作原理。
---

## [§](#宏观) Nostr 宏观原理

-   Nostr 网络有两个主要组成部分：[客户端](/cn/clients)和[中继器](/cn/relays).
    -   **客户端** 是用户用来向中继器读取和写入数据的界面。在社交媒体环境中，可将其视为推特网络应用程序或移动应用程序。是一个允许你从推特的中央数据库读取数据和向其写入数据的客户端。
    -   **中继器** 就像数据库（尽管它们不仅仅是存储数据）。它们允许客户端向它们发送数据并将该数据存储在数据库中。然后客户端可以从中继中读取数据以显示给用户。
-   每个用户都由公钥标识。每个事件对象（例如，你发布的消息、更新你的关注列表等）都已签名。客户验证这些签名以确保它们是正确的。
-   客户端从中继获取数据并将数据发布到中继。中继器几乎总是由用户选择。中继不必相互通信，但将来可能会实现。三
-   例如，要更新你的个人档案，你只需指示你的客户端将类型 0 的事件发送到你要使用的中继。然后中继器将存储该事件。
-   在启动时，你的客户端从你告诉它的中继查询数据。这可以被过滤以仅显示你关注的用户的事件，或者你可以索取所有内容，然后客户端向你显示该数据。
-   有许多不同类型的事件。事件可以包含各种结构化数据。最常用的结构会被纳入 [Nostr 实现可能](#nips)（NIPs——大家都遵守的协议标准），因此所有客户端和中继器都可以无缝地处理它们。
-   你可以在 Nostr 上看到的数据完全取决于你决定连接的中继器。请参见下面的网络图。

### 网络图

![Nostr 网络图](/images/nostr-network.webp)

You can see the diagram above that we have 3 relays and 3 users. Each of the users is connecting to Nostr with a different client (and on a different Platform).

Given the reads and writes in the diagram:

-   Bob can see all of Alice's posts, but can't see anything from Mary (and doesn't even know she exists)
-   Alice can see all of Bob's posts, but can't see anything from Mary (and doesn't even know she exists)
-   Mary can see all of Bob's and Alice's posts. This is because while she only writes to Relay 3, she is reading from Relay 2, where Bob and Alice are writing their posts.

This is a very simplified situation but you can already see that the choice of which relays you want to connect to can have a large impact on who and what you'll see when using Nostr.

## [§](#事件) 事件

Events are the only object type on the Nostr network. Each event object has a `kind`, which denotes what sort of event it is (what sort of action a user might take or messages that might be received).

Here's what a kind 1 event looks like (kind 1 is for Short text notes – i.e. something like a Twitter tweet)

```json
{
    "id": "4376c65d2f232afbe9b882a35baa4f6fe8667c4e684749af565f981833ed6a65",
    "pubkey": "6e468422dfb74a5738702a8823b9b28168abab8655faacb6853cd0ee15deee93",
    "created_at": 1673347337,
    "kind": 1,
    "tags": [
        ["e", "3da979448d9ba263864c4d6f14984c423a3838364ec255f03c7904b1ae77f206"],
        ["p", "bf2376e17ba4ec269d10fcc996a4746b451152be9031fa48e74553dde5526bce"]
    ],
    "content": "Walled gardens became prisons, and nostr is the first step towards tearing down the prison walls.",
    "sig": "908a15e46fb4d8675bab026fc230a0e3542bfade63da02d542fb78b2a8513fcd0092619a2c8c1221e581946e0191f2af505dfdf8657a414dbca329186f009262"
}
```

-   The `id` field tells us the ID of the event
-   The `pubkey` field tells us the public key of the user who sent the event
-   The `created_at` field tells us when the event was published
-   The `kind` field tells us what sort of event it is
-   The `tags` field tells us about tags on the event. These are used for creating links, adding media, and mentioning other users or events.
-   The `content` field gives us the content of the event. In this case, the short text post.
-   The `sig` field is the signature that clients use to verify that the user with this pubkey did in fact send this event on the date specified.

### 事件种类

这是当前的 `事件` 种类列表。最新的列表能在 [Nostr NIPs 存储库](https://github.com/nostr-protocol/nips)查阅。

| 种类        | 描述                      | NIP         |
| ----------- | -------------------------------- | ----------- |
| 0           | 元数据                         | [1](01.md)  |
| 1           | 短文笔记                  | [1](01.md)  |
| 2           | 推荐中继器                  | [1](01.md)  |
| 3           | 联络簿                         | [2](02.md)  |
| 4           | 加密私信        | [4](04.md)  |
| 5           | 删除事件                   | [9](09.md)  |
| 6           | 转发                          | [18](18.md) |
| 7           | 回应                         | [25](25.md) |
| 8           | 奖励徽章                      | [58](58.md) |
| 40          | 创建频道                 | [28](28.md) |
| 41          | 频道元数据                 | [28](28.md) |
| 42          | 频道消息                  | [28](28.md) |
| 43          | 频道隐藏消息             | [28](28.md) |
| 44          | 频道静音用户                | [28](28.md) |
| 1984        | 举报                        | [56](56.md) |
| 9734        | 打闪请求                      | [57](57.md) |
| 9735        | 打闪                              | [57](57.md) |
| 10000       | 静音列表                        | [51](51.md) |
| 10001       | 置顶列表                         | [51](51.md) |
| 10002       | 中继器列表元数据              | [65](65.md) |
| 22242       | 客户端验证            | [42](42.md) |
| 24133       | Nostr Connect                    | [46](46.md) |
| 30000       | Categorized People List          | [51](51.md) |
| 30001       | Categorized Bookmark List        | [51](51.md) |
| 30008       | 个人档案徽章                   | [58](58.md) |
| 30009       | 徽章定义                 | [58](58.md) |
| 30023       | 长篇内容                | [23](23.md) |
| 30078       | Application-specific Data        | [78](78.md) |
| 1000-9999   | 常规事件                   | [16](16.md) |
| 10000-19999 | 可替换事件               | [16](16.md) |
| 20000-29999 | 临时事件                 | [16](16.md) |
| 30000-39999 | 参数化可替换事件         | [33](33.md) |

### Standardized Tags

| 名称       | value                   | other parameters  | NIP                      |
| ---------- | ----------------------- | ----------------- | ------------------------ |
| e          | event id (hex)          | relay URL, marker | [1](01.md), [10](10.md)  |
| p          | pubkey (hex)            | relay URL         | [1](01.md)               |
| a          | coordinates to an event | relay URL         | [33](33.md), [23](23.md) |
| r          | a reference (URL, etc)  |                   | [12](12.md)              |
| t          | hashtag                 |                   | [12](12.md)              |
| g          | geohash                 |                   | [12](12.md)              |
| nonce      | random                  |                   | [13](13.md)              |
| subject    | subject                 |                   | [14](14.md)              |
| d          | identifier              |                   | [33](33.md)              |
| expiration | unix timestamp (string) |                   | [40](40.md)              |

## [§](#nips) NIPs

A Nostr Implementation Possibilty, or NIP for short, exist to document what MUST, what SHOULD and what MAY be implemented by Nostr-compatible relay and client software. NIPs are the documents that outline how the Nostr protocol works.

### 我为什么要关心 NIP？

Nostr is decentralized and not owned by a centralized service (like Twitter). This means that the direction of the protocol is up to all of us! We can suggest and advocate for changes and offer feedback on ideas suggested by others.

Being an active part of the community gives you a say in the direction of the network. NIPs published in the main repository are already approved. Adding new ideas is done via Pull Request on that repo.

### 在哪里找得到 NIPs?

你可以在 [Nostr NIP 存储库](https://github.com/nostr-protocol/nips) 中查看所有当前的 NIP。