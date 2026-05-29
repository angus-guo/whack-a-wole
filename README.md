# 打地鼠小游戏

一个用 HTML、CSS 和 JavaScript 写成的网页打地鼠小游戏。玩家选择关卡后，需要在 30 秒内点击足够数量的地鼠。地鼠会在鼠标悬停后短暂延迟再逃跑，既保留挑战性，也让玩家有机会点中。

## 功能特点

- 纯前端实现，无需安装依赖
- 1-10 关可选，每关 30 秒限时挑战
- 第 1 关目标 5 只，第 10 关目标 30 只
- 地鼠只会出现在绿色草地区域
- 鼠标悬停 400ms 后地鼠会逃跑
- 使用本地卡通图片作为地鼠形象
- 支持在本机或局域网内通过浏览器访问

## 如何运行

在项目目录下启动一个静态服务器：

```powershell
python -m http.server 8765 --bind 127.0.0.1
```

然后在浏览器打开：

```text
http://127.0.0.1:8765/index.html
```

## 局域网访问

如果希望同一局域网内的其他电脑访问，把服务绑定到所有网卡：

```powershell
python -m http.server 8766 --bind 0.0.0.0
```

查看本机局域网 IP：

```powershell
ipconfig
```

其他电脑访问：

```text
http://你的局域网IP:8766/index.html
```

例如：

```text
http://192.168.84.19:8766/index.html
```

如果无法访问，请确认两台电脑在同一局域网内，并检查 Wi-Fi 是否开启了客户端隔离。

## 项目结构

```text
.
├── assets/
│   └── cartoon-mole.png
├── index.html
└── README.md
```

## 技术说明

项目核心逻辑在 `index.html` 中：

- 使用 CSS 构建天空、草地、计分板和动画效果
- 使用 JavaScript 监听地鼠按钮的 `mouseover` 和 `click` 事件
- 通过随机修改按钮的 `left` 和 `top` 控制地鼠位置
- 通过 `setInterval` 实现 30 秒倒计时
- 通过关卡配置控制每关目标数量

## GitHub 仓库

<https://github.com/angus-guo/whack-a-wole>
