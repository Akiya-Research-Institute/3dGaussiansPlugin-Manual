# システム要件

## 対応するUnreal Engineのバージョン

- 5.1
- 5.2
- 5.3
- 5.4
- 5.5
- 5.6

## 対応プラットフォーム

| Platform                   | Development      | Target Build |
| -------------------------- | ---------------- | ------------ |
| Windows 64bit              | ✅               | ✅          |
| Ubuntu 22.04 Desktop 64bit | ✅(Experimental) | ✅(Experimental) | 
| Android                    |                  | ✅(Experimental) |
| iOS                        |                  |              |
| Mac                        |                  |              |

!!! Warning "プラグインのダウンロードにWindowsが必要です"
    **Windows**のEpic Games Launcherを使用してプラグインをダウンロードする必要があります。

!!! Question "テスト済みUbuntu環境"
    下記の環境でのみテスト済みです。

    - OS: Ubuntu 22.04 Desktop 64bit
    - CPU: Intel i3-8350K
    - GPU: NVIDIA GeForce GTX 1080 Ti
        - Driver: 535.113.01
    - Unreal Engine: 5.1.1, 5.2.1, 5.3.1
    - .NET SDK: 6.0.123

    他の環境で正常に動作するかは保証できないので、Ubuntuの対応状況は「Experimental」としています。

!!! Question "テスト済みAndroidデバイス"
    下記のデバイスでのみテスト済みです。
 
    - Xiaomi Redmi Note 9S

    他の環境で正常に動作するかは保証できないので、Androidの対応状況は「Experimental」としています。

## 対応GPU

- DirectX 12に対応するGPU

<!-- NiagaraでGPUのみで使用できる機能を用いているため、本プラグインの使用にはGPUが必須です。  
なお、下記GPUについては開発チームにて動作することが確認されています。

- NVIDIA RTX 2060
- NVIDIA RTX 3070 -->
