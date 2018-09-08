## JIANPU.js

利用[Web Audio API](https://developer.mozilla.org/zh-CN/docs/Web/API/Web_Audio_API)将数字简谱转为钢琴曲

[DEMO](http://journey-ad.github.io/jianpu/)

### 关于数字简谱

数字简谱是简谱记谱法的一种更简化形式，相对于简谱仅保留了音调，而不记录旋律信息

规定如下：

- 音符以数字1、2、3、4、5、6、7表示
- 调号为C大调
- 若为半音，就在音符前方加一个`#`号
- 若高一个八度，音符就用中括号`[]`包裹起来，再高一个八度，就用双重中括号`[[]]`包裹起来
- 若低一个八度，音符就用小括号`()`包裹起来，再高一个八度，就用双重小括号`(())`包裹起来
- 空格、换行和`-`号表示暂停一个音的时长，出现多个将暂停多次

由于数字简谱不记录旋律信息，因此不适合记录节奏复杂多变的乐曲，可善加使用暂停符来控制节奏

### 使用

```javascript
jianpu('1234567[1]')
jianpu('1155665 4433221 5544332 5544332 1155665 4433221')
```

### 谱面示例

音调测试
```
((1))((#1))((2))((#2))((3))((4))((#4))((5))((#5))((6))((#6))((7))
(1)(#1)(2)(#2)(3)(4)(#4)(5)(#5)(6)(#6)(7)
1#12#234#45#56#67
[1][#1][2][#2][3][4][#4][5][#5][6][#6][7]
[[1]][[#1]][[2]][[#2]][[3]][[4]][[#4]][[5]][[#5]][[6]][[#6]][[7]]
```

小星星
```
1155665 4433221 5544332 5544332 1155665 4433221
```

两只老虎
```
1231 1231 345 345 565431 565431 2(5)1 2(5)1
```

上学歌
```
12315 66[1]65 66[1]563 653531231 12315 66[1]65 66[1]563 653531231
```

粉刷将
```5353531 24325 5353531 24321 2244325 24325 5353531 24321
```

数鸭子
```
[1][1]553653 21231- 3-1-331 33565 6665444 23212 3-1-3-1 33566 [1]-5563 21235 [1]-5563 21231
```

哆啦A梦
```
(6)22#47#46 676#45#43
(7)335[#1][#1]7655#4(7)#123
(6)22#47#46 676#45#43
(7)335[#1][#1]7655#4(7)#132
7765676 3#4#536 763#4#536
7653[#1]76765 67#432
```

白金ディスコ
```
35653 23211- (6)12332122--
35653 23211- (6)12353211--
1(6)1-1121 1(6)1-1131-(5) (6)(5)(6)1 23211
1(6)1-1112 1(6)1-11131-(5) (6)123211--
11(6)1111 111121(6)(5)(6)1 123
11(6)1111 111121(6) 122-122 12123-5--

56235 (6)123(6)12 (6)123(6)11 (5)-132-123--
(6)123(6)12 (6)123521 (5)132 11--
(5)(6)-(5)(6) (5)(6)1232-
12-12 1231(6)11-
(5)(6)-(5)(6) (5)(6)1235321
(6)1-(5)(6) 1121211
```

致爱丽丝
```
[3][#2][3][#2][3]7[2][1]6 1367 3#57[1]3-
[3][#2][3][#2][3]7[2][1]6 1367 3[1]7
[3][#2][3][#2][3]7[2][1]6 1367 3#57[1]3-
[3][#2][3][#2][3]7[2][1]6 1367 3[1]7
67[1][2][3]5[4][3][2]4[3][2][1]3[2][1]7
[2][3][2][3][#2][3][#2][3][2][3][#2][3]7[2][1]6
13673#57[1]3
[3][#2][3][#2][3]7][2][1]6 1367 2[1]76
```

喀秋莎
```
(6)-(7)-1 (6)-1-(7)(6)(7)-(3) (7)-12-(7) 2221(7)(6)-
3-6-6 5-654-323-(6) 422-311 (7)(3)(3)1(7)(6)-
3-6-6 5-654-323-(6) 422-311 (7)(3)(3)1(7)(6)--
(6)-(7)-1 (6)-1-(7)(6)(7)-(3) (7)-12-(7) 2221(7)(6)-
3-6-6 5-654-323-(6) 422-311 (7)(3)(3)1(7)(6)-
3-6-6 5-654-323-(6) 422-311 (7)(3)(3)1(7)(6)
```

打靶归来
```
2525312 25251(7)(5)(6)1(5)
1(7)(6)(5)1561 56532(5)(6)(5)
35635 65312 22355535
```

别看我只是一只羊
```
[1][1][1][1]753 5---
[1][1][1][1]753 5[2]--
[3][3][3][3][2][1]6 4[2]--
7777653 35---
[1][1][1][1]753 5---
[1][1][1][1]753 5[2]--
[3][3][3][3][2][1]6 4[2]--
7777[1][2] [1]--
```

START_DASH
```
5552567656
#4#4#4#4#4#4 #4#45#4
552 567 6565 12
5552 567 656
#4#4#4#4 #4#45#4
5552 567 656
3[1]76 5#45
33#45 #456 223#4 567
67[1] 7655
67[1] 76567 7
----
37777 7765#4 26666 66567
37777 7765#4 223#45 6[1]7
37777 7765#4 26666 66[1]77
[3][#4][5]3#45[#4][5][6]#456
[#4][5][6]656 23#45567
[1]33 36 5#4#45
----
(7)3#465 3#45 #456
----
26666 66543 15555 55456
26666 66543 11234567
```

旅の途中
```
#1#24#44 #1#23#43
333#2(7)(#5)-
#1#24#44 #1#23#43
333#2(7)3-

#5#5#5#5#43#2#2#1#2
#43#2#1#2(7)(#5)-
3#4#5#5#5#5#43#2#2#1#2
3#43#2#136#5-

1#1#2#1 1#1#2#1
#23#5#4 #13#5#4
#56[#1]7 3#46#5
3#4#5#46#5#2-

#1#1#1#23#4
#1#1#1#23#4#5#46#5-

2#24#2 2#24#2
4#4#6#5 #2#4#6#5
#67[#2][#1] 4#57#6
#4#5#6#57#64-

#2#4#6#57#6#2
```

远い空へ
```
(7)(6)(7) #4#1 
2#1(6)(7) #123676 
(7)- #46#1 (6)(7)-
#4#1(7) #4#1 
2#1(6)(7) #123676 
(7)- #46#1 (6)(7)-
(6)#1(7) #467 676 3#46#12 
23#4 #43#43 23#456#67[#1]-
7-676 3#46[#1][2][3][#4] 
[#4][3][2][#1] 6[#1][2] [#1]7#67[#1] [#4][3][2][#1]6#47
```

成都
```
---(5)1 23533 (5)1 21(6)(5)
(5)1 23635 32 1252
35 5356[1]6 32 1233
35 533211 (5) 21311---

(5)1 23533 (5)1 21(6)(5)
(5)1 23655 21 1252
35 535[1]66 32 11233
35-- 32(6)1- 1-21--

--35 553566311 1253
35 53566311 (5)231
(5)(6)1 12233 356 56523
12 12(6)232 12222365
```

断桥残雪
```
3 33 212223(6) 23(5) 1(7)(7)(5)3---
3 33 212223(6) 23(5) 1(7)(7)(3)(6)---
3 33 212223(6) 23(5) 1(7)(7)(5)3---
3 66 21223(6) 235 5321(6)---
[1]33[1]77[1] 52653 1(6)(6)123 777663
[1]33[1]776 652653 1(6)(6)123
3332(7)(7)(7)(3)(6)
```