# Clean-Torrent-GUI
洗种工具-tk界面版

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

**注意：模板使用json格式，如果不是很了解，谷歌之。**

接下来说明上述字段的含义：

+ announce: 不用多说了，就是tracker要填的东西

+ source: 可填写任意字符串，如: "PTP"，或者空""，或者"delete"，直接删除该字段

+ comment: 可填写任意字符串，如: "PTP"，或者空""，或者"delete"，直接删除该字段

+ creation date: 每个种子都有制作时间，我们不希望跟源种子制作时间一样，所以在此基础上加指定秒数，600表示10分钟，然后会有一个random时间区分开

+ rename: 我们发现皮的种子不按P2P命名法则，而MTV会根据种子上传名称进行auto-fill。有必要按照种子内容重新命名~

### 使用步骤

1. 下载exe文件和config.example.json文件并且重命名为config.json文件，记事本打开修改模板。主要符合json规范以及上述字段进行填写。

2. 运行exe程序，会自动根据模板生成存放种子的文件夹，界面为一个表格。如果不进行行的选取，拖拽种子进入表格，会针对所有模板进行洗白。如果选择了特定行再进行拖拽，则会对指定行的模板进行洗白。洗白后的文件目录存放路径则会在表格中进行显示，双击则打开种子所在目录，拖拽到上传页面指定上传按钮处松开即上传种子成功。

### 总结
---

折腾不易，且行且珍惜。
