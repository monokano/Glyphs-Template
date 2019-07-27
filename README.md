# Glyphsテンプレート

### Template_Adobe-Identity-0
* Adobe-Identity-0のテンプレートです。
* 用意したグリフは「.notdef」「space」「X」の３つのみ。
    * 「X」はIllustratorの縦組みでズレないようにする目的で仕込んでいます。
    * glyphOrderで「.notdef」「space」が先頭から並ぶようにしています。glyphOrderを編集する際は、この２つが必ず最初になるように維持しなければいけません。


### Template_Adobe-Japan1-3
* Adobe-Japan1-3のテンプレートです。
* AJ1-3のグリフを網羅しています。
* 禁止：グリフを削除したり追加したりしてはいけません。
* 禁止：フィーチャーを設定してはいけません。
* 禁止：glyphOrderを編集してはいけません。
    * glyphOrderでCID順に並ぶようにしています。つまりGlyphsのIDイコールCIDです。
* .rotatグリフにはベースグリフのコンポーネントを配置してあります。
    * [Glyphs-Scripts](https://github.com/monokano/Glyphs-Scripts)の「Set vrt2 VertWidth」でvertWidthを設定すると良いでしょう。
* 文字コードはAJ1-3の規格に合わせています。［グリフ情報を更新］をするとGlyphs独自の文字コード割り当てに変更されますが、書き出したフォントはAJ1-3の規格に合わせた文字コード割り当てになるので、［グリフ情報を更新］をしても無意味です。
* GlyphsはAJ1用のnice nameをサイレントで変更することがあります。Glyphsのバージョンに合ったテンプレートを使用してください。