﻿2024/11/21
设计思路：
1.实现漏号、热号、温号
2.扫描100期号码，从每组号码中，找出漏号、间隔期数
3.10期内，出现率高于3期的视为热码.
4.等于3期的为温码、低于3期的为冷码

2024/12/10
设计思路：
1.原则：还是要用程序算号，不要自己分析号。
2.实现：
2.1.首先取100期或更多期的号码。
2.2.取100期内每个位置号码的区间，
        如：1号红号是6，100期内，最小值是1、最大值是16，并求得平均值。
            并且每个号中间间隔多少期出。哪个是出的最多的号，哪个是出的最少的号。
2.3.根据每期位置区间，得出间隔规律。
        如：找出每个号码隔多少期要出一次，每次出是哪个号带出来的。
            1号球上期开奖是[6]，倒回100期看，6号球最间隔多少期出一次，
            如：
            （1）*每次出6分别是什么号带出来的,共出现几次类似的情况：[2][3次]、[7][1次]、[10][1次]、[8][2次]
            （2）*出6后分别又出的什么号，共出现几次类似的情况：[2][1次]、[3][3次]、[9][1次]、[11][1次]
            （3）数据格式如下：
                 例如：本期开出第一个号是[1]，倒退100期分析结果
                 1.上期[4]本期[1]下期[3]中间间隔期数[?]最后遗漏期数[?]
                 2.上期[7]本期[1]下期[9]中间间隔期数[?]最后遗漏期数[?]
            （2）下期准备号码是什么号：
                 5.1.首先分析下期准备是往上走还是往下走
                     往下走[2][3次]
                     往上走[7][1次]、[10][1次]、[8][2次]