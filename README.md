# gomediainfo

利用mediainfo cli来分析视频音频信息
使用mediainfo获取视频音频的xml格式文本，然后解析成json

## mediainfo cil

在windows下的安装
版本 19.09
下载地址 https://mediaarea.net/download/binary/mediainfo/19.09/MediaInfo_CLI_19.09_Windows_x64.zip
安装方法 解压后指定文件夹下，设置好相应的环境变量。

## 例子

```go
package main

import (
	"encoding/json"
	"fmt"
	"github.com/gaoluhua99/gomediainfo"
)

func main() {
	mediainfo, err := mediainfo.GetMediaInfo("test.mp4")
	if err!=nil{
		fmt.Println("getmediainfo is err :",err)
	}
	info, err := json.Marshal(mediainfo)
	if err!=nil{
		fmt.Println("make json is failed . err:",err)
	} else {
		fmt.Println(string(info))
	}
}
```

