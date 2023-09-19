# FAQ

## Windows以外でも動したいです

開発チームではWindowsでのみテストを行っているので動くかどうかは保証できませんが、描画処理はNiagaraとMaterialの標準ノードで実装されているので、Windows以外でも動く可能性が高いです。

パッケージを作成するには、「C:\Program Files\Epic Games\UE_5.3\Engine\Plugins\Marketplace\ThreeDGaussians\ThreeDGaussians.uplugin」の22行目に目的のプラットフォームを追加する必要があります。

## パッケージサイズを減らすにはどうすればいいですか？

- Spherical Harmonics Degreeを「Degree 0」に設定します。
- sh1からsh11のテクスチャアセットをコンテンツブラウザで削除します。
  削除時に参照関係の警告が出ますが、強制的に削除を実行します。

## UEFNで動かすにはどうすればよいですか？

ドキュメントを作成中です。お待ちください。

## インポートしたBPをレベルに配置しても描画されません

- EnbaledBlocksのいずれか一つ以上がTrueになっていることを確認してください。
- ビューポートのリアルタイム表示がオンになっていることを確認してください。（Ctrl+R）

## インポートしたBPをレベルに配置するとクラッシュします

GPUのメモリが不足している可能性が高いです。下記をお試しください。

- BPを開き、EnbaledBlocksを一つだけ有効にする
- 空のレベルにBPを配置して描画する

## インポートしたBPをレベルに配置すると描画がおかしいです

- [Morton Orderでの分割](../how-to-split/#morton-order)の場合、ブロック間の描画順のソートは実行時のみ行われます。Playモードで確認してみてください。
- [原点からの距離での分割](../how-to-split/#_4)の場合、原点付近のブロックからのみ正しく描画されます。

## [3D Gaussian Splattingの公式実装](https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/)は商用利用不可ですが、このプラグインはどのような扱いですか？

- このプラグインは公式実装のソースコードは一切用いず、NiagaraとMaterialのノードベースプログラミングで一から実装されています（プラグインはCUDAやHLSLのソースコードを含んですらいません）。
  そのため、このプラグイン自体はUnreal Engineマーケットプレイスの通常の製品と同様に商用利用が可能です。
- ただし、ユーザが使用するデータの出所についてはユーザ自身が責任を負う必要があります。商用利用不可な方法で作成されたデータは商用利用できません。
- なお、既に公式実装以外にもMITライセンスなどで[非公式実装](https://github.com/WangFeng18/3d-gaussian-splatting)が公開されています。

## 3D Gaussian Splattingはフォトグラメトリの一種ですか？

いいえ。原理が大きく異なります。

## 3D Gaussian SplattingはNeRFの一種ですか？

いいえ。原理が大きく異なります。

## 3D Gaussian Splattingは微分可能レンダリングの一種ですか？

はい。