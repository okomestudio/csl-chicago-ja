# csl-chicago-ja

日本語文献のスタイルに最適化・ローカライズしたシカゴ書式（Chicago Manual of Style）のCSL（Citation Style Language）テンプレートです。

シカゴ書式のノート形式は学術論文にとどまらず英語圏では一般向けの書籍でも好まれている書式です。文中ではカッコを頻用せず引用元や出典を脚注にまとめることにより、読みやすく流れのよい文章を書くことができます。

## 背景と課題解決

シカゴ形式用の標準CSLファイルをそのまま日本語文献に適用すると、以下のような不自然な表記が発生します：

* 著者名が3名以上のときに「著者 A, 著者 B, and 著者 C」や「著者 A et al.」と出力される。
* 編集者や翻訳者が「edited by」「translated by」と表記される。
* 日本語の姓名の間に不要なカンマやスペースが入る。

本リポジトリのCSLファイルは、これら日本語文献におけるシカゴ書式のローカライズ要件をクリアするために調整されています。

Zotero、Pandoc、Emacs (org-cite / citeproc-el) などのCSL対応ツールでの使用を想定しています。

言語別のCSLテンプレートを別々のファイルとして用意することで、日本語と英語の文献が混在する環境で美しい引用・文献リストを出力をするために作成しています。ひとつのCSLファイルで複数言語の混在を可能にする[CSL-M](https://juris-m.github.io/cslm-docs/)への対応は確認していません。これについては[「コントリビューションについて」](#コントリビューションについて)にて後述します。

## 収録ファイル

リポジトリには以下のスタイルファイルを収録しています。

| ファイル名 | 引用形式 | 特徴 |
| :--- | :--- | :--- |
| `chicago-note-bibliography-ja.csl` | 註・文献リスト (Notes-Bib) | 脚注（Footnote）形式の引用と、巻末の文献リストを出力。 |

このファイルは[「Chicago Manual of Style」（第18版）](https://github.com/citation-style-language/styles/blob/master/chicago-notes-bibliography.csl)を元にして日本語対応スタイルを追加したものです。

著者—刊行年（Author-Year）形式のファイルは収録していません。

## コントリビューションについて

現時点でのメンテは[開発者](https://github.com/okomestudio)による個人プロジェクトとして行われています。

「このケースで読点やカッコの挙動がおかしい」「この文献タイプでの出力がシカゴ書式の日本語版ガイドラインと異なる」といった問題を見つけた場合は、イシューやプルリクエストなどをお気軽に寄せてください。開発者が個人的に扱っている文献に偏りがあるため、日本語対応を確認できていない種類の文献（「legal」など）が多い現状です。

日本語対応は、元のマクロ名に「-ja」という接尾文字列を加えた日本語対応マクロ（例えば「author-note」には「author-note-ja」など）を置換ではなく追記する形で行っています。ファイルサイズがおよそ倍になりますが、日英両方の言語で挙動をなるべく等しくすること、さらに、将来的な多言語対応を容易にするための妥協です。

開発者が環境を構築していないためCSL-M対応は未確認です。`citation`および`bibliography`ノード内には日本語対応と英語対応のふたつの`layout`ノードが残されています。標準CSLでは最初の`layout`のみ有効となるため、先に書かれている日本語版のみ有効になるようです。CSL-Mでは、これらのノードのロケール属性を適切に設定することによって多言語対応が可能になるはずです。このような、多言語環境での挙動の報告や、それを可能にするプルリクエストなども歓迎します。

## ライセンス

CSLプロジェクトの標準ライセンス（Creative Commons Attribution-ShareAlike 3.0 License）に準拠しています。

## 参考資料

[Official repository for Citation Style Language (CSL) citation styles](https://github.com/citation-style-language/styles).

[chicago-fullnote-bibliography-short-title-subsequent-ja-csl](https://github.com/kotobuki/chicago-fullnote-bibliography-short-title-subsequent-ja-csl). CSL-M対応版。CSM17版が元。CSLで対応が困難な問題には後処理スクリプトで対処。
