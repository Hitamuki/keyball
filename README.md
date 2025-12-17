# メモ

## フラッシュ手順

1. コンパイル
   - make keyball/keyball61:キーマップディレクトリ
   - qmk compile -kb keyball/keyball61 -km キーマップディレクトリ
2. ファームウェアのフラッシュ
   - CLIからフラッシュする
     - qmk flash
     - qmk flash -kb keyball/keyball61 -km キーマップディレクトリ
   - QMK Toolboxでフラッシュする
      1. hexファイルを選択し、Auto-Flashをチェック
      2. keyballのリセットボタン押下

## 環境最新更新

1. fork元から最新情報を取得する
   - git fetch upstream
   - git merge upstream/main

## 環境構築

1. QMK firmwareを取得
   - brew install qmk/qmk/qmk
2. QMK firmwareとサブモジュールをclone
   - git clone --recursive git@github.com:qmk/qmk_firmware.git
3. keyballリポジトリのfork
   - fork元のリポジトリを追加
      - git remote add [リモート追跡ブランチ名] [fork元のリポジトリのURL]
4. シンボリックリンクを作成し、keyballリポジトリをqmk_firmwareリポジトリに組み込む
   - ln -s ~/[path]/keyball/qmk_firmware/keyboards/keyball ~/[path]/qmk_firmware/keyboards/keyball
5. コンパイル
   - make keyball/keyball61:キーマップディレクトリ
   - qmk compile -kb keyball/keyball61 -km キーマップディレクトリ

## 予備知識

| 用語     | 説明                                 |
| -------- | ------------------------------------ |
| keymap.c | キーの配置、レイヤーや独自キーの設定 |
| rules.mk | 機能の有効/無効の設定                |
| rules.mk | 機能の詳細な設定                     |

## 注意点

- RGB LEDの設定はメモリ容量削減のためオミットする。

## 将来対応

- キースイッチをメンテナンスする
- 静音化する
- 静音リニアと静音タクタイルのキースイッチを厳選する
- keyball61 → keyball39に移行する
  - PCBカラーリング
  - ワイヤレス化
  - オートマウスレイヤー
- QMKを理解する
  - デバッグ
  - ドキュメントを読み込む
- RGB LEDをレイヤーに連動させる
- RE MAPで設定不要にするため、「keymap.c」でキー配列をカスタマイズする
- OLEDの表示をカスタマイズする
  - ねこの肉球、ねこを走らせる
- 3Dプリンターで自作する
  - keyballケース
  - トラックボールケース
  - OLEDカバー
- 自作キーキャップを製作する

## 参考

| 参考サイト                                              | URL                                                                               |
| ------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Automatic Mouse Layerの設定方法                         | <https://github.com/qmk/qmk_firmware/blob/master/docs/feature_pointing_device.md> |
| 自作キーボード「Keyball61」：おれのファームまとめ前編   | <https://mazcon.hatenablog.com/entry/2023/11/10/080000>                           |
| keyballのための はじめてのQMK firmware キーマップ作成編 | <https://note.com/yinouet1001/n/nc6d36cafd95b>                                    |
| keyballのための はじめてのQMK firmware環境構築 Mac編    | <https://note.com/yinouet1001/n/n856b45220ad4>                                    |
| （初心者編）Remapを使ってキーマップを書き換えよう       | <https://salicylic-acid3.hatenablog.com/entry/remap-manual>                       |
|                                                         | <>                                                                                |

## 後で参考

| 参考サイト                                                           | URL                                                                                                        |
| -------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| 自作キーボード「Keyball61」：おれのファームまとめ後編                | <https://mazcon.hatenablog.com/entry/2023/11/20/022521>                                                    |
| keyballのOLEDで猫ちゃんを走らせる                                    | <https://qiita.com/empelt/items/268389709a52cf533d13>                                                      |
| @t2_k10の開発した Keyball61 のファームウェア（OLEDで猫が走る）       | <https://github.com/empelt/keyball/tree/main/qmk_firmware/keyboards/keyball/keyball61/keymaps/cat>         |
| @d_kamiichiの開発した Keyball61 のファームウェア（自動マウスレイヤ） | <https://github.com/kamiichi99/keyball/tree/main/qmk_firmware/keyboards/keyball/keyball61/keymaps/kamidai> |
| Keyball61のLED制御をRGBMatrixに変更してTypingHeatmapを実現する       | <https://note.com/co_ke/n/nf89d0de0d718>                                                                   |
|                                                                      | <>                                                                                                         |

## 公式サイト

| 名前                   | URL                                   |
| ---------------------- | ------------------------------------- |
| RE MAP                 | <https://remap-keys.app/configure>    |
| QMK Firmware公式サイト | <https://docs.qmk.fm/#/>              |
| qmk_firmware GitHub    | <https://github.com/qmk/qmk_firmware> |
| keyball GitHub         | <https://github.com/Yowkees/keyball>  |

# Keyball Series

![Keyball61](./keyball61/doc/rev1/images/kb61_001.jpg)

Keyball series is keyboard family which have 100% track ball.

Keyboards in the family are:

* Available
    * Keyball39: split + 39 keys + a track ball
    * Keyball44: split + 44 keys + a track ball
    * Keyball61: split + 61 keys + a track ball
* Unavailable
    * Keyball46 (first one!)
    * One47

## Where to Buy

|Keyboard   |Yushakobo / 遊舎工房                       |Shirogane Lab / 白金ラボ                                   |
|-----------|-------------------------------------------|-----------------------------------------------------------|
|Keyball39  |<https://shop.yushakobo.jp/products/5357>  |<https://shirogane-lab.net/items/64b8f8693ee3fd0045280190> |
|Keyball44  |<https://shop.yushakobo.jp/products/8337>  |<https://shirogane-lab.net/items/64b7a006eb6dbe00346cd0c5> |
|Keyball61  |<https://shop.yushakobo.jp/products/5358>  |<https://shirogane-lab.net/items/64b8ed191435c1002bc4cd30> |

## Build Guide

*   Keyball39:
    [English/英語](/keyball39/doc/rev1/buildguide_en.md),
    [日本語/Japanese (ピンヘッダ版)](./keyball39/doc/rev1/buildguide_jp.md),
    [日本語/Japanese (コンスルー版)](./keyball39/doc/rev1/buildguide_jp_conth.md)
*   Keyball44: ~~English/英語~~ (Sorry, unavailable),
    [日本語/Japanese (ピンヘッダ版)](./keyball44/doc/rev1/buildguide_jp.md),
    [日本語/Japanese (コンスルー版)](./keyball44/doc/rev1/buildguide_jp_conth.md)
*   Keyball46:
    [English/英語](./keyball46/doc/rev1/buildguide_en.md),
    [日本語/Japanese](./keyball46/doc/rev1/buildguide_jp.md)
*   Keyball61:
    [English/英語](./keyball61/doc/rev1/buildguide_en.md),
    [日本語/Japanese (ピンヘッダ版)](./keyball61/doc/rev1/buildguide_jp.md),
    [日本語/Japanese (コンスルー版)](./keyball61/doc/rev1/buildguide_jp_conth.md)

## Firmware

See [document for firmware source code](./qmk_firmware/keyboards/keyball/readme.md).

### Pre-compiled Firmwares

(TO BE DOCUMENTED)
