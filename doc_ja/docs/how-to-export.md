# マージとエクスポート

クロップ等を適用した状態で、複数のモデルをマージして一つの.plyファイルにエクスポートすることができます。  
下記のような場合に便利です。

- 不要部分を削除してファイルサイズを減らしたい
- 複数のモデルを組み合わせたシーンを作成したい

![](images/how-to-export.png){ loading=lazy }  

1. レベルに配置した「BP_3D_Gaussians_モデル名」を選択し、詳細タブの「Export」でエクスポート先を指定します。

	- **Export Directory**で、エクスポート先のフォルダを指定します。
	- **Export File Name**で、エクスポートする.plyファイル名を指定します。

2. 下記のボタンを押すことで.plyファイルをエクスポートできます。

	- **Export All**：レベル上の全ての3D Gaussiansアクタをマージされた1つの.plyファイルにエクスポートします。
	- **Export This**：この3D Gaussiansアクタを.plyファイルにエクスポートします。

	上記のいずれも、下記が適用された状態でエクスポートされます。

	- アクタのTransform
	- Enabled Block
	- Crop Volume、Kill Volume
