# 大理大学网络安全协会 2024-2025学期 第一次作业

## [SWPUCTF 2021 新生赛]gift_F12

进入网址后告诉我们要等到一定的时间才会给flag，显然我们是等不到的，看到题目给了提示“F12”，所以直接在这个界面按F12

然后通过寻找功能找到flag就藏在某个角落

![](https://github.com/LaoAPi/DLU-CTFCLUB-HOMEWORK1/blob/master/4b1f71361ca30103394e4665e7ae62c6.png)

根据平台要求以NSSCTF{}形式发送flag，也就是NSSCTF{We1c0me_t0_WLLMCTF_Th1s_1s_th3_G1ft}

## [第五空间 2021]签到题

![](https://github.com/LaoAPi/DLU-CTFCLUB-HOMEWORK1/blob/master/a1d390ec85cd1dc3ef5ad3f8d14f8af0.png)
观察到题干有flag，直接以NSSCTF{}形式提交

## [SWPUCTF 2021 新生赛]re1

用ida打开附件，通过学习了解到按F5查看伪代码，发现如下程序

![](https://github.com/LaoAPi/DLU-CTFCLUB-HOMEWORK1/blob/master/46303cebbed262bfea2d6cdf4382e1c1.png)

用人话翻译一下，就是：给定了一组字符串str2，输入str1，str1中的某两个字符会被转换成另外两个字符，如果输入的str1和str2的结果非0，即strcmp（str1,str2）!=0，结果为真，便输出you are wrong，否则便是strcmp（str1,str2）==0，执行else语句，输出you are right。所以我们只需要将替换和被替换的字符识别出来，便是str1的内容，然后只要str1和str2相等，就是真正的flag。通过学习，将光标放在101，51，97，52旁并按R，发现str1把e变成了3，把a变成了4。

![](https://github.com/LaoAPi/DLU-CTFCLUB-HOMEWORK1/blob/master/65b3245be89cb125643523f479a8afc2.png)

那么str1就是“easy_reverse”,于是flag就是NSSCTF{easy_reverse}

## [鹤城杯 2021]easy_crypto

下载附件发现是一段中国共产主义核心价值观的文字，没见过，去搜索引擎搜索关键词“核心价值观”“加密”

![](https://github.com/LaoAPi/DLU-CTFCLUB-HOMEWORK1/blob/master/bb33dadf101862ec0b8b2a38c07f346b.png)

![](https://github.com/LaoAPi/DLU-CTFCLUB-HOMEWORK1/blob/master/a7411f5d3585970e114bfefad2055de0.png)

![](https://github.com/LaoAPi/DLU-CTFCLUB-HOMEWORK1/blob/master/9e3a86c4106d685e07bb8deeebcd0a10.png)

所以flag是NSSCTF{IlUqU9O5guX6YiITsRNPiQmbhNRjGuTP}

## [SWPUCTF 2021 新生赛]nc签到

先下载附件，用记事本打开，如图所示

![](https://github.com/LaoAPi/DLU-CTFCLUB-HOMEWORK1/blob/master/1596c76a973b67779351649956929da4.png)

可以看到blacklist里有'cat','ls',' ','cd','echo','<','${IFS}'等词汇，这些词都被列入黑名单禁用了，通过学习相关知识了解到，关键词可以用“\”隔开跳过识别，空格可以用“$IFS$”替代。

接下来用nc链接。之前已经在window上下载好nc了所以直接在终端里用，一开始忘记把“:”换成空格了所以没法连接，正确连接后是这样的

![](https://github.com/LaoAPi/DLU-CTFCLUB-HOMEWORK1/blob/master/a4f2b39a2504a54b0c426f7e6b1f5b56.png)

用l\s查看列表，发现有flag

于是输入c\a\t$IFS$5flag，得到flag

![](https://github.com/LaoAPi/DLU-CTFCLUB-HOMEWORK1/blob/master/a81ab67681c301c636d28a63c66af29e.png)