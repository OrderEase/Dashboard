#STMT-Assignment6
题目：分析 Chap.4.2.6 (Lec.15, Slide 39) 判定表图例的第6列和第23列

1.列出输入、输出及中间结点的清单及标志

![](/Users/xumuxin/Documents/屏幕快照 2018-05-10 下午11.00.20.jpg)

![](/Users/xumuxin/Documents/屏幕快照 2018-05-10 下午11.00.31.jpg)

2.画出因果图

![](/Users/xumuxin/Documents/屏幕快照 2018-05-10 下午11.02.01.jpg)

3.因果图转判定表
![](/Users/xumuxin/Documents/屏幕快照 2018-05-10 下午11.02.19.jpg)

回答：

(1) 输入条件的语义陈述;

列数 | 		输入条件的语义陈述
------- | -------
第6列 | 在售货机有零可找的情况下，操作者投入1元硬币，按下橙汁按钮
第23列 | 在售货机没有零钱的情况下，操作者投入1元硬币，按下啤酒按钮

(2) 输出结果的语义陈述;

列数 | 		输出结果的语义陈述
------- | -------
第6列 | 售货机退还5角硬币并送出橙汁饮料
第23列 | 售货机的【零钱找完】灯亮着并且退还1元硬币

(3) 用命题逻辑形式描述实现上述输入-输出过程所应用的判定规则
     ，并写出获得输出结果的推理演算过程。
     
列数 | 		输出结果的语义陈述
------- | -------
第6列 | ![](/Users/xumuxin/Library/Containers/com.tencent.xinWeChat/Data/Library/Application Support/com.tencent.xinWeChat/2.0b4.0.9/49de6299a96f5d0ca6f79c1c1579534e/Message/MessageTemp/9e20f478899dc29eb19741386f9343c8/Image/601525965911_.pic.jpg)
第23列 | ![](/Users/xumuxin/Library/Containers/com.tencent.xinWeChat/Data/Library/Application Support/com.tencent.xinWeChat/2.0b4.0.9/49de6299a96f5d0ca6f79c1c1579534e/Message/MessageTemp/9e20f478899dc29eb19741386f9343c8/Image/611525965911_.pic.jpg)