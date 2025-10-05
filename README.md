# Amazon-Sales-Dataset-Real-Analysis
亚马逊销售数据分析

基于Kaggle的[Amazon Sales Dataset](https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset)（1462行产品数据），分析产品评级、价格、折扣和评论情感，优化亚马逊卖家策略，提升销量潜力15%。

## 项目背景
作为亚马逊卖家，需分析产品数据，识别高潜力类别，评估折扣对评级影响，挖掘用户反馈情感，预测产品受欢迎度。项目模拟Seller Central报告分析，展示亚马逊平台数据分析经验。

## 数据与技能
- **数据**：1462行产品数据（价格、评级、评论、类别）。
- **技能**：
  - 数据清洗：Pandas处理字符串价格、缺失值。
  - EDA：Seaborn可视化（柱状图、散点图、热力图）。
  - 情感分析：NLTK Vader分析评论情感。
  - 预测建模：Scikit-learn（线性回归、随机森林）。
- **工具**：Python, Google Colab, Jupyter Notebook。

## 分析流程与成果
1. **数据清洗**：转换价格（₹去除）、评级（'|'转NaN），提取主类别，清洗后1462行。
2. **EDA**：
   - 评级集中4.0-4.5，Computers&Accessories性价比高（评级4.16，价845₹）。
   - 折扣与评级弱负相关（-0.2），Electronics折扣高（60%）。
   - Electronics评级数最高（15.8M），Car&Motorbike最低（3.8，1118）。
3. **情感分析**：60%评论正面（sentiment_score >0.5），10-15%负面需优化。
4. **预测建模**：
   - 初始线性回归：MSE=0.07, R²=0.12。
   - 优化（加`rating_count`, `category_encoded`）：线性回归R²=0.15，随机森林MSE=0.06, R²=0.29。
   - 特征重要性：评级数（31.16%）、情感（25.81%）驱动评级。

![特征重要性](figures/feature_importance.png)

## 业务建议
- **推广Computers&Accessories**：高评级（4.16），低价（845₹），加PPC广告，预计销量升15%。
- **优化Car&Motorbike**：评级3.8，加20%折扣，改进描述，目标评级4.0。
- **利用正面评论**：提取关键词（如“耐用”），优化产品页面，预计转化率升10%。
- **调整Electronics折扣**：从60%降至50%，平衡利润与评级。
- **模型部署**：用随机森林预测评级>4.0产品，提升亚马逊排名。

## 文件结构
- `amazon.csv`: 原始数据集。
- `amazon_analysis.ipynb`: 完整分析代码（清洗、EDA、建模）。
- `amazon_analysis.html`: 可视化报告（含图表）。
- `figures/`: 图表（评级分布、散点图、热力图、情感分布）。
- `report.pdf`: 总结报告（洞察+建议）。

## 运行项目
1. 下载`amazon.csv`。
2. 运行`amazon_analysis.ipynb`（Google Colab）。
3. 查看`amazon_analysis.html`或`report.pdf`。

## 成果展示
- **评级分布**：![评级分布](figures/rating_distribution.png)
- **价格vs折扣**：![价格vs折扣](figures/price_vs_discount.png)
- **报告**：下载[report.pdf](report.pdf)

## 改进计划
- 添加词云分析评论关键词。
- 测试更多特征（如`actual_price`）或XGBoost模型，进一步提升R²。

