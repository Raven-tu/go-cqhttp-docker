# go-cqhttp-ffmpeg-action

## **⚠️警告⚠️**:此版本为 dev 分支 action 构建版本，非稳定版本。

如需使用稳定版镜像请使用 [raventu/go-cqhttp-ffmpeg](https://hub.docker.com/r/raventu/go-cqhttp-ffmpeg)

[Mrs4s/go-cqhttp](https://github.com/Mrs4s/go-cqhttp) 的 docker 镜像,添加了 ffmpeg ,支持语音转文字等功能。

### docker部署

**docker 使用架构为 `amd64`**

- [raventu/go-cqhttp-ffmpeg-action](https://hub.docker.com/r/raventu/go-cqhttp-ffmpeg-action) 直接拉取镜像后运行即可。
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
  raventu/go-cqhttp-ffmpeg-action:latest
  # 注意使用正确的tag名称
```
