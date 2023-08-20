# GuBot-PRTS-static
用于PRTS GuBot编辑用的静态文件

## 小队群内使用方法
<del>每次更新时更新该库后群内@鸽机(可用的那个)并附文字`关卡更新`，鸽机会自动开始更新</del>

每次更新时从小队群里下载文件`prts_stage.zip`，安装要求的库并更新GameData后执行包里的`__init__.py`文件

## 文件介绍

### [unwritetiles.json](/unwritetiles.json)
本文件使用List储存不需要处理的特殊地形

### [unwritetraps.json](/unwritetraps.json)
本文件使用List储存不需要处理的特殊地形

### [tilesformat.json](/tilesformat.json)
本文件使用Json + jinja2模板 规定bot撰写特殊地形时的格式
1. jinja2模板为与wikitext不重复，设定了变量起始和终止符为`{$` 和 `$}`，函数保持与默认一致（即为`{%` `%}`
2. 由于Python对函数参数名的限制，类似`buff_yinyang[same].atk_scale`的Ark参数请将`[`、`]`和`.`均替换为`__`(两个下划线)