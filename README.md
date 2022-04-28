# crosswalk-build-tools

built on top of official Ubuntu images with ssh enabled.

```
import("//xwalk/build/android.gni")
is_debug = false
target_os = "android"
ffmpeg_branding = "Chrome"
target_cpu = "x86"
enable_plugins = true
```


```
export http_proxy=http://127.0.0.1:1087  
export https_proxy=http://127.0.0.1:1087

git config --global http.https://github.com.proxy socks5://127.0.0.1:1086
git config --global https.https://github.com.proxy socks5://127.0.0.1:1086

```

后面gclient sync的时候会说不支持http代理什么的，我是在depot_tools/目录下新建了一个http_proxy.boto，然后export NO_AUTH_BOTO_CONFIG=~/depot_tools/http_proxy.boto

```
[BOTO]
proxy = 127.0.0.1
proxy = 1087
```

