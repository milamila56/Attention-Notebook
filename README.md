# Attention-Notebook
AM机制的各类形态：soft AM，hard AM，global AM，local AM，self AM，bi-DAF

1. 首先Yoshua Benjio团队，Baunadau 2015是将attention引入NLP的鼻祖，基于CHO【Learning phrase representations using RNN encoder-decoder for statistical machine translation. In Proceedings of the Empiricial Methods in Natural Language Processing (EMNLP 2014) 】的端到端RNN模型加入Attention。也叫global attention、soft attention、动态AM，这里global是指给全部输入都分配一个权值，动态强调的则是，每个单词都用网络跑一个权值e_ij，相应地静态就是指对每个句子只算一个权值）

2. 之后把窗口变一变得到local AM，【斯坦福大学Manning研究组 2015 ACL Effective Approaches to Attention-based Neural Machine Translation】

3. 如果不计算每个单词，只计算句子的权值，就叫静态AM。【google Teaching Machines to Read and Comprehend中提出的静态、动态AM】
【前三个基本可以说是NLP第一梯队，领域的风向标了，都是2015年提出的】

4. Self attention（或者叫intra attention），自己和自己建立联系（只有一组序列即可，不涉及输入和输出两组序列），正是因为是自己和自己建立联系，不涉及RNN的前后序列关系，所以才有了后面google 的attention is all you need,也就是反映了attention的本质就是建立一个索引，不需要很长的RNN序列结构，缓解了这种序列计算导致的运算速度下降。（下面两个文章不知道谁先谁后）
	a. google的，就是把attention单拎出来去做任务，包括语言模型、情感分析和Stanford Natural Language Inference (SNLI) 等【2016 EMNLP A Decomposable Attention Model for Natural Language Inference】
	b. 爱丁堡大学，提出了intra-attention【之前的attention定义为inter-attention】，同时对LSTM进行改进，加了好多memory单元。【2016 EMNLP 做 Stanford Natural Language Inference (SNLI) Long Short-Term Memory-Networks for Machine Reading】

5. Google的略有噱头的Attention is all you need。
6. 双向的attention用于机器阅读理解（斯坦福的SQuAD）2017 ICLR BI-DIRECTIONAL ATTENTION FLOW FOR MACHINE COMPREHENSION


AM机制的应用范围
1. Soft AM用到句法分析【2015 NIPS Grammar as a foreign language】
2. Soft AM用到生成式文本摘要【】
3. 语言推断NLI
4. 阅读理解
5. 移情会话系统（Fung et al., 2016；Alam et al., 2017）？？什么东东？
