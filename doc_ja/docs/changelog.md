# 更新履歴

## v1.2 (2023/9/24)
- UE5.1と5.2に対応しました。
- 色をsRGBとして扱うかリニアとして扱うかのオプションを追加しました。BPのDetailsタブから設定できます。
- Apache-2.0の非公式実装[taichi_3d_gaussian_splatting](https://github.com/wanmeihuali/taichi_3d_gaussian_splatting)からの[変換手順](../how-to-unofficial)を追加しました。
- アクターのスケールを変更すると正しく描画できないバグを修正しました。
- Spherical Harmonics Degree 1以上で、アクターの回転が色の計算に含まれていないバグを修正しました。

## v1.1 (2023/9/22)
- 色調整、および、トリミング機能を追加しました。BPのDetailsタブから設定できます。
- UEFNへ移行しやすくするためにアセットを刷新しました。[UEFNへの移行方法はこちら](../how-to-uefn)。  
  この影響で、「Engine > Plugins > 3D Gaussians Content > Niagara」の下の一部のアセットへの直接のハード参照はv1.0と互換性がなくなりました。
- 一部のガウシアンが表示されないことがあるバグを修正しました。

## v1.0 (2023/9/19)
- 初版リリース