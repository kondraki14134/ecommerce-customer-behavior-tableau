# 数据说明 / Data Notes

## 1. 数据来源

| 项目 | 内容 |
|---|---|
| 数据集 | Customer Purchase Behavior Dataset (E-commerce) |
| 作者/发布者 | Gautham Vijayaraj |
| 来源 | [Kaggle](https://www.kaggle.com/datasets/gauthamvijayaraj/customer-purchase-behavior-dataset-e-commerce/data) |
| 规模 | 500,000 行 × 18 列 |
| 文件 | `customerData_500k.csv`（约 57 MB） |
| 许可 | **CC BY-NC 4.0**（署名—禁止商用） |

> 本仓库**不直接分发**完整的 500,000 行 CSV。这样做有三个原因：  
> 1. 原始文件约 57 MB，直接提交会让 Git 仓库变重；  
> 2. 数据集采用 CC BY-NC 4.0，需保留原作者的署名并限制商业用途；  
> 3. GitHub 更鼓励仓库只保留代码、文档和可复现所需的最小样例。

## 2. 如何获取完整数据

1. 打开 [Kaggle 数据页](https://www.kaggle.com/datasets/gauthamvijayaraj/customer-purchase-behavior-dataset-e-commerce/data) 并登录 Kaggle。
2. 下载 `customerData_500k.csv`。
3. 将文件放到本目录：

   ```text
   data/customerData_500k.csv
   ```

4. 回到仓库根目录，打开 `电商平台分析.twb`。

如果 Tableau 提示找不到文件，请在 **Data → Edit Connection** 中重新选择该 CSV。连接设置为：

- 文件类型：Text file
- 分隔符：逗号
- 字符集：UTF-8
- 首行为表头：是

## 3. 仓库中的样例

`data/sample/customerData_sample_5000.csv` 是完整数据集的前 5,000 行（含表头），用于：

- 让别人不用下载 57 MB 文件也能查看数据结构；
- 快速验证 Tableau 连接和字段类型；
- 在 CI/文档预览中作为轻量样例。

样例仅用于预览，所有图表和结论应以完整 500,000 行数据为准。样例同样遵循 **CC BY-NC 4.0**。

## 4. 字段字典

| 字段 | 类型 | 说明 | 范围 / 取值 |
|---|---|---|---|
| `Customer_ID` | string | 客户唯一标识 | 形如 `ID,001` |
| `Age` | integer | 年龄（岁） | 15–81 |
| `AnnualIncome` | float | 年收入（美元） | 约 11,966–204,178 |
| `NumberOfPurchases` | integer | 总购买次数 | 非负整数 |
| `TimeSpentOnWebsite` | float | 每次访问平均停留时长（分钟） | 非负 |
| `CustomerTenureYears` | float | 加入平台时长（年） | 非负 |
| `LastPurchaseDaysAgo` | integer | 距最近一次购买的天数 | 非负 |
| `Gender` | category | 性别 | Male / Female |
| `ProductCategory` | category | 最常购买品类 | Fashion / Kitchen / Electronics / Furniture / Groceries |
| `PreferredDevice` | category | 最常用设备 | Mobile / Desktop / Tablet |
| `Region` | category | 所在区域 | North / South / East / West |
| `ReferralSource` | category | 获客渠道 | Organic / Paid Ads / Email / Social / Referral |
| `CustomerSegment` | category | 客户分层 | Regular / Premium / VIP |
| `LoyaltyProgram` | binary | 是否加入忠诚度计划 | 0 / 1 |
| `DiscountsAvailed` | integer | 使用优惠券数量 | 非负整数 |
| `SessionCount` | integer | 会话/访问次数 | 非负整数 |
| `CustomerSatisfaction` | integer | 满意度评分 | 1–5 |
| `PurchaseStatus` | binary | 是否购买（目标变量） | 0 / 1 |

## 5. 数据质量

对完整 CSV 的检查结果：

- 行数：500,000
- 列数：18
- 缺失值：0
- 完全重复行：0
- 目标变量分布：`PurchaseStatus = 0` 为 290,823 条，`= 1` 为 209,177 条
- 整体转化率：41.84%

## 6. 使用限制

- 本数据集仅供学习、研究和非商业分析使用。
- 不得移除原作者的署名，不得将数据集或其派生样例用于商业用途。
- 数据集可能是模拟/合成数据；分析结论只针对该数据集，不应直接外推到真实电商平台。
- 如需引用，请同时引用原数据集和本项目，见仓库根目录的 `CITATION.cff` 与 `NOTICE`。
