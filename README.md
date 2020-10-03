# Technotip
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
x=pd.read_csv("C:/Anaconda codes/FLOOD-PREDICTION/kerala.csv")
y=pd.read_csv("C:/Anaconda codes/FLOOD-PREDICTION/kerala.csv")

y1=list(x["YEAR"])
x1=list(x["Jun-Sep"])
z1=list(x["JUN"])
w1=list(x["MAY"])

plt.plot(y1, x1,'*')
plt.show()


flood=[]
june=[]
sub=[]

#CREATING A NEW COLOUMN WITH BINARY CLASSIFICATION DEPENDING IF THAT YEAR HAD FLOODED OR NOT, USING RAINFALL OF THAT YEAR AS THRESHOLD
#print(x1[114])
for i in range(0,len(x1)):
    if x1[i]>2400:
        flood.append('1')
    else:
        flood.append('0')

#print(len(x1))

#APPROAXIMATELY FINDING THE RAINFALL DATA FOR 10 DAYS FOR THE MONTH OF JUNE IN EVERY YEAR FROM 1901 TO 2015
for k in range(0,len(x1)):
    june.append(z1[k]/3)

#FINDING THE INCREASE IN RAINFALL FROM THE MONTH OF MAY TO THE MONTH OF JUNE IN EVERY YEAR FROM 1901 TO 2015
for k in range(0,len(x1)):
    sub.append(abs(w1[k]-z1[k]))

#print(len(flood),len(x1))
df = pd.DataFrame({'flood':flood})
df1=pd.DataFrame({'per_10_days':june})

x["flood"]=flood
x["avgjune"]=june
x["sub"]=sub

#SAVING THE NEW CSV FILE WITH THE NEW COLOUMNS
x.to_csv("out1.csv")
print((x))

 SUBDIVISION  YEAR   JAN   FEB    MAR    APR    MAY     JUN     JUL    AUG  \
0        KERALA  1901  28.7  44.7   51.6  160.0  174.7   824.6   743.0  357.5   
1        KERALA  1902   6.7   2.6   57.3   83.9  134.5   390.9  1205.0  315.8   
2        KERALA  1903   3.2  18.6    3.1   83.6  249.7   558.6  1022.5  420.2   
3        KERALA  1904  23.7   3.0   32.2   71.5  235.7  1098.2   725.5  351.8   
4        KERALA  1905   1.2  22.3    9.4  105.9  263.3   850.2   520.5  293.6   
5        KERALA  1906  26.7   7.4    9.9   59.4  160.8   414.9   954.2  442.8   
6        KERALA  1907  18.8   4.8   55.7  170.8  101.4   770.9   760.4  981.5   
7        KERALA  1908   8.0  20.8   38.2  102.9  142.6   592.6   902.2  352.9   
8        KERALA  1909  54.1  11.8   61.3   93.8  473.2   704.7   782.3  258.0   
9        KERALA  1910   2.7  25.7   23.3  124.5  148.8   680.0   484.1  473.8   
10       KERALA  1911   3.0   4.3   18.2   51.0  180.6   990.0   705.3  178.6   
11       KERALA  1912   1.9  15.0   11.2  122.7  217.3   948.2   833.6  534.4   
12       KERALA  1913   3.1   5.2   20.7   75.7  198.8   541.7   763.2  247.2   
13       KERALA  1914   0.7   6.8   18.1   32.7  164.2   565.3   857.7  402.2   
14       KERALA  1915  16.9  23.5   42.7  106.0  154.5   696.1   775.6  298.8   
15       KERALA  1916   0.0   7.8   22.0   82.4  199.0   920.2   513.9  396.9   
16       KERALA  1917   2.9  47.6   79.4   38.1  122.9   703.7   342.7  335.1   
17       KERALA  1918  42.9   5.0   32.8   51.3  683.0   464.3   167.5  376.0   
18       KERALA  1919  43.0   6.1   33.9   65.9  247.0   636.8   648.0  484.2   
19       KERALA  1920  35.2   5.5   24.1  172.0   87.7   964.3   940.8  235.0   
20       KERALA  1921  43.0   4.7   15.0  171.3  104.1   489.1   639.8  641.9   
21       KERALA  1922  30.5  21.4   16.3   89.6  293.6   663.1  1025.1  320.6   
22       KERALA  1923  24.7   0.7   78.9   43.5   80.0   722.5  1008.7  943.0   
23       KERALA  1924  19.3   2.9   66.6  111.0  185.4  1011.7  1526.5  624.0   
24       KERALA  1925   4.1  16.5   76.9   93.4  258.2   688.8   593.5  554.1   
25       KERALA  1926  28.6   5.8   23.1   55.8  222.6   563.9   885.2  536.0   
26       KERALA  1927  18.8  35.3   49.6   86.5  265.4   720.2   888.2  315.0   
27       KERALA  1928  12.7  65.9   51.3  121.1   81.9   590.7   420.6  553.2   
28       KERALA  1929  12.8  29.8   58.9  210.7  148.0   946.6   844.0  293.9   
29       KERALA  1930  10.8  10.8   39.0  102.7  404.9   633.1   401.7  273.4   
..          ...   ...   ...   ...    ...    ...    ...     ...     ...    ...   
85       KERALA  1986   5.6  18.7   11.2   63.1  126.7   597.9   324.8  340.3   
86       KERALA  1987   0.6   0.8    4.3   57.2  108.3   572.6   221.0  396.6   
87       KERALA  1988   0.8  17.5   38.1  177.6  157.2   511.3   502.8  379.8   
88       KERALA  1989  10.3   0.0   30.1  141.5  169.4   657.5   450.7  285.5   
89       KERALA  1990  14.9   4.8   18.0   41.8  488.5   528.6   635.4  370.8   
90       KERALA  1991  10.9   4.4   33.2   97.0  113.4  1096.1   905.5  465.5   
91       KERALA  1992   2.4   0.9    0.1   43.0  218.4   819.3   767.8  508.0   
92       KERALA  1993   0.0  17.8   20.1   66.5  159.0   657.1   776.1  301.9   
93       KERALA  1994  24.3  27.1   18.1  154.5  141.3   845.0   955.5  479.9   
94       KERALA  1995  10.3   6.5   37.3  134.9  355.6   493.4   702.5  457.3   
95       KERALA  1996   2.8   9.1   14.4  124.3   74.3   572.4   696.0  327.4   
96       KERALA  1997   2.1   1.5   36.1   60.6  133.6   544.2   970.5  536.0   
97       KERALA  1998   6.0   2.1    8.1   61.1  151.6   732.5   641.4  371.8   
98       KERALA  1999   1.8  23.8   21.4  111.6  453.2   607.3   700.4  266.3   
99       KERALA  2000  11.7  57.8   21.5   96.3  124.5   633.8   343.2  566.5   
100      KERALA  2001  16.5  28.3    7.0  238.0  238.6   715.3   598.5  361.3   
101      KERALA  2002   4.7   8.7   35.7  117.3  330.8   503.1   318.7  438.2   
102      KERALA  2003   0.7  50.9   82.1  134.4   91.0   566.7   532.0  350.3   
103      KERALA  2004   2.4   8.1   37.9  113.2  610.9   673.4   385.4  417.9   
104      KERALA  2005  19.8   7.0   25.3  205.9  134.8   619.2   832.7  291.0   
105      KERALA  2006   8.1   0.5   90.7   65.3  521.2   482.4   804.0  432.6   
106      KERALA  2007   0.5   5.6    7.3  138.5  192.7   705.9   966.3  489.6   
107      KERALA  2008   0.8  30.3  217.2  108.4   81.2   469.9   505.1  349.0   
108      KERALA  2009   3.3   1.5   62.6   69.0  191.6   438.2   924.9  269.3   
109      KERALA  2010  18.6   1.0   31.4  138.9  190.6   667.5   629.0  356.0   
110      KERALA  2011  20.5  45.7   24.1  165.2  124.2   788.5   536.8  492.7   
111      KERALA  2012   7.4  11.0   21.0  171.1   95.3   430.3   362.6  501.6   
112      KERALA  2013   3.9  40.1   49.9   49.3  119.3  1042.7   830.2  369.7   
113      KERALA  2014   4.6  10.3   17.9   95.7  251.0   454.4   677.8  733.9   
114      KERALA  2015   3.1   5.8   50.1  214.1  201.8   563.6   406.0  252.2   

     ...      NOV    DEC  ANNUAL  Jan-Feb  Mar-May  Jun-Sep  Oct-Dec  flood  \
0    ...    350.8   48.4  3248.6     73.4    386.2   2122.8    666.1      0   
1    ...    158.3  121.5  3326.6      9.3    275.7   2403.4    638.2      1   
2    ...    157.0   59.0  3271.2     21.7    336.3   2343.0    570.1      0   
3    ...     33.9    3.3  3129.7     26.7    339.4   2398.2    365.3      0   
4    ...     74.4    0.2  2741.6     23.4    378.5   1881.5    458.1      0   
5    ...    163.1   86.0  2708.0     34.1    230.0   1943.1    500.8      0   
6    ...    219.1   52.8  3671.1     23.7    328.0   2737.8    581.7      1   
7    ...     47.9   11.0  2648.3     28.8    283.7   2023.6    312.2      0   
8    ...    171.1   32.3  3050.2     65.9    628.3   1940.4    415.5      0   
9    ...    280.4    0.1  2848.6     28.4    296.7   1886.5    637.0      0   
10   ...    145.7   87.6  2726.7      7.3    249.7   1934.0    535.7      0   
11   ...    138.7   22.0  3451.3     16.9    351.1   2453.1    630.2      1   
12   ...    109.9   45.8  2610.8      8.3    295.2   1729.0    578.3      0   
13   ...    100.9  135.2  2899.1      7.6    215.0   2066.1    610.5      0   
14   ...    302.5   14.9  3024.5     40.4    303.1   2167.0    514.0      0   
15   ...    134.3    8.9  2945.3      7.8    303.4   2170.2    463.9      0   
16   ...    256.4   41.6  2704.8     50.5    240.4   1851.7    562.1      0   
17   ...    295.4   54.1  2501.9     47.9    767.0   1104.3    582.6      0   
18   ...    280.1   53.0  3003.3     49.2    346.8   2025.0    582.3      0   
19   ...    302.3    8.2  3303.1     40.6    283.7   2318.2    660.6      0   
20   ...    136.2   15.8  2719.9     47.8    290.3   1927.5    454.3      0   
21   ...    293.7   25.1  3267.6     51.9    399.4   2231.2    585.1      0   
22   ...     83.9   41.6  3484.7     25.3    202.3   2928.4    328.6      1   
23   ...    162.9   50.4  4226.4     22.2    363.0   3451.3    389.9      1   
24   ...    223.7   98.8  3062.1     20.5    428.5   1995.2    617.9      0   
25   ...     88.8   16.2  2965.4     34.4    301.5   2307.8    321.7      0   
26   ...    137.6    6.8  2994.7     54.1    401.4   2258.9    280.2      0   
27   ...    155.2   52.7  2502.8     78.6    254.3   1640.4    529.4      0   
28   ...    158.2   39.4  3361.6     42.6    417.6   2353.5    548.0      0   
29   ...    207.0   89.2  3018.0     21.6    546.5   1719.7    730.2      0   
..   ...      ...    ...     ...      ...      ...      ...      ...    ...   
85   ...    194.7    9.5  2093.2     24.3    200.9   1498.4    369.6      0   
86   ...    216.0  131.1  2137.6      1.4    169.7   1347.2    619.2      0   
87   ...     67.0   31.1  2403.5     18.3    372.9   1845.7    166.6      0   
88   ...     92.9    5.6  2422.7     10.3    341.1   1664.7    406.5      0   
89   ...    158.8    5.2  2693.1     19.7    548.3   1638.0    487.2      0   
90   ...     99.9    2.3  3184.5     15.3    243.6   2515.6    410.0      1   
91   ...    287.6    3.7  3239.5      3.4    261.6   2392.5    582.1      0   
92   ...    153.8   46.2  2717.7     17.8    245.6   1823.1    631.3      0   
93   ...    117.6    6.5  3410.8     51.4    313.9   2493.0    552.5      1   
94   ...    182.6    0.1  2858.8     16.8    527.8   1933.2    380.9      0   
95   ...     89.9   62.5  2610.0     11.8    213.0   1938.5    446.6      0   
96   ...    298.4   88.4  3252.4      3.7    230.2   2342.9    675.7      0   
97   ...    135.0   79.4  3151.5      8.0    220.8   2263.4    659.3      0   
98   ...     68.1    4.9  2914.6     25.5    586.2   1661.9    640.9      0   
99   ...     78.1   69.1  2412.6     69.5    242.3   1739.4    361.5      0   
100  ...    181.0   10.1  2931.1     44.7    483.7   1892.0    510.7      0   
101  ...    137.5    2.1  2507.4     13.3    483.7   1359.0    651.3      0   
102  ...     76.4    9.7  2394.9     51.6    307.5   1542.6    493.1      0   
103  ...    120.7    2.7  2886.1     10.5    762.0   1669.5    444.0      0   
104  ...    184.3   56.4  3031.1     26.8    366.0   2157.6    480.7      0   
105  ...    162.8    1.8  3420.6      8.6    677.2   2193.8    541.0      0   
106  ...     87.4   11.9  3489.6      6.1    338.4   2688.5    456.5      1   
107  ...     55.4   17.0  2524.5     31.1    406.7   1670.9    415.7      0   
108  ...    274.4   44.2  2810.6      4.8    323.1   1958.9    523.8      0   
109  ...    335.1   46.8  3131.8     19.6    360.9   1928.0    823.3      0   
110  ...    169.7   49.5  3035.1     66.2    313.5   2209.1    446.3      0   
111  ...    112.9    9.4  2151.1     18.3    287.4   1535.6    309.8      0   
112  ...    154.9   17.0  3255.4     43.9    218.5   2561.2    431.8      1   
113  ...     99.5   47.2  3046.4     14.9    364.5   2164.8    502.1      0   
114  ...    223.6   79.4  2600.6      8.9    465.9   1514.7    611.1      0   

        avgjune    sub  
0    274.866667  649.9  
1    130.300000  256.4  
2    186.200000  308.9  
3    366.066667  862.5  
4    283.400000  586.9  
5    138.300000  254.1  
6    256.966667  669.5  
7    197.533333  450.0  
8    234.900000  231.5  
9    226.666667  531.2  
10   330.000000  809.4  
11   316.066667  730.9  
12   180.566667  342.9  
13   188.433333  401.1  
14   232.033333  541.6  
15   306.733333  721.2  
16   234.566667  580.8  
17   154.766667  218.7  
18   212.266667  389.8  
19   321.433333  876.6  
20   163.033333  385.0  
21   221.033333  369.5  
22   240.833333  642.5  
23   337.233333  826.3  
24   229.600000  430.6  
25   187.966667  341.3  
26   240.066667  454.8  
27   196.900000  508.8  
28   315.533333  798.6  
29   211.033333  228.2  
..          ...    ...  
85   199.300000  471.2  
86   190.866667  464.3  
87   170.433333  354.1  
88   219.166667  488.1  
89   176.200000   40.1  
90   365.366667  982.7  
91   273.100000  600.9  
92   219.033333  498.1  
93   281.666667  703.7  
94   164.466667  137.8  
95   190.800000  498.1  
96   181.400000  410.6  
97   244.166667  580.9  
98   202.433333  154.1  
99   211.266667  509.3  
100  238.433333  476.7  
101  167.700000  172.3  
102  188.900000  475.7  
103  224.466667   62.5  
104  206.400000  484.4  
105  160.800000   38.8  
106  235.300000  513.2  
107  156.633333  388.7  
108  146.066667  246.6  
109  222.500000  476.9  
110  262.833333  664.3  
111  143.433333  335.0  
112  347.566667  923.4  
113  151.466667  203.4  
114  187.866667  361.8  

[115 rows x 22 columns]

import scipy 
from scipy.stats import spearmanr

from sklearn.ensemble import RandomForestClassifier
from sklearn.preprocessing import scale
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import train_test_split
from sklearn import preprocessing
#TAKING THE COLOUMNS WHICH ARE TO USED FOR TRAINING THE MODEL
#16 MAR-MAY
#20- AVG OF 10 DAYS JUNE 
#21- DIFFERENCE OF RAINFALL FROM MAY TO JUNE
#19 - BINARY CLASS OF FLOOD- 0 OR 1
#MORE DATA CAN BE ADDED FOR TRAINING, BY JUST ADDING MORE NUMBER OF COLOUMNS FROM THE CSV FILE

#WE USE LOGISTIC REGRESSION FOR TRAINING

X = x.ix[:,{16,20,21}].values
y1=x.ix[:,19].values

(X_train, X_test, Y_train, Y_test) = train_test_split(X, y1, random_state=0)


#X1= scale(X)
#print(X1)

Lr=LogisticRegression()

Lr.fit(X,y1)
print(Lr.score(X,y1))  # PRINTS THE ACCURACY
#ypred=Lr.score(X_test,Y_test)
#print(ypred)

C:\Anaconda3\lib\site-packages\ipykernel_launcher.py:11: DeprecationWarning: 
.ix is deprecated. Please use
.loc for label based indexing or
.iloc for positional indexing

See the documentation here:
http://pandas.pydata.org/pandas-docs/stable/indexing.html#ix-indexer-is-deprecated
  # This is added back by InteractiveShellApp.init_path()
C:\Anaconda3\lib\site-packages\ipykernel_launcher.py:12: DeprecationWarning: 
.ix is deprecated. Please use
.loc for label based indexing or
.iloc for positional indexing

See the documentation here:
http://pandas.pydata.org/pandas-docs/stable/indexing.html#ix-indexer-is-deprecated
  if sys.path[0] == '':
  0.860869565217
  
  q1=275 # present years march to may rainfall data on average
w1=130 #average rainfall in past 10 days of june
e1=260 #average inscrease in rainfall from may to june 

q2=200 # present years march to may rainfall data on average
w2=400 #average rainfall in past 10 days of june
e2=300 #average inscrease in rainfall from may to june 


l=[[q1,w1,e1],[q2,w2,e2],[50,300,205]]

#print(X)

#ypred=Lr.predict(X)
f1=Lr.predict(l)

for i in range(len(f1)):

    if (int(f1[i])==1):
        print(f1[i],"- possibility of  severe flood")
    else:
        print(f1[i],"- no chance of severe flood")
    
        
"""
print("data1 prediction",f1[0],"=")
print("data2 prediction",f1[1])
"""
0 - no chance of severe flood
1 - possibility of  severe flood
1 - possibility of  severe flood
out:
'\nprint("data1 prediction",f1[0],"=")\nprint("data2 prediction",f1[1])\n
