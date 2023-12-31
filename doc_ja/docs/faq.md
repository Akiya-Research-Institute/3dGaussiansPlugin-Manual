# FAQ

## Windows, Linux, Android以外でも動したいです

テストしていないので動くかどうかは保証できませんが、描画処理はNiagaraとMaterialの標準ノードで実装されているので、その他のプラットフォームでも動く可能性が高いです。

パッケージを作成するには、「C:\Program Files\Epic Games\UE_5.3\Engine\Plugins\Marketplace\ThreeDGaussians\ThreeDGaussians.uplugin」の22行目と32行目に目的のプラットフォームを追加する必要があります。

## パッケージサイズを減らすにはどうすればいいですか？

- Spherical Harmonics Degreeを「Degree 0」に設定します。
- sh1からsh11のテクスチャアセットをコンテンツブラウザで削除します。
  削除時に参照関係の警告が出ますが、強制的に削除を実行します。

## インポートしたBPをレベルに配置しても描画されません

- Enabled Blocksのいずれか一つ以上がTrueになっていることを確認してください。
- ビューポートのリアルタイム表示がオンになっていることを確認してください。（Ctrl+R）

## インポートしたBPをレベルに配置するとクラッシュします

GPUのメモリが不足している可能性が高いです。下記をお試しください。

- BPを開き、Enabled Blocksを一つだけ有効にする
- 空のレベルにBPを配置して描画する

## インポートしたBPをレベルに配置すると描画がおかしいです

- [Morton Orderでの分割](../how-to-split/#morton-order)の場合、ブロック間の描画順のソートは実行時のみ行われます。Playモードで確認してみてください。
- [原点からの距離での分割](../how-to-split/#_4)の場合、原点付近のブロックからのみ正しく描画されます。

## レンダリングの結果が公式ビューアと一致しません

公式実装のビューアとは実装が根本的に異なるので、描画結果は必ずしも一致しません。

描画精度を上げる一つの方法は、BPのDetailsパネルで「Sprite Size」を大きくすることです。  
これにより、ガウス分布を描画するときのスプライトのサイズが大きくなり、ガウス分布の端まで正しく描画されるようになります。

## SceneCapture2Dで正しく描画されません

BPの詳細タブの「Default > Advanced > Render As 2D Gaussians」をオンにしてください。

3D Gaussianの本来の描画方法ではカメラとの相対的な位置関係等からスプライトのサイズと向きを計算します。このプラグインではその計算をNiagaraで行いますが、NiagaraはSceneCapture2Dのカメラ位置等を取得してくれません。「Render As 2D Gaussians」をオンにすると、カメラ位置等が必要なNiagaraでの計算を省略した近似的な描画方式に切り替わります。厳密には描画結果が不正確ですが、ほとんど気が付かれないレベルと思います。

## [3D Gaussian Splattingの公式実装](https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/)は商用利用不可ですが、このプラグインはどのような扱いですか？

- このプラグインは公式実装のソースコードは一切用いず、NiagaraとMaterialのノードベースプログラミングで一から実装されています（プラグインはCUDAやHLSLのソースコードを含んですらいません）。
  そのため、このプラグイン自体はUnreal Engineマーケットプレイスの通常の製品と同様に商用利用が可能です。
- ただし、ユーザが使用するデータの出所についてはユーザ自身が責任を負う必要があります。商用利用不可な方法で作成されたデータは商用利用できません。
- なお、既に公式実装以外にもApache-2.0ライセンスで[非公式実装](https://github.com/wanmeihuali/taichi_3d_gaussian_splatting)が公開されています。[非公式実装からの変換](../how-to-unofficial)をご覧ください。

## 3D Gaussian Splattingはフォトグラメトリの一種ですか？

いいえ。原理が大きく異なります。

## 3D Gaussian SplattingはNeRFの一種ですか？

いいえ。原理が大きく異なります。

## 3D Gaussian Splattingは微分可能レンダリングの一種ですか？

はい。