# Glyphsテンプレート

### Template_Adobe-Identity-0
* Adobe-Identity-0のテンプレートです。
* 用意したグリフは「.notdef」「space」「X」の３つのみ。
    * 「X」はIllustratorの縦組みでズレないようにする目的で仕込んでいます。
    * glyphOrderで「.notdef」「space」が先頭から並ぶようにしています。glyphOrderを編集する際は、この２つが必ず最初になるように維持しなければいけません。


### Template_Adobe-Japan1
* Adobe-Japan1のテンプレートです。
* グリフを網羅しています。すべて字形パスがない空グリフです。
* .rotatグリフにはベースグリフをコンポーネントとして配置してあります。
    * [Glyphs-Scripts](https://github.com/monokano/Glyphs-Scripts)の「Set vertWidth for vrt2 Glyph」でvertWidthを設定すると良いでしょう。
* GlyphsはAJ1用のnice nameをサイレントで変更することがあります。Glyphsのバージョンに合ったテンプレートを使用してください。
    * バージョンが異なっても、テンプレートをそのままフォント書き出しをしてエラーにならなければ大丈夫です。
* 禁止：グリフを削除したり追加したりしてはいけません。
* 禁止：OpenTypeフィーチャーを設定してはいけません。
    * フォント書出時にGlyphsがGSUBを自動的に仕込んでくれるので、それにまかせてください。
    * Glyphsが使用しているGSUBファイルは間違っているので、1-4以降は「[GlyphsのAJ1の問題と対処 - 1. GSUB編](https://gist.github.com/monokano/edff98aabdee6c99c54f1107c62cd2ef)」の対処方法でGSUBファイルを差し替えてください。
* 禁止：glyphOrderを編集してはいけません。
    * glyphOrderでCID順に並ぶようにしています。
* 禁止：［グリフ情報を更新］をしてはいけません。
    * ［グリフ情報を更新］を実行するとグリフ名が変更されてしまいます。
* 書き出されたフォントにはROS情報が間違っている問題があります。「[GlyphsのAJ1の問題と対処 - 2. ROS編](https://gist.github.com/monokano/a3cf2992b8246720c5edc9abe12a65af)」で説明していますが、簡便な対処方法が今のところないので、そのままでもいいかなぁ…。


## 更新履歴
#### 2019.12.17
「Templates_AJ1_Glyphs2.6.3-1271」を追加。なお、Glyphs2.6.2でAJ1用nice nameの一部が変更されています。
#### 2019.9.14　Template_Adobe-Identity-0
Adobeアプリで日本語フォントとして認識されるようにunicodeRangesを追加。
#### 2019.8.16
フォント書き出し時に結合文字の文字コードを持つグリフの幅をGlyphsが自動的にゼロにしてしまう仕様を回避するため、マスターのカスタムパラメータに「DisableAllAutomaticBehaviour」を追加した。