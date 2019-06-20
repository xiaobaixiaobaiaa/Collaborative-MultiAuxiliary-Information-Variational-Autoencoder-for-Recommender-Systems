# Collaborative-Multi-Auxiliary-Information-Variational-Autoencoder-for-Recommender-Systems
### 更改声明：
对于前面发布的代码进行了些许整理，重新发布


### 须知：
* 使用citeulike-a和citeulike-t时的代码基本类似，仅在导入数据部分存在不同，故在本说明内不区分两个数据集
* LICENSE：该许可为Xiaopeng Li发布，本实验代码中进行保留


### 需要的环境：
* numpy、tensorflow、scipy
* 运行citeulike-a时，需要8G内存；运行citeulike-t时，需要16G内存


### 代码文件说明：
* test_mvae：预训练MVAE的初始化参数
* test_cmvae：训练用于推荐任务的CMVAE模型
* run_：为了简化操作，可直接运行该文件

* 在实验代码内包含两个测试系统性能的函数：evaluateCorrect和evaluatePaper
* evaluateCorrect：将用于训练的数据的得分压低
* evaluatePaper：没有将用于训练的数据的得分压低，导致召回率比较高，该版本是CVAE在论文中使用的。

* /data/citeulike-a/data_prep和/data/citeulike-t/data_prep用于划分训练集和测试集，运行该文件可以产生训练集文件，然后在test_cmvae中相应位置进行文件名的改动即可

* 实验数据集分别位于/data/citeulike-a和/data/citeulike-t中
* 模型的代码位于/lib中


### 使用：
* 首先运行run_.py文件，待程序运行完毕后，模型和训练得到的用户向量以及物品向量将保存于/model下。然后将pmf.mat取出，运行test.m即可验证。

### 数据说明，以citeulike-a为例，citeulike-t与此相同：
* /data/citeulike-a/mult_nor.mat：文本的向量表示数据
* /data/citeulike-a/citations.mat：链接的向量表示数据
* /data/citeulike-a/item_tag.mat：tag的向量表示数据
