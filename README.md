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
MATLAB中<br>
* double()指将数据类型转换成浮点型<br>
* im2double()当输入数据为uint8时，函数输出为[0-1]的double型数据，相当于uint8数据除以255<br>
* mat2gray()也是输出数据为[0-1]的double型数据，只不过是根据输入矩阵的数据归一化<br>
* im2uint8()只对输入数据值为区间[0,1]内进行[0,255]映射，对于小于0的数据置0，大于1的数据置255<br>

20190613-20190614：<br>
-------------------------------------------
标注多目标车辆数据600帧 <br>
阅读文献：<br>
* 《一种采用IHS空间表征偏振遥感图像的方法》<br>
* 《图像融合在偏振关联成像中的应用》<br>
* 《成像偏振探测的若干关键技术研究》<br>
* 《Pseudo-Color Image Fusion Based on Intensity-Hue-Saturation Color Space》<br>
* 《基于偏振图像融合的长波红外人脸图像增强技术》<br>
对文献《成像偏振探测的若干关键技术研究》中提到的使用偏振度、偏振角、强度图像去除冗余后映射到RGB通道进行伪彩色融合的方法用matlab复现，由于偏振角在脸部区域产生跳变的原因，融合出来的人脸效果并不理想<br>
对文献《基于偏振图像融合的长波红外人脸图像增强技术》中仅仅使用强度和偏振度两幅图像进行融合增强，取得了不错的效果。下一步准备复现该文章。

20190615：<br>
-------------------------------------------
标注多目标车辆数据100帧

20190616：<br>
-------------------------------------------
    看yolov1文章：You Only Look Once: Unified, Real-Time Object Detection  
    yolov1实现端到端的目标检测功能 设计输出为7*7*30 因为设想是将图片分割成7*7个格子
    每个格子负责预测两个同类目标，每个预测框有5个参数:(p,x,y,w,h)
    p代表有无目标,用1/0表示；x,y为目标中心点所处位置，要对格子归一化在[0-1]之内；w,h表示目标长宽对格子归一化的数值，可以大于1；
    最后接20个类别参数，表示将该目标分为哪个类别，用1/0表示。

20190617：<br>
-------------------------------------------
玩了一天的王者荣耀

20190618: <br>
-------------------------------------------
    感觉这个logbook可以当作diary来用了23333333
    上午学会了一些readme的使用格式调整，就设置大小标题、换行、小圆点标题三种操作
    快要跑通yolov1的pytorch代码了，不过里边的YOLO_Loss.py还没仔细看

20190619：<br>
-------------------------------------------
    github上面下了两个使用python爬取微信好友信息/自动回复/定时发消息等功能的项目，玩了一下
    
20190620：<br>
-------------------------------------------
    上午申请临时住宿/保单/修改毕设问题
    下午唱歌 晚上看毕业晚会
    
20190621-0622：<br>
-------------------------------------------
    emmm，临近毕业，和大家一起玩耍

20190623：<br>
-------------------------------------------
    按照pytorch教程实现线性回归，逻辑回归
    在mnist手写字体数据集上完成
    前馈神经网络：
    示例中仅给出一层500神经元的隐藏层，我对网络结构进行修改增加一层隐藏层或者是更改单隐藏层的神经元数目，对测试准确率影响在1%内（97%）
    卷积神经网络：示例中两层卷积层将28*28调整为7*7*32，后面跟softmax层分类，准确率98.83

20190624-0625：<br>
-------------------------------------------
    yolov3相比较于yolov1更复杂、更强大、更完整
    v1将图片分成7*7个格子，每个格子负责预测用两个boundingbox来预测同一类物体，网络最后输出的featuremap为7*7*(2*5+20)
    v1的缺陷在于：
    1.检测物体种类较少，只有20种
    2.由于尺度固定为7*7，当一个boundingbox里面有两类以上目标时，v1必然存在漏检情况
    v3作出的改进
    1.使用残差结构，新构造出的backbone---darknet53 在v3上面性能媲美resnet152，速度远胜
    2.使用batch normalization作为正则化、加速收敛的方法(v2开始使用)
    3.采用"leaky ReLU"作为激活函数
    4.为了能够检测出同一个bounding的不同类目标，v3使用anchor box策略(v2开始使用)，每一个anchor box负责预测一类目标；
    同时为了能够检测出不同大小的目标,v3输出3个不同尺度的featuremap,分别为13*13*(anchorbox_num=3)*(5+80(coco数据集含有80类目标))
    26*26*255，52*52*255；
    
20190626：<br>
-------------------------------------------
    完成视频转图片，图片使用yolov3检测，检测后的图片转视频功能
    下一步计划批量完成
    原视频->图片->yolov3检测后图片->保存成视频
    今天毕业咯
    
20190627: <br>
-------------------------------------------
    将video2pic(),pic2video(),detectimages()封装在一个.py文件中，实现多个视频输进来，直接输出多个检测视频的功能
    在视频分割成图片的时候，最后一帧总是格式错误，解决方法就是分割每个视频完毕后，删除照片文件夹最后一帧
    plt.savefig()的保存路径必须为已经存在的文件夹中....写到这好像所有的保存路径都应该要求次上一级的文件夹存在....调这个bug调了快一上午。爆炸
    用plt.subplots_adjust(top=1, bottom=0, right=1, left=0, hspace=0, wspace=0)解决使用plt画图后，周围一圈出现空白的问题
    
    
    
    
