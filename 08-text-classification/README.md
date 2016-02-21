# 实例分析：文本分类


## 准备知识

* 文本分类
* Python
* Hadoop Streaming










现有的分类技术都已经非常成熟,SVM、KNN、Decision Tree、AN、NB 在 不同的应用中都展示出较好的效果,由于支持向量机(Support Vector Machine) 在解决小样本、非线性及高维模式识别中表现出许多特有的优势,并能够推广应 用到函数拟合等其他机器学习问题中,因此本文选取支持向量机算法进行文本分
类。支持向量机方法是建立在统计学习理论的 VC 维理论和结构风险最小原理基 础上的,根据有限的样本信息在模型的复杂性(即对特定训练样本的学习精度, Accuracy)和学习能力(即无错误地识别任意样本的能力)之间寻求最佳折衷, 以期获得最好的推广能力(或称泛化能力)。

模型 model 中包含的参数会返回两个结果:keys 和 score,其中 keys 为每 一个 word 对应的行数,而 score 是该 word 属于类别 1 的隶属度,分值越大,代 表属于该类的置信度越大。对测试集数据的每一行中出现的 word,求这篇文章中所有语料库单词属于类别 1 的隶属度之和,若该和大于 0,则属于类别 1,若 该和小于 0,则属于类别 0。据此可以编写其 mapper 程序,如下所示:



	#! /usr/bin/env python 
	# -*- coding: utf-8 -*-








根据以上信息而已计算准确率(accuracy)、精确率(precision)、召回率 (recall)和 F1 值 4 个评价分类性能的指标。


	def main():
		beta_squared = math.pow(1., 2.)
				


	0    5    285
（感谢中央财经大学成慧敏提供素材和案例。）