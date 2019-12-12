# IMSoftware
Based on coroutine IM communication software

# 依赖的库
```shell
go get github.com/go-xorm/xorm
go get github.com/gorilla/websocket
go get gopkg.in/fatih/set.v0
go get github.com/go-xorm/xorm
go get -u golang.org/x/time
go get -u golang.org/x/net
``` 

# 打包发布
# windows平台
::是注释的意思
直接运行build.bat
```bash
::remove dir
rd /s/q release
::make dir 
md release
::go build -ldflags "-H windowsgui" -o chat.exe
go build -o chat.exe
::
COPY chat.exe release\
COPY favicon.ico release\favicon.ico
::
XCOPY asset\*.* release\asset\  /s /e
XCOPY view\*.* release\view\  /s /e 
```
# linux平台
直接运行build.sh
```bash
#!/bin/sh
rm -rf ./release
mkdir  release
go build -o chat
chmod +x ./chat
cp chat ./release/
cp favicon.ico ./release/
cp -arf ./asset ./release/
cp -arf ./view ./release/