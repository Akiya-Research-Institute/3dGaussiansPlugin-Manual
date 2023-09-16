# 3D Gaussians Pluginって何？

[3D Gaussians Plugin](https://vrlab.akiya-souken.co.jp/products/threedgaussianplugin/)は、[3D Gaussian Splatting](https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/)のデータをUnreal Engineにインポートし、Unreal Engine上でリアルタイム描画するためのプラグインです。

<iframe width="560" height="315" src="https://www.youtube.com/embed/AGr__JrojZg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

- UEエディタ上で数クリックでインポートできます。
- RTX3070なら約30-100FPSでリアルタイム描画が可能(データ量に依存)。
- PythonやCUDAに依存せず、UEのNiagaraとMaterialで実装が完結しているため、様々な環境で動作します。
- [デモプロジェクト](./demo-project-overview)を無料でダウンロードできます。