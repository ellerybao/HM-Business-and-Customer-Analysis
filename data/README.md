# data文件夹
此文件夹专门用于放置原始数据集及用于Tableau看板制作的数据。

## 关于原始数据集
原始数据集因为占用内存过大，这里用Kaggle链接替代。

**Kaggle官方链接**：https://www.kaggle.com/competitions/h-and-m-personalized-fashion-recommendations/data  （需注册账号加入比赛下载，部分地区存在验证限制，可能无法加入）

**备用链接（百度网盘）**：https://pan.baidu.com/s/1oM3_ovSYNzODWX2cKhg73g?pwd=hmod 提取码: hmod

下载后请解压文件，并将文件中的customers.csv、articles.csv、transactions_train.csv共计三张表拖入此文件夹。

## 关于中间表（processed文件夹）

由于文件较大，`processed/` 文件夹下的6张中间表已上传至百度网盘。

**下载链接（百度网盘）**：https://pan.baidu.com/s/14BX-jKZm_tNV2cov_-rlJw?pwd=proc 提取码: proc

下载后请解压到 `data/processed/` 目录下，得到以下6个文件。为与原始数据集文件名区分，对其中Customers.csv、Articles.csv、Transactions.csv文件名首字母进行大写处理。

- **Customers.csv**：数据清洗后新增了一列RFM分层标签。

- **Articles.csv**：仅删除原表无用字段。

- **Transactions.csv**：数据清洗后新增还原价格、年月及工作日字段，并将sales_channel_id字段的两个数字替换成对应的渠道。

- **monthly_channel.csv**：由于数据集中不存在H&M2020年4月线下销售数据，为便于Tableau看板制作，制作一份聚合计算了每月不同渠道的销售额及消费人数表，并补齐2020年4月线下销售数据。

- **prefer_idx.csv**：为制作RFM客群对品类偏好的偏好指数热力图，将notebook中计算好的偏好矩阵导出。

- **baskets.csv**：用于制作品类关联分析图、AOV等指标的趋势展示。

**注意**：所有 CSV 文件使用 UTF-8 编码保存。Windows Excel 直接打开中文列可能出现乱码，请通过"数据 → 从文本/CSV → 选择 UTF-8 编码"方式导入，或使用 Tableau、Power BI、Python 等工具打开。