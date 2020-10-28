> This doc isn't meant to be published and is only an internal note to contributors.

一般に、ドキュメントコンテキストルールがあります。ドキュメントの開発はWebサイトに、寄稿ドキュメントはリポジトリに移動します。 ただし、` @ redwoodjs / router `はRedwoodアプリの外部で使用できるため、Redwoodユーザーエクスペリエンスだけではなくなったため、このルールに違反する必要があります。

> Why design our packages so that they can work outside of Redwood apps too? Well, one of the reasons we made Redwood was to inject more integration into the JS ecosystem. And if we can accelerate this phenemenon, why wouldn't we?

So unless we want to face the perils of synchronizing changes across two docs in two places, the package's README kind of needs to have it all.

これは、このドキュメントを編集したい場合（そして編集した場合はありがとうございます！）、次のリンクを使用して` redwoodjs / redwood `リポジトリのルーターパッケージREADMEを編集し、PRを送信することを意味します。 そこに：https：//github.com/redwoodjs/redwood/blob/main/packages/router/README.md
