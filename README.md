# GuBot-PRTS-static
用于PRTS [GuBot](https://prts.wiki/w/User:GuBot) 和 [trapper-script](https://github.com/GuGuMur/trapper-script)编辑用的静态文件

## 小队群内使用方法
<del>每次更新时更新该库后群内@鸽机(可用的那个)并附文字`关卡更新`，鸽机会自动开始更新</del>

每次更新时从小队群里下载文件`prts_stage.zip`，安装要求的库并更新GameData后执行包里的`__init__.py`文件

## 在PRTS的使用方法
启用IPE后在你的`用户:xx/common.js`页加入以下代码：

```javascript
mw.loader.load('/index.php?title=User:GuBot/trapper.js&action=raw&ctype=text/javascript');
```

## 文件介绍

### [unwritetiles.json](/unwritetiles.json)
本文件使用List储存不需要处理的地形

### [unwritetraps.json](/unwritetraps.json)
本文件使用List储存不需要处理的装置

### [tilesformat.json](/tilesformat.json)
本文件使用Json + jinja2模板 规定bot撰写特殊地形时的格式
1. jinja2模板为与wikitext不重复，设定了变量起始和终止符为`{$` 和 `$}`，函数保持与默认一致（即为`{%` `%}`
2. 由于Python对函数参数名的限制，类似`buff_yinyang[same].atk_scale`的Ark参数请将`[`、`]`和`.`均替换为`__`(两个下划线)

### [trapsformat.json](/trapsformat.json)
本文件使用Json规定装置编写的格式
```json
{
    "L-44\"留声机\"": {
        "type": "地图装置",
        "params": [
            { "param": "攻击间隔", "content": "1.5s" },
            { "param": "技能范围标题", "content": "传输协议范围" },
            {
                "param": "备注",
                "content": "技力达到0时变为敌方装置，技力达到100时变为我方装置<br>※设定为敌方单位<br>※治疗对我方隐匿单位无效<!--<br>在本图的突袭模式中，位于{{Popup|内容=坐标格式为(Y,X)，坐标以左下角为原点}}的留声机初始SP为0且为敌方装置。-->"
            }
        ]
    }
}
```
