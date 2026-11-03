# perch - Firmware (ZMK)

リストレスト型マウス（perch / シールド名: `wrist_mouse`）の XIAO BLE (nRF52840) 向け ZMK ファームウェアソースおよびビルド済みバイナリです。

## フォルダ構成
- `prebuilt/`: ビルド済みバイナリ
  - `wrist_mouse-xiao_ble__zmk-zmk.uf2`: 書き込み用 UF2 ファイル (shield: `wrist_mouse`)
- `shield/`: ZMK シールド定義
  - `wrist_mouse.overlay`: PMW3360 センサーの SPI ピン定義、IRQ、CPI 解像度設定
  - `wrist_mouse.conf`: Bluetooth スプリットペリフェラル設定
  - `wrist_mouse.keymap`: マッピング定義（ダミーマトリクス）
  - `Kconfig.shield`, `Kconfig.defconfig`: シールド認識用定義

## ハードウェア・ピンアサイン
- `PMW_CS` -> `D7` (`P0.06`)
- `SPI_SCK` -> `D8` (`P0.08`)
- `SPI_MISO` -> `D9` (`P0.17`)
- `SPI_MOSI` -> `D10` (`P0.20`)
- `PMW_MOT` (IRQ) -> `D6` (`P1.11`)
- デフォルト CPI: 1600 CPI (`wrist_mouse.overlay` で変更可能)

## 書き込み方法
1. XIAO BLE を USB 接続し、リセットボタンをダブルクリックします。
2. ドライブに `prebuilt/wrist_mouse-xiao_ble__zmk-zmk.uf2` をドラッグ＆ドロップします。
