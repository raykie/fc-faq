# FC 经典解决方案

## 音视频

### 注意事项

- CPU 密集型场景， 建议直接单实例单并发

- 目前 FC runtime 已经在 python/java/custom runtime 内置了 FFmpeg

  - 自动化编译脚本如下：[https://github.com/rsonghuster/ffmpeg-static](https://github.com/rsonghuster/ffmpeg-static), 如果用户有能力对 FFmpeg 做二次开发， 可以参考这个编译。

  - 如果使用我们提供的 ffmpeg 和用户直接在 ecs 上 apt-get install 安装的 FFmpeg 有较大性能差异的话， 建议用户直接从 [https://johnvansickle.com/ffmpeg/](https://johnvansickle.com/ffmpeg/) 下载使用对应的 FFmpeg

- 建议新用户一开始就使用有状态异步调用、Destination、以及开启实例监控等

### ffmpeg 示例集锦

```
s init devsapp/ffmpeg-app -d ffmpeg-app
```

详情见: [ffmpeg-app](https://github.com/devsapp/ffmpeg-app)

- AudioConvert: 音频格式转换器
- GetMediaMeta: 获取音视频 meta
- TranscodeMaster/TranscodeWorker: 功能强大的并行视频转码器
- GetDuration: 获取音视频时长
- VideoGif: 功能强大的 video 提取为 gif 函数
- GetSprites: 功能强大雪碧图制作函数
- VideoWatermark: 功能强大的视频添加水印功能

### 视频转码

#### 1. 无编排单个函数直接转

[simple-video-processing](https://github.com/awesome-fc/simple-video-processing)

#### 2. 工作流编排并行加速转

[fnf-video-processing](https://github.com/awesome-fc/fc-fnf-video-processing)

### 全景录制

```
s init devsapp/start-headless-ffmpeg -d start-headless-ffmpeg
```

详情见: [start-headless-ffmpeg](https://github.com/devsapp/start-headless-ffmpeg)

### 视频直播流截图

```
s init devsapp/start-rtmp-snapshot -d start-rtmp-snapshot
```

详情见: [start-rtmp-snapshot](https://github.com/devsapp/start-rtmp-snapshot)

## AI

### 1. pytorch

```
s init devsapp/start-pytorch -d start-pytorch
```

详情见: [start-pytorch](https://github.com/devsapp/start-pytorch)

### 2. tensorflow

```
s init devsapp/start-tensorflow -d start-tensorflow
```

详情见: [start-tensorflow](https://github.com/devsapp/start-tensorflow)

### 3. OCR

```
s init devsapp/start-ocr -d start-ocr
```

详情见: [start-ocr](https://github.com/devsapp/start-ocr)

## 前端领域

### 1. Puppeter 应用示例

```
s init devsapp/start-puppeteer -d start-puppeteer
```

详情见: [puppeter 应用示例](https://github.com/devsapp/start-puppeteer)

提供了两种部署方式， nodejs12 runtime 和 custom container， 建议直接使用 custom container

### 2. SSR 应用示例

```
s init nodejs-nuxt
```

详情见 [nodejs-nuxt-ssr](https://github.com/devsapp/nodejs-nuxt)

## 文档图片转换相关

### 1. 基于 GS 和 GM 的 PDF 转 JPG 实践

```
s init devsapp/start-pdf2img -d start-pdf2img
```

详情见: [基于 GS 和 GM 的 PDF 转 JPG 实践](https://github.com/devsapp/start-pdf2img)

### 2. 基于 LibreOffice 实现 word 转 pdf

```
s init devsapp/start-word2pdf -d  start-word2pdf
```

详情见: [基于 LibreOffice 实现 word 转 pdf](https://github.com/devsapp/start-word2pdf)

## OSS 文件解压

[fc-decompress-oss](https://github.com/awesome-fc/decompress-oss)

readme 中有详细介绍

## Application-Awesome Repo

[Application-Awesome](https://github.com/devsapp/Application-Awesome)
