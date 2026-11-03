# Sub Feeder - Circuit (基板・回路データ)

左手コントローラー（Sub Feeder）の KiCad 設計データ、JLCPCB 発注用 Gerber データです。

## フォルダ構成
- `gerber/`: JLCPCB 発注用 Gerber ファイル一式
  - `left_device.zip`: JLCPCB にそのままアップロードする zip ファイル
- `kicad/`: KiCad 設計データ (`left_device.kicad_sch`, `left_device.kicad_pcb`, `left_device.dxf` など)

## 部品構成 (BOM)
- **マイコン**: Seeed Studio XIAO BLE nRF52840 × 1
- **キースイッチ**: Kailh Choc V1 / V2 ロープロファイルスイッチ × 5
- **ホットスワップソケット**: Kailh Choc ソケット × 5
- **ロータリーエンコーダー**: EC11互換ロータリーエンコーダー (プッシュスイッチ付き) × 1
- **電源**: 3.7V リチウムポリマーバッテリー (JST-PH または直はんだ)

## JLCPCB 発注手順
1. `gerber/left_device.zip` を JLCPCB の PCB 発注画面にアップロードします。
2. 仕様: 2層, 1.6mm 厚, お好みの色（黒、紫など）。
3. 本基板はスルーホール・ソケット部品で構成されているため、SMT実装なし（PCB製造のみ）で安価に発注可能です。
