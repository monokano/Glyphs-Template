# Glyphsテンプレート

GlyphsでOpenType CFF（.otf）の日本語フォントを作るテンプレートです。

### Template_Adobe-Identity-0

Adobe-Identity-0 のテンプレート。用意したグリフは `.notdef` `space` `X` の3つのみ。

* glyphOrder は `.notdef` `space` が必ず先頭になるよう維持してください
* `X` は Illustrator の縦組みズレ対策（Illustrator 2025 (29) 以降は不要）
* マスターのカスタムパラメータに `DisableAllAutomaticBehaviour` を追加（結合文字グリフの幅自動ゼロ化を回避）
* マスターのカスタムパラメータに `Export vmtx Table` を追加（全グリフの天地幅が UPM と同一の場合に vmtx が生成されない問題を回避）

### Templates_AJ1-3 (StdN)

Adobe-Japan1-3 (StdN) のテンプレート。グリフ幅は全角 1000 / 欧文 600 / 半角 500 の3種。

* 空白文字を除くすべてのグリフに「〓」をコンポーネント配置
* `.rotat` グリフにはベースグリフをコンポーネント配置（編集が自動反映される）
* `vertWidth` のみ自動反映されません。[Glyphs-Scripts](https://github.com/monokano/Glyphs-Scripts) の `vrt2 Glyph_ Optimization.py` で設定してください
* `Template_Empty` は「〓」なしの空グリフ版です

**禁止事項：**

* グリフの削除・追加・改名
* OpenType フィーチャーの手動設定
* glyphOrder の編集
* 「グリフ情報を更新」の実行
* ROS の変更（AJ1-7 設定が正しい）

## リンク

* [Glyphs Versions](https://florianpircher.com/glyphs/versions/)

## 更新履歴

* **2026.3.25** Glyphs 3.4.1 (3436) 用に一新。旧ファイルを「OLD」に移動
