# perch - Circuit (基板・回路データ)

リストレスト型マウス（perch）の JLCPCB 発注用 Gerber データ、KiCad 設計ファイル、および SMT 実装用ファイル群です。

## ファイル構成
- `gerber/`: JLCPCB 発注用 Gerber ファイル一式
  - `wrist_mouse.zip`: JLCPCB にそのままアップロードする zip ファイル
- `jlcpcb_smt/`: JLCPCB SMT 部品実装用
  - `wrist_mouse_bom.csv`: 部品表 (BOM)
  - `wrist_mouse_cpl.csv`: 部品座標・実装角度表 (Pick & Place / CPL)
- `kicad/`: KiCad 設計データ (`wrist_mouse.kicad_sch`, `wrist_mouse.kicad_pcb` など)

## JLCPCB 発注手順
1. JLCPCB の PCB 発注画面で `gerber/wrist_mouse.zip` をアップロードします。
2. 仕様: 2層, 厚み **1.6mm** (推奨) または 1.2mm。
3. **PCB Assembly (SMT)** を選択し、表面 (Top Layer) 実装を指定します。
4. `jlcpcb_smt/wrist_mouse_bom.csv` と `wrist_mouse_cpl.csv` をアップロードします。
5. 以下のチップ部品が自動実装されます：
   - C1, C4: 0.1uF 0805
   - C2: 1uF 0805
   - C3: 4.7uF 0805
   - R1, R3: 10k 0805
   - R2: 39Ω 0805
   - U2: TLV70019DDCR (1.9V LDO)
6. 手半田パーツ：
   - PixArt PMW3360 センサー & レンズ
   - Seeed Studio XIAO BLE
   - リチウムポリマーバッテリー (3.7V)

## ライセンス・著作権表示 (BOB-PMW3360-SUMI)
本基板の PMW3360 センサー回路および 1.9V LDO 電源回路（U2, U3, C1〜C4, R1〜R3）は、Tomotsugu Kaneko (@snize) 氏によるオープンソースハードウェア [BOB-PMW3360-SUMI](https://github.com/snize/BOB-PMW3360-SUMI)（CERN-OHL-P v2 ライセンス）を元に改変・統合した設計です。
詳細はルートの [README_ja.md](../../README_ja.md) および [LICENSE](../../LICENSE) をご覧ください。
