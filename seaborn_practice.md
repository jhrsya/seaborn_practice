

```python
!pip install seaborn
```

    Collecting seaborn
      Downloading seaborn-0.11.2-py3-none-any.whl (292 kB)
    [K     |████████████████████████████████| 292 kB 189 kB/s eta 0:00:01
    [?25hRequirement already satisfied: numpy>=1.15 in /home/huchaowen/.conda/envs/pyg/lib/python3.8/site-packages (from seaborn) (1.21.2)
    Requirement already satisfied: pandas>=0.23 in /home/huchaowen/.conda/envs/pyg/lib/python3.8/site-packages (from seaborn) (1.1.4)
    Requirement already satisfied: matplotlib>=2.2 in /home/huchaowen/.conda/envs/pyg/lib/python3.8/site-packages (from seaborn) (3.5.0)
    Requirement already satisfied: scipy>=1.0 in /home/huchaowen/.conda/envs/pyg/lib/python3.8/site-packages (from seaborn) (1.7.1)
    Requirement already satisfied: pillow>=6.2.0 in /home/huchaowen/.conda/envs/pyg/lib/python3.8/site-packages (from matplotlib>=2.2->seaborn) (8.4.0)
    Requirement already satisfied: pyparsing>=2.2.1 in /home/huchaowen/.conda/envs/pyg/lib/python3.8/site-packages (from matplotlib>=2.2->seaborn) (3.0.6)
    Requirement already satisfied: setuptools-scm>=4 in /home/huchaowen/.conda/envs/pyg/lib/python3.8/site-packages (from matplotlib>=2.2->seaborn) (6.3.2)
    Requirement already satisfied: python-dateutil>=2.7 in /home/huchaowen/.conda/envs/pyg/lib/python3.8/site-packages (from matplotlib>=2.2->seaborn) (2.8.2)
    Requirement already satisfied: cycler>=0.10 in /home/huchaowen/.conda/envs/pyg/lib/python3.8/site-packages (from matplotlib>=2.2->seaborn) (0.11.0)
    Requirement already satisfied: packaging>=20.0 in /home/huchaowen/.conda/envs/pyg/lib/python3.8/site-packages (from matplotlib>=2.2->seaborn) (21.3)
    Requirement already satisfied: fonttools>=4.22.0 in /home/huchaowen/.conda/envs/pyg/lib/python3.8/site-packages (from matplotlib>=2.2->seaborn) (4.28.1)
    Requirement already satisfied: kiwisolver>=1.0.1 in /home/huchaowen/.conda/envs/pyg/lib/python3.8/site-packages (from matplotlib>=2.2->seaborn) (1.3.2)
    Requirement already satisfied: pytz>=2017.2 in /home/huchaowen/.conda/envs/pyg/lib/python3.8/site-packages (from pandas>=0.23->seaborn) (2021.3)
    Requirement already satisfied: six>=1.5 in /home/huchaowen/.conda/envs/pyg/lib/python3.8/site-packages (from python-dateutil>=2.7->matplotlib>=2.2->seaborn) (1.16.0)
    Requirement already satisfied: tomli>=1.0.0 in /home/huchaowen/.conda/envs/pyg/lib/python3.8/site-packages (from setuptools-scm>=4->matplotlib>=2.2->seaborn) (1.2.2)
    Requirement already satisfied: setuptools in /home/huchaowen/.conda/envs/pyg/lib/python3.8/site-packages (from setuptools-scm>=4->matplotlib>=2.2->seaborn) (58.0.4)
    Installing collected packages: seaborn
    Successfully installed seaborn-0.11.2



```python
import seaborn as sns
sns.set_theme()
tips = sns.load_dataset("tips")
```


```python
print(type(tips))
```

    <class 'pandas.core.frame.DataFrame'>



```python
print(tips.shape)
```

    (244, 7)



```python
print(tips[:5])
```

       total_bill   tip     sex smoker  day    time  size
    0       16.99  1.01  Female     No  Sun  Dinner     2
    1       10.34  1.66    Male     No  Sun  Dinner     3
    2       21.01  3.50    Male     No  Sun  Dinner     3
    3       23.68  3.31    Male     No  Sun  Dinner     2
    4       24.59  3.61  Female     No  Sun  Dinner     4



```python
sns.relplot(data = tips, x = "total_bill", y = "tip", col = "time", hue = "smoker", style = "size", size = "size")#day，sex没有用上，
```




    <seaborn.axisgrid.FacetGrid at 0x7f72740022b0>




![png](output_5_1.png)



```python
time = set()
for s in tips["smoker"]:
    time.add(s)
print(time)
```

    {'No', 'Yes'}



```python
sns.relplot(data = tips, x = "total_bill", y = "tip", col = "time", hue = "smoker", style = "smoker", size = "size")#day，sex没有用上，
```




    <seaborn.axisgrid.FacetGrid at 0x7f72732777c0>




![png](output_7_1.png)

