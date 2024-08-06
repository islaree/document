### CSP - content security policy

CSP（コンテンツセキュリティポリシー）は、サーバーからのレスポンスを受けた後に、クライアントサイドでリソースのロードや実行を制御する仕組みです。

![image](https://github.com/user-attachments/assets/eaa0ec93-9083-4c2c-bd60-7d21f3901b8f)

コンテンツセキュリティポリシーでは、サーバーサイドで設定を行う必要があります。

CSPが設定されている場合レスポンスヘッダーには以下のようなものついています。

```
Content-Security-Policy: script-src 'self' https://true.com;
```

```html
<script src="https://true.com"></script> // 〇load
<script src="https://false.com"></script> // ×block
```

これは内部のscriptとtrue.comからのjavascriptのみを外部からロード可能なことを意味します。

このようにすることで許可していない外部からのscriptの読み込みをブロックすることができます。

ブロックはクライアントサイドで行われます。
