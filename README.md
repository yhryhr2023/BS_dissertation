# 重金属镉污染下石榴的耐性特征及富集 数据分析
## 数据准备
截取了发芽天数数据分析部分，用python的pandas和matplotlib对数据进行了重新分析。

### 环境设置
```
import pandas as pd
import matplotlib.pyplot as plt

plt.rcParams['font.sans-serif']=['SimHei'] #用来正常显示中文标签
plt.rcParams['axes.unicode_minus'] = False #用来正常显示负号
```

### 读取数据
```Python
发芽天数 = pd.read_csv('发芽天数.csv')
富集系数 = pd.read_csv('富集系数.csv')
叶绿素 = pd.read_csv('叶绿素.csv')
```

### 耐性特征
查看空白对照组的发芽天数
```
发芽天数.set_index("cd浓度",inplace = True)
发芽_对照组 = 发芽天数.iloc[0]
发芽_对照组 = 发芽_对照组[:3]

plt.figure(figsize=(8,4))
发芽_对照组.plot(kind="bar")
plt.xlabel("实验组", size = 13)
plt.ylabel("天数", size = 13)
plt.title('CK组发芽天数', size = 17)
```
![My Image](CK组发芽天数.jpg)
