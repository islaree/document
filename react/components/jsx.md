### JSX

コンテンツを HTML で、デザインを CSS で、ロジックを JavaScript で保持していました。

しかし、Web がよりインタラクティブになるにつれて、ロジックがコンテンツを決定することが多くなりました。JavaScript が HTML を担当するようになりました。これが、React でレンダリング ロジックとマークアップが同じ場所、つまりコンポーネントに共存する理由です。

```javascript
export default function Sidebar() {
  return
    <>
      {isLoggedIn ? (
        <p>welcome</p>
      ) : (
        <Form />
      )}
    </>
}
```

### JSXのルール

1. 単一のルートを返す
2. すべてのタグを閉じる
3. キャメルケースにする

```javascript
export default function Bio() {
  return (
    <div>
      <div className="intro">
        <h1>Welcome to my website!</h1>
      </div>
      <p className="summary">
        You can find my thoughts here.
        <br /><br />
        <b>And <i>pictures</i></b> of scientists!
      </p>
    </div>
  );
}
```

### 中括弧を使用したJSX

`{}`内にはjavascriptを記述することが可能です。
