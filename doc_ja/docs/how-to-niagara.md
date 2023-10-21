# 描画処理のカスタム

## ローカル空間での描画

![](images/how-to-niagara-local.png){ loading=lazy }  

「Engine > Plugins > 3D Gaussians Content > Niagara > NE_3D_Gaussians」を開いてEmitter Propertiesの「Local Space」をオンにすると、ローカル空間でNiagaraの処理が行われるようになります。  
Sequencer等で3D Gaussians Splattingのアクタを実行時に動かす場合は、「Local Space」をオンにしておいてください。

## 独自のNiagaraを使う

「BP_3D_Gaussians_モデル名」の変数「Default > Advanced > Niagara Override」に任意のNiagara Systemを指定することで、描画処理にそのNiagaraを使用できます。  
主な使い方として、「Engine > Plugins > 3D Gaussians Content > Niagara」のNiagara Systemをコピーしてそこに処理を追加して独自のNiagara Systemを作成し、それを上記「Niagara Override」に指定する、という流れを想定しています。

### 例:Wind Forceによる移動

![](images/how-to-niagara-wind.gif){ loading=lazy }  

「Engine > Plugins > 3D Gaussians Content > Example > NS_3D_Gaussians_sh0_MoveByWindForce」を「Niagara Override」に指定すると、風でパーティクルが流されていくような効果が得られます。

### 例:Curl Noiseによる回転

![](images/how-to-niagara-curl.gif){ loading=lazy }  

「Engine > Plugins > 3D Gaussians Content > Example > NS_3D_Gaussians_sh0_RotateByCurlNoise」を「Niagara Override」に指定すると、風でパーティクルが揺れているような効果が得られます。