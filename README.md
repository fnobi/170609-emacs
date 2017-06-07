# <span>Emacs布教資料</span><span>（基礎編）</span>

## Emacsって？

> the extensible, customizable, self-documenting, real-time display editor

- オープンソース。1970年ごろから開発が始まる。

- Emacs.appも、ターミナル上で起動するタイプもあるよ

- Vimと比較対象に挙がることが多い
  - **Vimmerより偏屈な人が多い ※所感**



## キーバインド

- `control + なにか` を主体としたキーバインド
  - とにかく左手小指を伸ばしましょう
- いくつかのキーバインドは、Macのテキストフィールド等々でも使用可能なので、覚えておくとMacでのテキスト作成全般がスピードアップします


## elisp

- Emacsの全ては **lisp** で書かれており、エディタを拡張したい場合・プラグインを使いたい場合はlispを使うことになる
  - lisp: カッコでくくったリストで全ての処理を記述する非常に原理主義的な言語
  - lispは使う処理系によっていろいろと「方言」があり、Emacsで使われるものはelispと呼ばれる


## よく使われるプラグイン

- [auto-complete](https://github.com/auto-complete/auto-complete)
  - 補完（言語ごとにカスタマイズ等可能）

- [anything](https://www.emacswiki.org/emacs/Anything) / [helm](https://github.com/emacs-helm/helm)
  - 対象とするファイルをインクリメンタルサーチして、一括で同じ処理をかける

- [yasnippet](https://github.com/joaotavora/yasnippet)
  - スニペットを管理する

- [magit](https://github.com/magit/magit)
  - gitクライアント
