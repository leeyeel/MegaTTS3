<div align="center">
    <h1>
    MegaTTS 3 <img src="./assets/fig/Hi.gif" width="40px">
    </h1>
    <p>
    Official PyTorch Implementation<br>
    </p>
</div>
<div align="center">
    <a href="https://huggingface.co/spaces/ByteDance/MegaTTS3"><img src="https://img.shields.io/badge/Hugging%20Face-Space%20Demo-yellow" alt="Hugging Face"></a>
    <a href="#"><img src="https://img.shields.io/badge/Platform-linux-lightgrey" alt="version"></a>
    <a href="#"><img src="https://img.shields.io/badge/Python-3.10-brightgreen" alt="version"></a>
    <a href="#"><img src="https://img.shields.io/badge/PyTorch-2.3.0-orange" alt="python"></a>
    <a href="#"><img src="https://img.shields.io/badge/License-Apache%202.0-blue.svg" alt="mit"></a>
</div>
<div align="center">
    <img src="https://img.shields.io/badge/Bytedance-%230077B5.svg?&style=flat-square&logo=bytedance&logoColor=white" />
    <img src="https://img.shields.io/badge/Zhejiang University-%230077B5.svg?&style=flat-square&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA1MTIgNTEyIj48IS0tIUZvbnQgQXdlc29tZSBGcmVlIDYuNy4yIGJ5IEBmb250YXdlc29tZSAtIGh0dHBzOi8vZm9udGF3ZXNvbWUuY29tIExpY2Vuc2UgLSBodHRwczovL2ZvbnRhd2Vzb21lLmNvbS9saWNlbnNlL2ZyZWUgQ29weXJpZ2h0IDIwMjUgRm9udGljb25zLCBJbmMuLS0+PHBhdGggZmlsbD0iI2ZmZmZmZiIgZD0iTTI0My40IDIuNmwtMjI0IDk2Yy0xNCA2LTIxLjggMjEtMTguNyAzNS44UzE2LjggMTYwIDMyIDE2MGwwIDhjMCAxMy4zIDEwLjcgMjQgMjQgMjRsNDAwIDBjMTMuMyAwIDI0LTEwLjcgMjQtMjRsMC04YzE1LjIgMCAyOC4zLTEwLjcgMzEuMy0yNS42cy00LjgtMjkuOS0xOC43LTM1LjhsLTIyNC05NmMtOC0zLjQtMTcuMi0zLjQtMjUuMiAwek0xMjggMjI0bC02NCAwIDAgMTk2LjNjLS42IC4zLTEuMiAuNy0xLjggMS4xbC00OCAzMmMtMTEuNyA3LjgtMTcgMjIuNC0xMi45IDM1LjlTMTcuOSA1MTIgMzIgNTEybDQ0OCAwYzE0LjEgMCAyNi41LTkuMiAzMC42LTIyLjdzLTEuMS0yOC4xLTEyLjktMzUuOWwtNDgtMzJjLS42LS40LTEuMi0uNy0xLjgtMS4xTDQ0OCAyMjRsLTY0IDAgMCAxOTItNDAgMCAwLTE5Mi02NCAwIDAgMTkyLTQ4IDAgMC0xOTItNjQgMCAwIDE5Mi00MCAwIDAtMTkyek0yNTYgNjRhMzIgMzIgMCAxIDEgMCA2NCAzMiAzMiAwIDEgMSAwLTY0eiIvPjwvc3ZnPg==&logoColor=white" />
</div>

## 使用说明

本项目是[bytedance/MegaTTS3](https://github.com/bytedance/MegaTTS3)的docker版本。默认启动webui。

<img src="./assets/fig/webui.png">

## 构建项目

请先把模型下载到项目根目录，并放置到`checkpoints`目录内，如果不想打包模型到镜像内，
可参考后面[checkpoints其他处理方式](#checkpoints其他处理方式)小节。

```
git clone https://github.com/bytedance/MegaTTS3.git
cd MegaTTS3
docker build . -t megatts3:latest
```

## 启动webui

使用GPU:

```
docker run -it -p 7929:7929 --gpus all -e CUDA_VISIBLE_DEVICES=0 megatts3:latest
```
使用CPU:

```
docker run -it -p 7929:7929  megatts3:latest
```
启动后访问`http://0.0.0.0:7929/`即可。


## checkpoints其他处理方式

如果不希望把checkpoints拷贝进容器，可以使用映射目录的方式，既可以节省一些构建时间，也可以显著减少镜像体积。

```
docker run -it -p 7929:7929 -v /your/path/checkpoints:/app/checkoupoints megatts3:latest

```

🟥 对于windows用户，如果采用目录映射的方式，一定要主要按照windows的路径方式书写:

```
docker run -it -p 7929:7929 -v D:\your\path\checkpoints:/app/checkoupoints megatts3:latest
```

## License
This project is licensed under the [Apache-2.0 License](LICENSE).

