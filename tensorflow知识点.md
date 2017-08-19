## TensorFlow中常用函数

**tensorflow中维护的集合列表**

|               集合名称                |               集合内容               |           使用场景           |
| ------------------------------------- | ------------------------------------ | ---------------------------- |
| tf.GraphKeys.VARRIABLES               | 所有变量                             | 持久化TensorFlow模型         |
| tf.GraphKeys.TRAINABLE_VARIABLES      | 可学习的变量(一般指神经网络中的参数) | 模型训练、生成模型可视化内容 |
| tf.GraphKeys.SUMMARIES                | 日志生成相关的张量                   | TensorFlow计算可视化         |
| tf.GraphKeys.QUEUE_RUNNERS            | 处理输入的QueueRunner                | 输入处理                     |
| tf.GraphKeys.MOVING_AVERAGE_VARIABLES | 所有计算滑动平均值的变量             | 计算变量的滑动平均值         |


**tensorflow中随机数生成函数**

|      函数名称       |                                  随机数分布                                   |               主要参数                |
| ------------------- | ----------------------------------------------------------------------------- | ------------------------------------- |
| tf.random_normal    | 正态分布                                                                      | 平均值、标准差、取值类型              |
| tf.truncated_normal | 正态分布，但如果随机出来的值偏离平均值超过2个标准差，那么这个数将会被重新随机 | 平均值、标准差、取值类型              |
| tf.random_uniform   | 平均分布                                                                      | 最小、最大取值、取值类型              |
| tf.random_gamma     | Gamma分布                                                                     | 形状参数alpha、尺度参数beta、取值类型 |

**tensorflow中常数生成函数**

|  函数名称   |             功能             |                    样例                    |
| ----------- | ---------------------------- | ------------------------------------------ |
| tf.zeros    | 产生全0的数组                | tf.zeros([2,3],int32) -> [[0,0,0],[0,0,0]] |
| tf.ones     | 产生全1的数组                | tf.ones([2,3],int32) -> [[1,1,1],[1,1,1]]  |
| tf.fill     | 产生一个全部为给定数字的数组 | tf.fill([2,3],9) -> [[9,9,9],[9,9,9]]      |
| tf.constant | 产生一个给定值的常量         | tf.constant([1,2,3]) -> [1,2,3]            |

**tensorflow中变量初始化函数**

* 初始化函数主要用于
    - tf.get_varialbe
        - 以下两种书写方式结果相同
            - v = tf.get_variable('v', shape = [1], initializer = tf.constant_initializer(1.0))
            - v = tf.Variable(tf.constant(1.0, shape = [1]), name = 'v')

|             初始化函数              |                                                   功能                                                    |           主要参数           |
| ----------------------------------- | --------------------------------------------------------------------------------------------------------- | ---------------------------- |
| tf.constant_initializer             | 将变量初始化为给定常量                                                                                    | 常量的取值                   |
| tf.random_normal_initializer        | 将变量初始化为满足正态分布的随机值                                                                        | 正态分布的均值和标准差       |
| tf.truncated_normal_initializer     | 将变量初始化为满足正态分布的随机值，但如果随机出来的值偏离平均值超过2个标准差，那么这个数将会被臭重新随机 | 正态分布的均值和标准差       |
| tf.random_uniform_initializer       | 将变量初始化为满足平均分布的随机值                                                                        | 最大、最小值                 |
| tf.uniform_unit_scaling_initializer | 将变量初始化为满足平均分布但不影响输出数量级的随机值                                                      | factor产生随机值时乘以的系数 |
| tf.zero_initializer                 | 将变量设置为全0                                                                                           | 变量维度                     |
| tf.ones_initializer                 | 将变量设置为全1                                                                                           | 变量维度                     |
