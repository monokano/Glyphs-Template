# Glyphsテンプレート

GlyphsでOpenType CFF（.otf）の日本語フォントを作るテンプレートです。

OpenType CFFを日本語フォントとして認識させるには、以下の条件にすべて該当する必要があります。
* cid-keyedである
* ROSが「Adobe-Identity-0」か「Adobe-Japan1-x」である
* CodePageRangeにJIS/Japanがある

テンプレートは、この条件に該当するように仕込みをしたGlyphsファイルです。

### Template_Adobe-Identity-0
* Adobe-Identity-0のテンプレート
* 用意したグリフは「.notdef」「space」「X」の３つのみ
     * glyphOrderで「.notdef」「space」が先頭から並ぶようにしています。glyphOrderを編集する際は、この２つが必ず最初になるように維持してください
   * 「X」はIllustratorの縦組みでズレないようにする目的で仕込んでいます

### Templates_AJ1-3(StdN)
* Adobe-Japan1-3(StdN)のテンプレート
    * Glyphsはアップデート時にAJ1用のグリフ名を変更することがあります。Glyphsのバージョンに合ったテンプレートを使用してください
* グリフを網羅しています（Glyphs 2用は令和グリフなし）
    * グリフ幅を 1000/600/500 の3つに分けています
    * 1000は全角グリフ。600は欧文グリフ。500は半角幅グリフ
* 「〓」をコンポーネント配置してあります（空白文字を除く）
* .rotatグリフにはベースグリフをコンポーネント配置してあります
    * ベースグリフを編集すると、自動的に.rotatグリフへ反映されます。ただしvertWidth（縦組時の縦方向のグリフ幅）だけは反映されません。[Glyphs-Scripts](https://github.com/monokano/Glyphs-Scripts)の「Set vertWidth for vrt2 Glyph」で設定してください
#### Templates_AJ1-3の注意点
* 禁止：グリフの削除や追加をしないでください
* 禁止：グリフ名を変更しないでください
* 禁止：OpenTypeフィーチャーを設定しないでください
    * Glyphs 2用はフォント書出時にGlyphsが自動的に仕込むので、それにまかせてください
    * Glyphs 3用はGSUBフィーチャーを外部ファイルから取り込んでいるので、それにまかせてください
* 禁止：glyphOrderを編集しないでください
* 禁止：［グリフ情報を更新］をしないでください
* Glyphs 2用は、書き出されたフォントのROSが間違っている問題があります。「[GlyphsのAJ1の問題と対処 - 2. ROS編](https://gist.github.com/monokano/a3cf2992b8246720c5edc9abe12a65af)」で説明していますが、簡便な対処方法が今のところないので、そのままでもいいかなぁ…
* Glyphs 3用は、Aj1-7に設定しています。それが正しいので変更しないでください

### Sample_AJ1-3(StdN)
* Templates_AJ1-3(StdN)へ実際に字形パスを納めてみたサンプル
* 字形パスはIPAex明朝を使用しています。IPAex明朝になかったグリフは〓のままです
* 要件等はTemplates_AJ1-3(StdN)と同じ

## Glyphs ダウンロードリンク
* [https://updates.glyphsapp.com/Glyphs2.6.2-1268.zip](https://updates.glyphsapp.com/Glyphs2.6.2-1268.zip)
* [https://updates.glyphsapp.com/Glyphs2.6.3-1271.zip](https://updates.glyphsapp.com/Glyphs2.6.3-1271.zip)
* [https://updates.glyphsapp.com/Glyphs2.6.4-1286.zip](https://updates.glyphsapp.com/Glyphs2.6.4-1286.zip)
* [https://updates.glyphsapp.com/Glyphs2.6.5-1342.zip](https://updates.glyphsapp.com/Glyphs2.6.5-1342.zip)
* [https://updates.glyphsapp.com/Glyphs2.6.6-1350.zip](https://updates.glyphsapp.com/Glyphs2.6.6-1350.zip)
* [https://updates.glyphsapp.com/Glyphs2.6.7-1359.zip](https://updates.glyphsapp.com/Glyphs2.6.7-1359.zip)
* [https://updates.glyphsapp.com/Glyphs2.6.8-1361.zip](https://updates.glyphsapp.com/Glyphs2.6.8-1361.zip)
* [https://updates.glyphsapp.com/Glyphs2.6.9-1363.zip](https://updates.glyphsapp.com/Glyphs2.6.9-1363.zip)
* [https://updates.glyphsapp.com/Glyphs3.0.4-3108.zip](https://updates.glyphsapp.com/Glyphs3.0.4-3108.zip)
* [https://updates.glyphsapp.com/Glyphs3.0.5-3131.zip](https://updates.glyphsapp.com/Glyphs3.0.5-3131.zip)
* [https://updates.glyphsapp.com/Glyphs3.1-3133.zip](https://updates.glyphsapp.com/Glyphs3.1-3133.zip)
* [https://updates.glyphsapp.com/Glyphs3.1.1-3148.zip](https://updates.glyphsapp.com/Glyphs3.1.1-3148.zip)

## GlyphsのAJ1用アプリ
* [Detect AJ1 Name Diff](https://tama-san.com/dl/files/Detect-AJ1-Name-Diff-102.tbz2)
	* Glyphsのバージョンによって異なるAJ1用グリフ名の差分を調べる
* [Repair AJ1 Name Diff](https://tama-san.com/dl/files/Repair-AJ1-Name-Diff-102.tbz2)
	* Glyphsのバージョンによって異なるAJ1用グリフ名の差分を調べ、glyphsファイルを修繕する
* [Convert AJ1 GSUB for Glyphs](https://tama-san.com/dl/files/Convert-AJ1-GSUB-for-Glyphs-100.tbz2)
	* Adobeが公開しているAJ1用GSUBファイルの「\cid」表記をnice nameに全置換する
* [AJ1 Explorer](https://tama-san.com/dl/files/AJ1-Explorer-2.2.1-34.tbz2)
	* AJ1のグリフの各種情報を閲覧する。GlyphsのAJ1用nice nameも取り込める

## 更新履歴

2023.1.2
* AI0テンプレートのunicodeRangesをcodePageRangesに変更した
* Glyphs3用AJ1テンプレートにcodePageRangesを追加した（G3でJIS/Japanが自動設定されないので）
* Glyphs3用AJ1サンプルを追加した
* ファイル名をなるべく簡潔にした

2022.11.28
* Glyphsのバージョンアップに合わせてフォルダ名を変更した

2022.5.26
* Glyphs3用テンプレートのGSUBファイル名を変更した

2022.5.24
* Glyphs3.0.4用のAJ1-3テンプレートを追加した

2021.12.22
* Glyphs2.6.6-2.6.7用のAJ1-3テンプレートを追加した
* Glyphs3用のAdobe-Identity-0テンプレートを追加した
* Glyphs2のダウンロードリンクを追加した
* GlyphsのAJ1用アプリを追加した

2020.11.20
* フォルダ名に使用可能なGlyphsバージョンの範囲を明記した

2020.10.3
* Sample_AJ1-3(StdN)を追加した

2020.9.28
* Adobe-Japan1用を1-3のみにして、グリフに「〓」を仕込んだ

2019.12.17
* 「Templates_AJ1_Glyphs2.6.3-1271」を追加。なお、Glyphs2.6.2でAJ1用nice nameの一部が変更されています

2019.9.14　Template_Adobe-Identity-0
* Adobeアプリで日本語フォントとして認識されるようにunicodeRangesを追加した

2019.8.16
* フォント書き出し時に結合文字の文字コードを持つグリフの幅をGlyphsが自動的にゼロにしてしまう仕様を回避するため、マスターのカスタムパラメータに「DisableAllAutomaticBehaviour」を追加した