# Glyphsテンプレート

### Template_Adobe-Identity-0
* Adobe-Identity-0のテンプレートです。
* 用意したグリフは「.notdef」「space」「X」の３つのみ。
    * 「X」はIllustratorの縦組みでズレないようにする目的で仕込んでいます。
    * glyphOrderで「.notdef」「space」が先頭から並ぶようにしています。glyphOrderを編集する際は、この２つが必ず最初になるように維持しなければいけません。


### Templates_AJ1-3(StdN)
* Adobe-Japan1-3(StdN)のテンプレートです。
    * 要 Glyphs 2.6.2 以降
    * GlyphsはAJ1用のグリフ名を変更することがあります。Glyphsのバージョンに合ったテンプレートを使用してください。
* グリフを網羅しています（令和グリフは未対応）。
    * グリフ幅を 1000/600/500 の3つに分けています。
    * 1000は全角グリフ。600は欧文グリフ。500は半角幅グリフ。
* 「〓」をコンポーネント配置してあります（空白文字を除く）。        
* .rotatグリフにはベースグリフをコンポーネント配置してあります。
    * ベースグリフを編集すると、自動的に.rotatグリフへ反映されます。
    * ただし、vertWidth（縦組時の縦方向のグリフ幅）だけは反映されません。
    * vertWidthは、[Glyphs-Scripts](https://github.com/monokano/Glyphs-Scripts)の「Set vertWidth for vrt2 Glyph」で一括に設定できます。
#### Templates_AJ1-3の注意点
* 禁止：グリフを削除したり追加したりしてはいけません。
* 禁止：グリフ名を変更してはいけません。
* 禁止：OpenTypeフィーチャーを設定してはいけません。
    * フォント書出時にGlyphsが自動的に仕込むので、それにまかせてください。
* 禁止：glyphOrderを編集してはいけません。
    * glyphOrderでCID順に並ぶようにしています。
* 禁止：［グリフ情報を更新］をしてはいけません。
    * ［グリフ情報を更新］を実行するとグリフ名が変更されてしまいます。
* 書き出されたフォントにはROS情報が間違っている問題があります。「[GlyphsのAJ1の問題と対処 - 2. ROS編](https://gist.github.com/monokano/a3cf2992b8246720c5edc9abe12a65af)」で説明していますが、簡便な対処方法が今のところないので、そのままでもいいかなぁ…。


### Sample_AJ1-3(StdN)
* Templates_AJ1-3(StdN)へ実際に字形パスを納めてみたサンプルです。
* 字形パスはIPAex明朝を使用しています。IPAex明朝になかったグリフは〓のままです。
* 要件等はTemplates_AJ1-3(StdN)と同じ。


## 更新履歴
#### 2020.11.20
ファイル名に使用可能なGlyphsバージョンの範囲を明記した。

#### 2020.10.3
Sample_AJ1-3(StdN)を追加した。

#### 2020.9.28
Adobe-Japan1用を1-3のみにして、グリフに「〓」を仕込んだ。

#### 2019.12.17
「Templates_AJ1_Glyphs2.6.3-1271」を追加。なお、Glyphs2.6.2でAJ1用nice nameの一部が変更されています。

#### 2019.9.14　Template_Adobe-Identity-0
Adobeアプリで日本語フォントとして認識されるようにunicodeRangesを追加した。

#### 2019.8.16
フォント書き出し時に結合文字の文字コードを持つグリフの幅をGlyphsが自動的にゼロにしてしまう仕様を回避するため、マスターのカスタムパラメータに「DisableAllAutomaticBehaviour」を追加した。