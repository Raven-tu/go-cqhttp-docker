# go-cqhttp-ffmpeg

[Mrs4s/go-cqhttp](https://github.com/Mrs4s/go-cqhttp) 的 docker 镜像,添加了 ffmpeg ,支持语音转文字等功能。

## docker部署

**docker 使用架构为 `amd64`**

在release中下载最新的docker镜像，然后在docker中倒入镜像，然后运行即可。

以下是需要持久化的文件，均在工作目录下(即绝对路径为/app/再加上下表中的文件名)

| 路径                 | 文件名          | 作用       |
| :------------------- | :-------------- | :--------- |
| `/app/config.yml`    | `config.yml`    | 配置文件   |
| `/app/device.json`   | `device.json`   | 设备信息   |
| `/app/session.token` | `session.token` | token      |
| `/app/logs/`         | `logs`          | 日志文件夹 |
| `/app/data`          | `data`          | 数据文件夹 |

## 参考命令

```bash
docker run -itd --name go_cqhttp \
  -v /custom_directory/:/app \
  -p 6800:6800 \
  --restart always \
  go_cqhttp:2022-10-14
  # 注意使用正确的tag名称
```

## 感谢

- [Mrs4s/go-cqhttp](https://github.com/Mrs4s/go-cqhttp)
- [silicer/go-cqhttp](https://registry.hub.docker.com/r/silicer/go-cqhttp)
- [go-cqhttp 官方文档](https://docs.go-cqhttp.org/)
