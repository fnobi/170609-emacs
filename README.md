# <span>Emacs布教資料</span><span>（基礎編）</span>

## Emacsって？

> the extensible, customizable, self-documenting, real-time display editor

- オープンソース。1970年ごろから開発が始まる。

- Emacs.appも、ターミナル上で起動するタイプもあるよ

- Vimと比較対象に挙がることが多い
  - **Vimmerより偏屈な人が多い ※所感**

## 宗教戦争？

[http://dev.ariel-networks.com/wp/archives/1280](http://dev.ariel-networks.com/wp/archives/1280)

![yurushi](/slide/yurushi.png)

## キーバインド

- `control + なにか` を主体としたキーバインド
  - とにかく左手小指を伸ばしましょう
- いくつかのキーバインドは、Macのテキストフィールド等々でも使用可能なので、覚えておくとMacでのテキスト作成全般がスピードアップします


## elisp

- Emacsの全ては **lisp** で書かれており、エディタを拡張したい場合・プラグインを使いたい場合はlispを使うことになる
  - lisp: カッコでくくったリストで全ての処理を記述する非常に原理主義的な言語
    - **神の言語**
  - lispは使う処理系によっていろいろと「方言」があり、Emacsで使われるものはelispと呼ばれる

### sample

```
(defun write-rough ()
  "現在のbufferをいいかんじのファイル名で保存します"
  (interactive)
  (setq rough (rough-file-name 0))
  (write-file rough)
  (message (format "write to %s" rough)))
```

```
(defun rough-file-name (index)
  (setq dir (expand-file-name "~/Documents/rough"))
  (setq today (shell-command-to-string "echo -n $(date +%y%m%d)"))
  (setq filename (if (> index 0)
                   (format "%s/%s_rough-%d.md" dir today index)
                   (format "%s/%s_rough.md" dir today)))
  (if (file-exists-p filename) (rough-file-name (+ index 1)) filename))
```

## よく使われるプラグイン

- [auto-complete](https://github.com/auto-complete/auto-complete)
  - 補完（言語ごとにカスタマイズ等可能）

- [anything](https://www.emacswiki.org/emacs/Anything) / [helm](https://github.com/emacs-helm/helm)
  - 対象とするファイルをインクリメンタルサーチして、一括で同じ処理をかける

- [yasnippet](https://github.com/joaotavora/yasnippet)
  - スニペットを管理する

## 最近の悩み

- パッケージマネージャーがいまいち安定しない
- 開発が止まらないか心配

- [Spaceemacs](https://github.com/syl20bnr/spacemacs) とかいうやつは基本vimです
  - [Evil: EmacsをVimのごとく使う - 導入編 - 貳佰伍拾陸夜日記](http://tarao.hatenablog.com/entry/20130303/evil_intro)
