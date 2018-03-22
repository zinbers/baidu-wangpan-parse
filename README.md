#原始github链接 https://github.com/tychxn/baidu-wangpan-parse

# 百度网盘分享文件下载链接解析，并自动发送链接给aria2cGUI程序

## 功能

- 获取百度网盘分享文件的真实下载地址
- 将获取到的下载链接复制到[IDM](http://www.internetdownloadmanager.com/)、[FDM](https://www.freedownloadmanager.org/)等下载器即可实现高速下载，避免使用百度网盘客户端

## 运行环境

- Python 2.7

## 第三方库

- [Requests](http://docs.python-requests.org/en/master/)


## 使用帮助

```sh
$ python baidu_wangpan_parse.py -h 
usage: baidu_wangpan_parse.py [-h] -f [FOLDER] -e [ENCRYPT] -l LINK [-p PASSWORD]

Get Baidu wangpan private sharing file download link.

optional arguments:
  -h, --help            show this help message and exit
  -f [FOLDER], --folder [FOLDER]
                        Whether the sharing is a folder, input should be either "true" or "false"
  -l LINK, --link LINK  Baidu wangpan sharing file link
  
```

## 使用实例

1.获取没有加密的单个文件的下载地址：
```sh
$ python baidu_wangpan_parse.py -l "https://pan.baidu.com/s/1gC0EobepvMXpq6Eaz0ywJw"

```

2.获取加密的单个文件的下载地址：
```sh
$ python baidu_wangpan_parse.py -l "链接: https://pan.baidu.com/s/1ySq6bu2fkzGVaEimoY9fhg 密码: 8sgb"

```

3.获取没有加密的文件夹的打包下载地址
```sh
$ python baidu_wangpan_parse.py -f true -l "https://pan.baidu.com/s/1XYqoRcbXl5b--zmX3yijEQ"

```

4.获取加密的文件夹的打包下载地址
```sh
$ python baidu_wangpan_parse.py -f true -l "链接: https://pan.baidu.com/s/1pMosAp_y_YKyfWlo1tHhag 密码: tkay"

```

## 常见问题

文件打包下载后解压时提示`头部错误`， 解压失败。这个问题多发于`7-Zip`解压，换用`WinRAR`即可解压成功。

## Todo

- 解析文件夹的下载地址同时获取zip压缩包名字以及大小
