a record for my work<br>
===========================================
20190523:<br>
-------------------------------------------
今天的主要工作是用python为毕设做了一个GUI，学会了设置基本的控件，包括button，label，entry；<br>
还在网上搬运了一个实现秒表计时的功能，实现对训练时间的计时；<br>
一个button触发训练和计时两个功能，训练时间较久会使GUI页面卡住计时功能无法正常运行,解决方法是对训练开了一个多线程模式<br>

20190524:<br>
-------------------------------------------
完善昨天的计时功能，使训练识别程序开始后自动计时，程序停止后停止计时
python完成单链表节点类的创建/删除/插入/遍历
采集室外不同距离人脸 1-9m，间隔1m采集一次，共九组数据

20190526-20190601：<br>
-------------------------------------------
参加陕西省大学生羽毛球比赛，获得男子甲组团体第三名、男子甲组单打第三名

20190602-20190611：<br>
-------------------------------------------
修改毕设论文

20190612：<br>
-------------------------------------------
MATLAB中
*double()指将数据类型转换成浮点型<br>
*im2double()当输入数据为uint8时，函数输出为[0-1]的double型数据，相当于uint8数据除以255<br>
*mat2gray()也是输出数据为[0-1]的double型数据，只不过是根据输入矩阵的数据归一化<br>
*im2uint8()只对输入数据值为区间[0,1]内进行[0,255]映射，对于小于0的数据置0，大于1的数据置255<br>

20190613-20190614：<br>
-------------------------------------------
标注 多目标车辆数据 600帧 <br>
阅读文献：<br>
《一种采用IHS空间表征偏振遥感图像的方法》<br>
《图像融合在偏振关联成像中的应用》<br>
《成像偏振探测的若干关键技术研究》<br>
《Pseudo-Color Image Fusion Based on Intensity-Hue-Saturation Color Space》<br>
《基于偏振图像融合的长波红外人脸图像增强技术》<br>
对文献《成像偏振探测的若干关键技术研究》中提到的使用偏振度、偏振角、强度图像去除冗余后映射到RGB通道进行伪彩色融合的方法用matlab复现，由于偏振角在脸部区域产生跳变的原因，融合出来的人脸效果并不理想<br>
对文献《基于偏振图像融合的长波红外人脸图像增强技术》中仅仅使用强度和偏振度两幅图像进行融合增强，取得了不错的效果。下一步准备复现该文章。

20190615：<br>
-------------------------------------------
标注数据100帧

20190616：<br>
-------------------------------------------
看yolov1文章：You Only Look Once: Unified, Real-Time Object Detection <br>
yolov1实现端到端的目标检测功能 设计输出为7*7*30 因为设想是将图片分割成7*7个格子，每个格子负责预测两个同类目标，每个预测框有5个参数:(p,x,y,w,h),p代表有无目标，x,y为目标中心点所处位置，要对格子归一化在[0-1]之内；w,h表示目标长宽对格子归一化的数值，可以大于1。最后接20个类别参数，表示将该目标分为哪个类别，用1/0表示。

20190617：<br>
-------------------------------------------
玩了一天的王者荣耀
