便宜上、Solid には `on` ヘルパーが用意されており、計算のための明示的な依存関係を設定できます。これは主に、どの Signal を追跡するかをより明確にするための簡潔な方法として使用されます。しかし計算をすぐに実行せず、最初の変更時にのみ実行することもできます。`defer` オプションはこれを可能にします。

`a` が更新されたときだけ Effect を実行し、値が変わるまで実行を延期するようにしてみましょう。

```js
createEffect(on(a, (a) => {
  console.log(a, b());
}, { defer: true }));
```
