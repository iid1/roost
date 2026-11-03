# perch - 3D Models (ケース・筐体データ)

リストレスト型マウス（perch）の筐体・シェル用 3D モデルデータです。

## フォルダ構成
- `stl/`: 3D プリンター出力用データ
  - `wrist_mouse.stl`: 一体成型・基本シェル STL
- `step/`: CAD 編集・寸法確認用データ
  - `wrist_mouse_upper_v1_4.step`: アッパーシェル (v1.4)
  - `wrist_mouse_cap_v1_4.step`: トップキャップ (v1.4)
  - `wrist_mouse.step`: アセンブリモデル
  - `FusionComponent.3mf`: Fusion 360 / 3MF コンポーネントデータ

## 推奨プリント設定
- **方式**: FDM または 光造形 (SLA / MJF)
- **素材**: PLA / PETG / レジン (MJFナイロン推奨)
- **積層ピッチ**: 0.12mm 〜 0.16mm (高精度)
- **インフィル**: 20% 〜 40% (ジャイロイドまたはグリッド)
