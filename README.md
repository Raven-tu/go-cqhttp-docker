- [go-cqhttp-ffmpeg](#go-cqhttp-ffmpeg)
  - [docker部署](#docker部署)
  - [参考命令](#参考命令)
- [zerobot-plugin](#zerobot-plugin)
  - [docker部署](#docker部署-1)
  - [参考命令](#参考命令-1)
- [感谢](#感谢)

## go-cqhttp-ffmpeg

[Mrs4s/go-cqhttp](https://github.com/Mrs4s/go-cqhttp) 的 docker 镜像,添加了 ffmpeg ,支持语音转文字等功能。

### docker部署

**docker 使用架构为 `amd64`**

- [raventu/go-cqhttp-ffmpeg](https://hub.docker.com/r/raventu/go-cqhttp-ffmpeg) 直接拉取镜像后运行即可。
- 在 releases 中下载最新的docker镜像，然后在docker中导入镜像，然后运行即可。

以下是需要持久化的文件，均在工作目录下(即绝对路径为/app/再加上下表中的文件名)

| 路径                 | 文件名          | 作用       |
| :------------------- | :-------------- | :--------- |
| `/app/config.yml`    | `config.yml`    | 配置文件   |
| `/app/device.json`   | `device.json`   | 设备信息   |
| `/app/session.token` | `session.token` | token      |
| `/app/logs/`         | `logs`          | 日志文件夹 |
| `/app/data/`          | `data`          | 数据文件夹 |

### 参考命令

```bash
docker run -itd --name go_cqhttp \
  -v /custom_directory/config.yml:/app/config.yml \
  -p 6800:6800 \
  --restart always \
  raventu/go-cqhttp-ffmpeg:latest
  # 注意使用正确的tag名称
```

## zerobot-plugin

[FloatTech/ZeroBot-Plugin](https://github.com/FloatTech/ZeroBot-Plugin)的 docker 镜像使用最新 releases 构建。

### docker部署

**docker 使用架构为 `amd64`**

- [raventu/zerobot-plugin](https://hub.docker.com/r/raventu/zerobot-plugin) 直接拉取镜像后运行即可。
- 在 releases 中下载最新的docker镜像，然后在docker中导入镜像，然后运行即可。

以下是需要持久化的文件，均在工作目录下(即绝对路径为/app/再加上下表中的文件名)

| 路径                 | 文件名          | 作用       |
| :------------------- | :-------------- | :--------- |
| `/app/config.json`    | `config.json`    | 配置文件   |

### 参考命令

```bash
# 注意使用正确的tag名称
docker run -itd --name zerobot_plugin \
  -v /custom_directory/:/app \
  -p 6800:6800 \
  --restart always \
  raventu/zerobot-plugin:latest
```

## 感谢

- [Mrs4s/go-cqhttp](https://github.com/Mrs4s/go-cqhttp)
- [silicer/go-cqhttp](https://registry.hub.docker.com/r/silicer/go-cqhttp)
- [FloatTech/ZeroBot-Plugin](https://github.com/FloatTech/ZeroBot-Plugin)
- [go-cqhttp 官方文档](https://docs.go-cqhttp.org/)
