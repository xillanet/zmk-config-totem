<picture>
  <source media="(prefers-color-scheme: dark)" srcset="/docs/images/TOTEM_logo_dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="/docs/images/TOTEM_logo_bright.svg">
  <img alt="TOTEM logo font" src="/docs/images/TOTEM_logo_bright.svg">
</picture>

# ZMK CONFIG FOR THE ONE-HANDED KEYBOARD USING TOTEM

[Here](https://github.com/GEIGEIGEIST/totem) you can find the hardware files and build guide.\
[Here](https://github.com/GEIGEIGEIST/qmk-config-totem) you can find the QMK config for the TOTEM.

Original TOTEM is a 38 key column-staggered split keyboard running [ZMK](https://zmk.dev/) or [QMK](https://docs.qmk.fm/). It's meant to be used with a SEEED XIAO BLE or RP2040.
This fork is design for one-handed use and is specifically for Japanese.

本フォークは無線分割キーボード「TOTEM」の左手側（または右手側）を独立した片手用キーボードとして運用するための個人用設定レポジトリになります。
配列は改良中のため、配列図は省略します。

## 本フォークの特徴
- **片手入力最適化配列** TOTEMの片側（19キー）だけでほぼ一通りのキー入力を可能としている。
- **日本語特化配列** 日本語だけならばレイヤー切り替えが最小となるようにデザイン。
  - 濁音は対応する清音のレイヤー切り替えに配置。
  - 母音は中指と薬指に集中配置。同じ指が連続して異なるキーを叩かないように配慮。
  - 英文やプログラミング言語は不得意。
- **4レイヤー構成** 基本レイヤーと親指キーで切り替えるサブ、数字、ナビの4レイヤー構成。ほぼすべてのキーにマップ済み。
  - 基本レイヤーは母音と子音の清音。
  - 親指左キーはバックスペース兼ナビレイヤー。カーソルや修飾キー、Bluetooth設定キーを配置。
  - 親指右キーはスペース兼サブレイヤー。濁音や読点、日本語入力で使わない文字。
  - 親指中央キーはエンター兼数字レイヤー。数字キーは電話由来の配列。記号もこちら。
- **英語キーボード** 英語キーボードとして設計。iPhoneやMac、Androidに対応。
  - 数字を含む各キーのシフト入力の記号などの対応は英語キーボード準拠なので注意。
  - 英語キーボードなのでペアリング時のトラブルが起きにくい。
- **ホールドタップ不使用** GUIキーなどはスティッキーキーを使用。Shiftキーのみ専用キーだが、単押しは言語切替。
- **2026年6月時点のビルドで安定動作** ビルドエラーを回避するためにZMKのバージョンを`v0.2`に固定。


## 備忘録：ハードウェアの調達
- AliExpressで1〜2万円でハンダ済みの完成品を購入できる。
  - Choc V1のみとChoc V1/V2両対応版があるので注意。
  - XIAO BLEのものが主流と思われるが、有線版もあるのかも。
  - XIAO BLEはモジュール自体が日本の技適を取得している。
  - 当然だが両手を買っても使うのは片手だけ。左右鏡像配置でも学習コストは高め。っｙ

## 備忘録：キー配列のカスタマイズ
- レポジトリをフォークする。
- [キーマップエディタ](https://nickcoutsos.github.io/keymap-editor/)に自分のレポジトリを読み込ませる。
- カスタマイズしたらSaveする。

## 備忘録：ファームの書き込み方法
- TOTEMの電源を切り、USBケーブルでPCに接続する。
- 側面のボタンスイッチを2連打する。
- PCにドライブがマウントされるので、そこにビルドしたファームウェア（.uf2）をコピーする。
- コピーが終わると強制アンマウントされるが、ファームウェアは書き換わる。
