# 環境変数

ターゲットに応じて、さまざまな方法でRedwoodプロジェクトの両側に環境変数を提供できます。

## API

### 開発

あなたのターゲットとしてNodeJSとAPI側では、あなたの中で定義された環境変数にアクセスすることができます`.env`と`.env.defaults`ファイルや、あなたのコードでそれらを参照する`process.env.MY_VAR_NAME` 。

### 製造

デプロイメントシステムには、関数が実行されるサーバーレス環境で環境変数を利用できるようにするための何らかの方法が必要になります。たとえば、Netlifyでは、設定の[ビルド環境変数](https://docs.netlify.com/configure-builds/environment-variables/)セクションでそれらを設定できます。

## ウェブ

Web側では、webpackをターゲットとして、次の3つのいずれかを実行できます。

1. 環境変数の前に` REDWOOD_ENV_ `を付けます—これらは<code data-md-type="codespan"> process.env.REDWOOD_ENV_MY_VAR_NAME を介して利用可能であり、ビルドフェーズ中に動的に置き換えられます。 これは、<code>process.env.REDWOOD_ENV_SECRET_API_KEY</code> が削除され、APIキーの<em data-md-type="emphasis"> actual 値に置き換えられるため、誰かがページのソースを調べた場合にそれを確認できることを意味します。 プレーンテキストで。 これは、静的JavascriptおよびHTMLファイルをブラウザに配信する際の制限です。</em></code></code>

2. `redwood.toml`それらをホワイトリストに登録します。例えば：

    ```toml
    [web]
      includeEnvironmentVariables = ['API_KEY']
    ```

    これらは、上記の最初のオプションと同様に、コードでも置き換えられます。

3. それらを`.env`ファイルで定義します。これは開発環境でのみ機能し、ENV変数が参照されている場所に応じて、エラーが発生するか、本番環境でサイレントに失敗します。
