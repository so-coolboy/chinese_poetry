# chinese_poetry
- 基于Tensorflow2实现。
- 可以直接在colab中运行，不需要配置本地环境，这个notebook中训练了一会我就停掉了，没有训练完。
- 模型训练了写5言诗。
- 参考自：https://github.com/youyuge34/Poems_generator_Keras
# 原理
模型原理就是使用LSTM做多分类，这里设置输入x的长度为6，y的长度为1，比如对于诗句“床前明月光，疑是地上霜”，第一对x和y分别是“床前明月光，”和“疑”。对于第二对则是“前明月光，疑”和“是”。以此类推。
# 数据格式
数据在poetry.txt中，前几行的格式我也在notebook中打印了。
# 训练
我没有完全训练，只跑了1800epoch就停掉了，如果是普通版本的colab，跑个1万轮应该没问题。
# 预测
原始的代码一共提供了4个进行predict 的API:
- predict_first:给定一个汉字，输出一首五言绝句
- predict_random:随机从全部的训练诗作当中抽出一首诗的首句，然后生成一首诗
- predict_gen:给定五个汉字作为首句，生成一首五言绝句
- predict_hide:给定四个汉字，输出以这个四个汉字开头的藏头诗
