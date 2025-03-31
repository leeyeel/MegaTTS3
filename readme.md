<div align="center">
    <h1>
    MegaTTS 3 <img src="./assets/fig/Hi.gif" width="40px">
    </h1>
    <p>
    Official PyTorch Implementation<br>
    </p>
    <p></p>
    <img src="https://img.shields.io/badge/Bytedance-%230077B5.svg?&style=flat-square&logo=bytedance&logoColor=white" />
    <img src="https://img.shields.io/badge/Zhejiang University-%230077B5.svg?&style=flat-square&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA1MTIgNTEyIj48IS0tIUZvbnQgQXdlc29tZSBGcmVlIDYuNy4yIGJ5IEBmb250YXdlc29tZSAtIGh0dHBzOi8vZm9udGF3ZXNvbWUuY29tIExpY2Vuc2UgLSBodHRwczovL2ZvbnRhd2Vzb21lLmNvbS9saWNlbnNlL2ZyZWUgQ29weXJpZ2h0IDIwMjUgRm9udGljb25zLCBJbmMuLS0+PHBhdGggZmlsbD0iI2ZmZmZmZiIgZD0iTTI0My40IDIuNmwtMjI0IDk2Yy0xNCA2LTIxLjggMjEtMTguNyAzNS44UzE2LjggMTYwIDMyIDE2MGwwIDhjMCAxMy4zIDEwLjcgMjQgMjQgMjRsNDAwIDBjMTMuMyAwIDI0LTEwLjcgMjQtMjRsMC04YzE1LjIgMCAyOC4zLTEwLjcgMzEuMy0yNS42cy00LjgtMjkuOS0xOC43LTM1LjhsLTIyNC05NmMtOC0zLjQtMTcuMi0zLjQtMjUuMiAwek0xMjggMjI0bC02NCAwIDAgMTk2LjNjLS42IC4zLTEuMiAuNy0xLjggMS4xbC00OCAzMmMtMTEuNyA3LjgtMTcgMjIuNC0xMi45IDM1LjlTMTcuOSA1MTIgMzIgNTEybDQ0OCAwYzE0LjEgMCAyNi41LTkuMiAzMC42LTIyLjdzLTEuMS0yOC4xLTEyLjktMzUuOWwtNDgtMzJjLS42LS40LTEuMi0uNy0xLjgtMS4xTDQ0OCAyMjRsLTY0IDAgMCAxOTItNDAgMCAwLTE5Mi02NCAwIDAgMTkyLTQ4IDAgMC0xOTItNjQgMCAwIDE5Mi00MCAwIDAtMTkyek0yNTYgNjRhMzIgMzIgMCAxIDEgMCA2NCAzMiAzMiAwIDEgMSAwLTY0eiIvPjwvc3ZnPg==&logoColor=white" />
</div>

## 使用说明

本项目是[bytedance/MegaTTS3](https://github.com/bytedance/MegaTTS3)的docker版本。默认启动webui。

<img src="./assets/fig/webui.png">

## 构建项目

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

## License
This project is licensed under the [Apache-2.0 License](LICENSE).

