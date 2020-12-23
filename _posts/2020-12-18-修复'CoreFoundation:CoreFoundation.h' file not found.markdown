macOS 10.15 (Catalina) 更新部分（多关注man xcrun）：
macOS 10.15 下/System/Library/Frameworks/也缺少很多头/库文件，会导致很多软件编译失败。
比如：CoreFoundation（找不到 #include <CoreFoundation/CoreFoundation.h>），在这里我也一并处理了。

# csrutil disable   # 需要在恢复模式下运行命令，具体请自行搜索。
```$ xcode-select --install    # 安装常用开发工具，如：git等。
$ sudo mount -uw /	# 根目录挂载为可读写，否则无法在/usr/下建立文件，本修改重启前有效。
$ sudo ln -s "$(xcrun --show-sdk-path)/usr/include" /usr/include
$ export SDKROOT="$(xcrun --show-sdk-path)" # 设置环境变量
$ echo "export SDKROOT=\"\$(xcrun --show-sdk-path)\"" >> ~/.bash_profile # zsh的自行搞定
$ sudo DevToolsSecurity -enable # 将系统置于开发模式
```
[https://zhile.io/2018/09/26/macOS-10.14-install-sdk-headers.html](https://zhile.io/2018/09/26/macOS-10.14-install-sdk-headers.html)

