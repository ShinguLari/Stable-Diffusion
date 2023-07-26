# [チュートリアル] Automatic1111 WebUIをローカルにインストールし、Stable Diffusion XL(SDXL)を無料で使用する方法
[新宮ラリ・プロフィール](https://www.beacons.ai/shingulari/) 

[![Twitter 新宮ラリ](https://img.shields.io/badge/Twitter-Follow%20Me-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/aisinguularity)

[![YouTube Channel](https://img.shields.io/badge/YouTube-新宮ラリのAIシンギュラリティー-C50C0C?style=for-the-badge&logo=youtube)](https://www.youtube.com/@aisinguularity) 



<br>

## このしおりのgithubブランチ切り替えやSDXLのWebUI解説動画
[ブランチ切り替え方法解説動画](https://youtu.be/m7lq0BmMUvU)

[WebUI1.5.0簡単インストールと5つの運用方解説動画]()

<br>

## 必要条件

**Pythonとgitのインストールの仕方
* [git for Windowsインストール動画 (1:10~)](https://youtu.be/nJCwnd3QFX0?t=70)
* [Pythonインストール動画 (1:50~)](https://youtu.be/nJCwnd3QFX0?t=110)


**Python 3.10.x (3.10.6, 3.10.9, 3.10.11) と git のダウンロードページ**
* git -> https://gitforwindows.org/
* 3.10.9 -> https://www.python.org/ftp/python/3.10.9/python-3.10.9-amd64.exe

<br>

## SDXL対応ComfyUIチュートリアル
* ComfyUIでのSDXLの利用に興味がある方は、以下のチュートリアル動画をご覧ください。
* [SDXL0.9用ComfyUIノード（日本語版）🥳4Kアップスケーラー付き | Ultimate SD Upscale](https://youtu.be/XFe2-q7ZGxE)
* その他のネイティブdiffusersと、Gradioベースのチュートリアル動画
* [SDXL0.9をGoogle Colabで無料使い放題のツール、使い方解説](https://youtu.be/MYqYFbJRae8)

<br>

## webui-user.batへの追記
※次のチャプターの「手動インストール」を実行後に行って下さい。

* webui-user.bat ファイルを右クリックから編集して下記のパラメータを追加して下さい。
* ```set COMMANDLINE_ARGS=--xformers```

* ※--no half vaeの引数は無くても正式版1.5.0では動きました。

* もし 'out of memory error' が出たら以下のパラメータを試して下さい。medvramから先に試して下さい。
* ~```--no-half-vae``` はSDXLに必要ですが、 VAEエラーが出ない限りはStable Diffusion 1.5 モデルには使わない方がいいです。~
* ```set COMMANDLINE_ARGS=--xformers --medvram```
* ```set COMMANDLINE_ARGS=--xformers --lowvram```
  
<br>

### 手動インストール方法

**SDXL safetensorsファイル２つを公式ページからダウンロードして下さい。**
* SDXL Base : https://huggingface.co/stabilityai/stable-diffusion-xl-base-0.9/tree/main
* SDXL Refiner : https://huggingface.co/stabilityai/stable-diffusion-xl-refiner-0.9/tree/main
   
<br>

**SDXL用WebUI1111のインストールの仕方**

* 最初に、Automatic1111 をお好きなフォルダ内へgit cloneして下さい。

* Automatic1111 レポジトリ : https://github.com/AUTOMATIC1111/stable-diffusion-webui
```
git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui
```
* V1.5 SDXL 変更ログ : https://github.com/AUTOMATIC1111/stable-diffusion-webui/blob/release_candidate/CHANGELOG.md

* ※git cloneが完了したら、上のチャプターの「webui-user.batへの追記」を行って下さい。

* そして通常通りwebui-user.batをダブルクリックしてStable Diffusionを起動して下さい。

<br>

**既存のSD WebUIをアップグレードする時**

既にインストールしてあるWebUI1111フォルダー内でコマンドプロンプトを開き（動画を参照）

そしてアップグレードに必要な以下のコマンドを入力して下さい。 

```
git pull
```

※上のチャプターの「webui-user.batへの追記」を行って下さい。

そして通常通りwebui-user.batをダブルクリックしてStable Diffusionを起動して下さい。

<br>

## Link Shell Extension (シンボリックリンクツール）
[https://schinagl.priv.at/nt/hardlinkshellext/hardlinkshellext.html](https://schinagl.priv.at/nt/hardlinkshellext/hardlinkshellext.html)

<br>

## 動画で使用したプロンプト

Positive
```
chest-up portraitt photograhy of Beautiful cocasian girl 18 years old is wearing Kimono in Winter Kyoto Japan in snow weather,
Ultrarealistic, cinematic, fujifilm, snowy japanese old city, flowers, colorful, overcast sky, sunset
```

Negative
```
Deformed, unrealistic, bad quality, grainy, noisy, plastic, hazy, low contrast
```
  
<br>

## Githubのブランチをdevに変更したい時
devブランチの新機能を試したい時に使う

* SD WebUIフォルダー内で、CMDを押してコマンドプロンプトを立ち上げ、
```
git checkout dev
```

を入力する。
これでdevブランチに切り替えられる。

* あとは webui-user.bat をダブルクリックするとdevブランチの内容がダウンロードされる。

元のブランチに戻したい時は、
```
git checkout master
```
  
<br> 

## 今回利用したcommit hash

4bf64976c1971fe2ff8931dd094306d297ebabcf
