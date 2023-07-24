# [チュートリアル] Automatic1111 WebUIをローカルにインストールし、Stable Diffusion XL(SDXL)を無料で使用する方法

[![image] [![Hits] [![Twitter 新宮ラリ](https://img.shields.io/badge/Twitter-Follow%20Me-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/aisinguularity)

[![YouTube Channel](https://img.shields.io/badge/YouTube-SECourses-C50C0C?style=for-the-badge&logo=youtube)](https://www.youtube.com/@aisinguularity) [![新宮ラリプロフィール](https://www.beacons.ai/shingulari/) 

## 必要条件

**Pythonとgitのインストールの仕方
* [git for Windowsインストール(1:10~)](https://youtu.be/nJCwnd3QFX0?t=70)
* [Pythonインストール(1:50~)](https://youtu.be/nJCwnd3QFX0?t=110)


**Python 3.10.x (3.10.6, 3.10.9, 3.10.11) と git のダウンロードページ**
* git > https://gitforwindows.org/
* 3.10.9 > https://www.python.org/ftp/python/3.10.9/python-3.10.9-amd64.exe


## SDXL対応ComfyUIチュートリアル
* If you are interested in using ComfyUI checkout below tutorial
* [ComfyUI Tutorial - How to Install ComfyUI on Windows, RunPod & Google Colab | Stable Diffusion SDXL](https://youtu.be/FnMHbhvWUhE)
* Other native diffusers and very nice Gradio based tutorials
* [How To Use Stable Diffusion XL (SDXL 0.9) On Google Colab For Free](https://youtu.be/s2MQqmv6yAg)
* [Stable Diffusion XL (SDXL) Locally On Your PC - 8GB VRAM - Easy Tutorial With Automatic Installer](https://youtu.be/__7VNmnn5iU)
* [How To Use SDXL On RunPod Tutorial. Auto Installer & Refiner & Amazing Native Diffusers Based Gradio](https://youtu.be/gTdPRm-R-14)

## webui-user.batへの追記

* webui-user.bat ファイルを右クリックから編集して下記のパラメータを追加して下さい。
* ```set COMMANDLINE_ARGS=--no-half-vae --xformers```
* もし 'out of memory error' が出たら以下のパラメータを試して下さい。medvramから先に試して下さい。
* ```--no-half-vae``` はSDXLに必要ですが、 VAEエラーが出ない限りはStable Diffusion 1.5 モデルには使わない方がいいです。
* ```set COMMANDLINE_ARGS=--no-half-vae --xformers --medvram```
* ```set COMMANDLINE_ARGS=--no-half-vae --xformers --lowvram```

### 手動インストール方法

**SDXL safetensorsファイル２つを公式ページからダウンロードして下さい。**
* SDXL Base : https://huggingface.co/stabilityai/stable-diffusion-xl-base-0.9/tree/main
* SDXL Refiner : https://huggingface.co/stabilityai/stable-diffusion-xl-refiner-0.9/tree/main

**SDXL用WebUI1111のインストールの仕方**

* Automatic1111 レポ　リンク : https://github.com/AUTOMATIC1111/stable-diffusion-webui
* V1.5 SDXL 変更ログ : https://github.com/AUTOMATIC1111/stable-diffusion-webui/blob/release_candidate/CHANGELOG.md

* 最初に、Automatic1111 を動画で説明するフォルダ内へgit cloneして下さい。

* 次に、 そのフォルダ内でコマンドプロンプトを開き、 ブランチをdevへ変更します。（※7/24現在ではdevブランチのみSDXLに対応）
```
git checkout dev
```

* それから動画の通り、通常通りにインストールして下さい。

**既存のSD WebUIをアップグレードする時**

既にインストールしてあるWebUI1111フォルダー内でコマンドプロンプトを開き（動画を参照）

そしてアップグレードに必要な以下のコマンドを入力して下さい。 

```
git pull
```

Then checkout to dev version

```
git checkout dev
```

Then start as usual


## 動画で使用したプロンプト

Positive
```
photo of a male warrior, modelshoot style, (extremely detailed CG unity 8k wallpaper), full shot body photo of the most beautiful artwork in the world, medieval armor, professional majestic oil painting by Ed Blinkey, Atey Ghailan, Studio Ghibli, by Jeremy Mann, Greg Manchess, Antonio Moro, trending on ArtStation, trending on CGSociety, Intricate, High Detail, Sharp focus, dramatic, photorealistic painting art by midjourney and greg rutkowski
```

Negative
```
canvas frame, cartoon, 3d, ((disfigured)), ((bad art)), ((deformed)),((extra limbs)),((close up)),((b&w)), weird colors, blurry, (((duplicate))), ((morbid)), ((mutilated)), [out of frame], extra fingers, mutated hands, ((poorly drawn hands)), ((poorly drawn face)), (((mutation))), (((deformed))), ((ugly)), blurry, ((bad anatomy)), (((bad proportions))), ((extra limbs)), cloned face, (((disfigured))), out of frame, ugly, extra limbs, (bad anatomy), gross proportions, (malformed limbs), ((missing arms)), ((missing legs)), (((extra arms))), (((extra legs))), mutated hands, (fused fingers), (too many fingers), (((long neck))), Photoshop, video game, ugly, tiling, poorly drawn hands, poorly drawn feet, poorly drawn face, out of frame, mutation, mutated, extra limbs, extra legs, extra arms, disfigured, deformed, cross-eye, body out of frame, blurry, bad art, bad anatomy, 3d render
```

## 利用したコミットハッシュ 

4bf64976c1971fe2ff8931dd094306d297ebabcf



