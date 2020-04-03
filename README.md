## 01/ 任务
A公司希望发掘用户购买产品的行为习惯，建立产品精准营销模型，对有意向的客户进行精准营销，增加收入，减少开支。

## 02/ 数据
参赛选手将取得训练数df_training.csv及测试数据df_test.csv。  

### 2.1 训练数据
训练数据包含6000笔客户资料；每笔客户资料包含12个字段(1个客户ID字段、10个输入字段及1个目标字段-Purchase or not购买与否(0代表未购买，1代表购买)。  

### 2.2 测试数据
测试数据包含2000笔客户资料；字段个数与训练数据相同，唯目标字段的值全部填“Withheld”。

## 03/ 评分标准
我们通过混淆矩阵（Confusion matrix）来评价分类模型的准确率。准确率越高，说明正确预测出响应营销效果越好

## 模型构建过程
1.加载数据，分析得出样本不均衡，同时缺失值较多，采用对缺失值不敏感的xgboost进行模型的训练  
2.通过GridSearchCV优化模型参数  
3.通过BaggingClassifier提高模型准确率  
4.通过cross_val_score评估模型效果  
