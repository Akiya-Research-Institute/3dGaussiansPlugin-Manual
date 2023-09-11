# インポートとレベルへの配置

## インポート

![](images/how-to-import.png){ loading=lazy }  

1. UEエディタ上部のメニューで「Window > Import 3D Gaussians」を選択します
2. ダイアログ画面で、3D Gaussian Splattingの学習結果の「point_cloud.ply」を選択します。

!!! Failure "パスは英数字のみ"
	日本語などマルチバイト文字が含まれるパスからはインポートできません。  
	パスには英数字のみが含まれるようにしてください。

!!! Failure "フォルダ構造の制約"
	フォルダ構造は「モデル名 > point_cloud > iteration_n」となっている必要があります。

## レベルへの配置

![](images/how-to-place.png){ loading=lazy }  

1. コンテンツブラウザで「Content > ThreeDGaussians > モデル名」の下の「BP_3D_Gaussians_モデル名」をレベル上にドラッグ＆ドロップします。

また、必要に応じて詳細タブの「Default」の下の項目を設定します。

2. 「Bound Min」「Bound Max」でカリング範囲を指定できます。
3. 「SRGB」をオフにすると、元データをリニアカラーとして扱います。デフォルトのオンの状態ではsRGBとして扱います。
4. 「Mesh」をオンにすると、ガウシアンの大きさに応じた楕円体を描画します。主にデバッグに使用します。
