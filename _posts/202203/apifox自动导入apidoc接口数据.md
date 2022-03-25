---
layout:  post
title:  apifox自动导入apidoc接口数据
tags:
- Apifox
- Apifox自动导入
- apiDoc
categories:
- 清学小记
---

## 使用```apiDoc```生成接口数据
查看```apiDoc```[官方文档](https://apidocjs.com/)

- 全局安装```apiDoc```，必须安装```0.29.0```或以下版本；新版本不再支持生成```api_data.json```等数据文件，导致无法导入```Apifox```
```
npm install apidoc@0.29.0 -g
```

- 创建配置文件```apidoc.json```
```json
{
  "name": "example",
  "version": "1.0.0",
  "description": "apiDoc basic example",
  "title": "Custom apiDoc browser title",
  "url" : "https://api.github.com/v1"
}
```
- 生产文档命令
```
apidoc -i src -o apidoc/ -f .jsp
```

## 使用```Apifox```自动导入```apiDoc```数据
- 创建好项目
- 依次打开```项目设置```、```数据管理```、```导入数据(自动同步)```
- ```数据源格式```选择```apiDoc```，```数据源url```填入```http://xxx.xxx/api_data.json```
- ```保存```，```立即导入```
- 按需开启```自动导入```