# Awesome-DL-tricks: hx的玄学炼丹小技巧

### Part1: 关于一些参数的设置
1.为什么RNN输入默认不是batch first=True？这是为了便于并行计算
why: 因为batch first意味着模型的输入（一个Tensor）在内存中存储时，先存储第一个sequence，再存储第二个... 而如果是seq_len first，模型的输入在内存中，先存储所有序列的第一个单元，然后是第二个单元...seq_len first意味着不同序列中同一个时刻对应的输入单元在内存中是毗邻的，这样才能做到真正的batch计算。两种区别如下图所示：
![image](https://user-images.githubusercontent.com/57054352/134612500-d8e90e51-eb01-42a2-b847-533d5d2da9b1.png)


