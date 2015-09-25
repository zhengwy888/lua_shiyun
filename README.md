# lua_shiyun
一个帮助查找近体诗的韵律韵脚的工具，使用Lua实现。
数据源头来自[《平水韵》](https://zh.wikisource.org/zh-hans/%E5%B9%B3%E6%B0%B4%E9%9F%BB)

###主要功能
查询字符韵脚，平仄
查询近体诗（五绝七绝五律七律）的韵律

###使用方法
```lua
local YunjiaoLoader = require 'yunjiao.YunjiaoLoader'
local yunjiao = YunjiaoLoader.create()
print(yunjiao:getYunjiao('杉'))
-- table：返还所有跟‘杉’处在同一个韵部里的字
--[[
{
  1 : "咸"
  2 : "咸"
  3 : "函"
  4 : "缄"
  5 : "岩"
  6 : "谗"
  7 : "衔"
  8 : "岩"
  9 : "帆"  
  10 : "衫"
  11 : "杉"
  12 : "监"
  13 : "凡"         
  14 : "馋"
  15 : "巉"
  16 : "镵"
  17 : "芟"         
  18 : "喃"
  19 : "嵌"
  20 : "掺"
  21 : "瑊"
  22 : "劖"
  23 : "碞"
  24 : "諴"
  25 : "儳"
  26 : "欃"
  27 : "搀"
  28 : "毚"
  29 : "颿"
  30 : "缄"
  31 : "麙"
  32 : "𧮪"
  33 : "髟"
  34 : "縿"
  35 : "獑"
  36 : "锨"
  37 : "严"
}
]]--
print(yunjiao:getPingze('低'))
-- 1 (1平，2仄，3平韵脚，9分隔号）
print(yunjiao:getNextPingzes('两个黄鹂鸣翠'))
-- {2}（跟上一个函数返还相同， 以及：0-任何平仄都可以）
print(yunjiao:belongsTo({1},'低'))
-- true（检查平仄是否符合）
```

###有待实现
同一韵脚的查询

###License
MIT License

