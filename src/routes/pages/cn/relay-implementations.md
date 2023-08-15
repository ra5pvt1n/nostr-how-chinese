---
title: 中继器实现
description: 这是 Nostr 中继规范的所有已知实现的列表。 打算自己运行中继器的话才需要。 中继器（到目前为止）与应用程序无关。 你可以运行自己的或使用任何或所有公共实例。
---

## Go

-   [Relayer Basic](https://github.com/fiatjaf/relayer/tree/master/basic): 由 Postgres 支持的简单参考中继，作为演示。在构建自定义中继的框架 [Relayer](https://github.com/fiatjaf/relayer) 上编写。

## C++

-   [Strfry](https://github.com/hoytech/strfry): C++ 无数据库中继实现

## C#

-   [NNostr](https://github.com/Kukks/NNostr): C# 中继

## Rust

-   [nostr-rs-relay](https://sr.ht/~gheartsfield/nostr-rs-relay/): 用 Rust 编写的简约中继，可将数据保存在 SQLite 上
-   [søstr](https://github.com/metasikander/s0str): 一个用 rust 编写的私有 nostr 中继，保存来自一个公钥的所有笔记并将它们发布给任何需要它们的人

## Node.js / Typescript

-   [nostream](https://github.com/Cameri/nostream): 由 PostgreSQL 支持的用 Typescript 编写的 nostr 中继（从 nostr-ts-relay 重命名）
-   [Minds Nostr Relay](https://gitlab.com/minds/infrastructure/nostr-relay): 开源社交网络 [Minds](https://www.minds.com) 的中继
    -   [Minds Engine - Nostr](https://gitlab.com/minds/engine/-/tree/master/Core/Nostr): 相关用于使用 Nostr 读/写 Minds 帖子的 Minds API 代码

## Clojure

-   [me.untethr.nostr-relay](https://github.com/atdixon/me.untethr.nostr-relay): 用 Clojure 编写的中继

## Python

-   [nostrypy](https://github.com/monty888/nostrpy): 用 python 编写的中继、客户端和其他工具
-   [nostr_relay](https://code.pobblelabs.org/fossil/nostr_relay/): 用 python 编写的 Nostr 中继，由 SQLite 支持

## Kotlin

-   [NostrPostr Relay](https://github.com/Giszmo/NostrPostr/tree/master/NostrRelay): 同时支持 SQLite 和 Postgresql 的 Kotlin 中继
-   [knostr](https://github.com/lpicanco/knostr): 在 Kotlin 中实现的 nostr 中继，支持 Postgres 和指标（micrometer）