# Amazon-Sales-Dataset-Real-Analysis
亚马逊销售数据分析
- **数据**：Kaggle 1462行产品数据（价格、评级、评论）。数据集地址https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset/data
- **技能**：清洗字符串（Pandas）、EDA（Seaborn）、情感分析（NLTK）、预测建模（Scikit-learn）。
- **优化**：初始线性回归（MSE=0.07, R²=0.12）添加rating_count和类别特征，随机森林提升至MSE=0.06, R²=0.29。
- **洞察**：评级数（31.16%重要性）和评论情感（25.81%）驱动评级，Computers&Accessories性价比高（评级4.16，价845₹）。
- **建议**：推广高性价比产品，优化Car&Motorbike（评级3.8），预计销量升15%。
