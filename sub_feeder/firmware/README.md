# Sub Feeder - Firmware (ZMK)

Seeed Studio XIAO BLE をホスト（Central）とし、Bluetooth 接続・スプリット通信・キー入力・光学センサー入力プロセッサを統括する ZMK ファームウェアです。

## フォルダ構成
- `prebuilt/`:
  - `left_device-xiao_ble__zmk-zmk.uf2`: Sub Feeder（シールド名: `left_device`）用ファームウェア
  - `settings_reset-xiao_ble__zmk-zmk.uf2`: BLEペアリングクリア用リセットファームウェア
- `shield/`:
  - `left_device.overlay`: スイッチマトリクス (Direct GPIO) および EC11 エンコーダーのピン定義
  - `left_device.keymap`: キーマップ、レイヤー、ホールドタップ、コンボ、および Wrist Mouse 入力プロセッサの動作定義
  - `left_device.conf`: ZMK スプリット設定、ポインティングデバイス有効化設定
  - `Kconfig.shield`, `Kconfig.defconfig`: シールド定義

## ピンアサイン
- SW2 (`KEY_1`) -> `D0` (`P0.02`)
- SW3 (`KEY_2`) -> `D1` (`P0.03`)
- SW4 (`KEY_3`) -> `D2` (`P0.28`)
- SW5 (`KEY_4`) -> `D3` (`P0.29`)
- SW6 (`KEY_5`) -> `D4` (`P0.04`)
- エンコーダー A相 (`ENC_A`) -> `D5` (`P0.05`)
- エンコーダー B相 (`ENC_B`) -> `D6` (`P1.11`)
- エンコーダー 押し込みSW (`ENC_SW`) -> `D7` (`P0.06`)

## 動作思想とレイヤー構成
詳細はルートの [README_ja.md](../../README_ja.md) をご参照ください。
- レイヤー0: 通常キー入力 & クリック（手首の移動は無効）
- レイヤー1 (SW1長押し): Bluetooth 3プロファイル切替、音量調整、ミュート
- レイヤー2 (SW6トグル / SW4ホールド): リストマウスのカーソル移動を有効化
- レイヤー3 (SW6 0.5s長押し): リストマウスの移動を上下反転スクロールに変換
