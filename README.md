# Clean-Torrent-GUI

顾名思义，清洗种子，多数情况下，内站并不需要，但是外站很多都需要重新制作种子，一来二去，浪费时间。该软件配合脚本实用更佳。

不同站点有不同要求，下面贴一个使用模板：

```json
{
	"HDT": {
		"announce": "http://hdts-announce.ru/announce.php",
		"source": "blank",
		"creation date": 600,
		"comment": "blank"
	},
	
	"PTP": {
		"announce": "",
		"source": "delete",
		"creation date": 600,
		"comment": "delete"
	},

	"MTV": {
		"announce": "",
		"source": "delete",
		"creation date": 600,
                "rename": "yes",
		"comment": "delete"
	},

	"SC": {
		"announce": "",
		"source": "delete",
		"creation date": 600,
		"comment": "delete"
	},

	"BTN": {
		"announce": "",
		"source": "delete",
		"creation date": 600,
		"comment": "delete"
	},

	"KG": {
		"announce": "",
		"source": "delete",
		"creation date": 600,
		"comment": "delete"
	},

	"PURIST": {}
}
```

**注意：模板使用json格式，如果不是很了解，谷歌之。其中"PURIST": {}请不用理会，会默认生成一个announce为空的种子，可以用于发内站，实在不需要可以删掉。**

接下来说明上述字段的含义：

+ announce: 不用多说了，就是tracker要填的东西

+ source: 可填写任意字符串，如: "PTP"，或者设置为"blank"表示为空，或者"delete"，直接删除该字段

+ comment: 可填写任意字符串，如: "PTP"，或者设置为"blank"表示为空，或者"delete"，直接删除该字段

+ creation date: 每个种子都有制作时间，我们不希望跟源种子制作时间一样，所以在此基础上加指定秒数，600表示10分钟，然后会有一个random时间区分开

+ rename: 我们发现皮的种子不按P2P命名法则，而MTV会根据种子上传名称进行auto-fill。有必要按照种子内容重新命名~

### 使用步骤

1. 下载exe文件和config.example.json文件并且重命名为config.json文件，记事本打开修改模板。需要符合json规范以及上述字段进行填写。

2. 运行exe程序，会自动根据模板生成存放种子的文件夹，界面为一个表格。两种洗白方案：

+ 如果不进行行的选取，拖拽种子进入表格，会针对所有模板进行洗白。
+ 如果选择了特定行再进行拖拽，则会对指定行的模板进行洗白。

使用：洗白后的文件目录存放路径则会在表格中进行显示，双击则打开种子所在目录，拖拽到上传页面指定上传按钮处松开即上传种子成功。

**说明：可以一次性拖入多个种子，但是界面会保留最后一个完成的路径，双击打开会显示拖入的种子都已经完成。**

### 放个界面图

![123.png](https://www.z4a.net/images/2022/04/19/123.png)

### 更新20220423 V2.0
因为内站转外站很多时候mediainfo就变成自定义的短的了，然后需要找到视频进行mediainfo的获取；或者需要原图、缩略图。所以写了imgbox和ptpimg两个图床。
需要配置imghost.json，如果你使用了代理，替换成自己的端口，如果想使用ptpimg，填上自己的api-key。

### 总结
---

折腾不易，且行且珍惜。
