<picture>
  <source media="(prefers-color-scheme: dark)" srcset="/docs/images/TOTEM_logo_dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="/docs/images/TOTEM_logo_bright.svg">
  <img alt="TOTEM logo font" src="/docs/images/TOTEM_logo_bright.svg">
</picture>

# ZMK CONFIG FOR THE ONE-HANDED KEYBOARD USING TOTEM

[Here](https://github.com/GEIGEIGEIST/totem) you can find the hardware files and build guide.\
[Here](https://github.com/GEIGEIGEIST/qmk-config-totem) you can find the QMK config for the TOTEM.

Original TOTEM is a 38 key column-staggered split keyboard. This fork is using ZMK TOTEM and is design for one-handed use and is specifically for Japanese.

本フォークは無線分割キーボード「TOTEM」の左手側（または右手側）を独立した片手用キーボードとして運用するための個人用設定レポジトリになります。
完全に日本語の入力に特化した配列です。英語やプログラミングには不向きですが、その分、日本語入力は効率的になるようにデザインされています。
レイヤーを使っていますが、日本語の清音はレイヤー切り替えなしで入力可能です。濁音は清音キーのレイヤー切り替えに配置されています。4つのレイヤーを使うことで、ほぼすべての英数字と記号の入力が可能です。

## 本フォークの特徴
- **片手入力最適化配列** TOTEMの片側（19キー）だけでほぼ一通りのキー入力を可能としている。
- **日本語特化配列** 日本語だけならばレイヤー切り替えが最小となるようにデザイン。
  - 濁音は対応する清音のレイヤー切り替えに配置。
  - 母音は中指と薬指に集中配置。同じ指が連続して異なるキーを叩かないように配慮。
- **4レイヤー構成** レイヤーは、baseが基本。親指キーのホールドでnav、num、subと切り替える。
  - base_layerは母音と子音の清音。
  - nav_layerは親指左キーでバックスペース兼用。カーソルや修飾キー、Bluetooth設定キーを配置。
  - sub_layerは親指右キーでスペースキー兼用。濁音や読点、日本語入力で使わない文字。
  - num_layerは親指中央キーでリターンキー兼用。数字キーは電話由来の配列。各種記号キーも左右に配置。
- **英語キーボード設定向け** 英語キーボードとして設計。iPhoneやMac、Androidに対応。
  - Shiftキーによる記号などの対応は英語キーボード準拠なので注意。とくに数字キー。
  - 英語キーボードなのでペアリング時のトラブルが起きにくいハズ。
  - 言語切替のLANG1キーとLANG2キーがあるのえ、アップル製品とAndroidでは日本語・英語の切り替えが容易（Windowsは未検証）。
- **ホールドタップ不使用** GUI/ALT/CTRLキーはSticky Keyを使用。Shiftはホールド設定で単押しは言語切替。
- **2026年6月時点のビルドで安定動作** ビルドエラーを回避するためにZMKのバージョンを`v0.2`に固定。

<img width="494" height="417" alt="layer_0" src="https://github.com/user-attachments/assets/d5d2deb7-0b8c-4853-8681-9d9f8e19b34e" />
<img width="494" height="417" alt="layer_1" src="https://github.com/user-attachments/assets/6464531a-535d-4127-922a-5673665a5579" />
<img width="494" height="417" alt="layer_2" src="https://github.com/user-attachments/assets/75bb4ba1-2acf-4976-a5cf-e635212bc843" />
<img width="494" height="417" alt="layer_3" src="https://github.com/user-attachments/assets/135f02e7-da84-47a4-b93d-fcf91cbaf7c7" />

## 備忘録：用途の想定
- スマートフォンやタブレット、空間コンピュータデバイスなど。
- 寝ながらや立ったまま、安楽椅子など、フルキーボードで対応しにくい環境での活用。
- 右手に何かを持ったりし作業しながらの文字入力。

## 備忘録：ハードウェアの調達
- AliExpressで1〜2万円でハンダ済みのTOTEM完成品を購入できる。
  - Choc V1のみとChoc V1/V2両対応版があるので注意。
  - XIAO BLEのものが主流と思われるが、有線版もあるのかも（本レポジトリは非対応）。
  - XIAO BLEはモジュール自体が日本の技適を取得している。
  - 当然だが両手を買っても使うのは片手だけ。
  - Choc V2対応改修版にPurple Glede軸をつけて買ったけど、癖になるキータッチ。
  - KLP Lameキーキャップも押しやすいのでセット品はわりとオススメ。

## 備忘録：やったこと
- Gemini師匠にアドバイスを求めながらビルドエラーを解消。バージョンv2.0にしたのが決めてな模様。
- 右手は独立動作するように書き換え済み。右手は子機として左手に接続できない。

## 備忘録：キー配列のカスタマイズ
- レポジトリをフォークする。
- [キーマップエディタ](https://nickcoutsos.github.io/keymap-editor/)に自分のレポジトリを読み込ませる。
- カスタマイズしたらSaveすると、レポジトリ側に反映され、設定しておけば自動ビルド。

## 備忘録：ファームウェアの書き込み方法
- ファームウェアをビルドしてダウンロードする。
- TOTEMの電源を切り、USBケーブルでPCに接続する。
- 側面のボタンスイッチを2連打する。
- PCにドライブがマウントされるので、そこにビルドしたファームウェア（.uf2）をコピーする。
- コピーが終わると強制アンマウントされるが、ファームウェアは書き換わる。
