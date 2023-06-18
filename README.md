# Data and set up

    import numpy as np

    import pandas as pd

    import matplotlib.pyplot as plt

    import seaborn as sns

    %matplotlib inline

    df = pd.read_csv("D:/Python For DA/911.csv")

    df.head()

    df['Reason'] = df['title'].apply(lambda title : title.split(':')[0])
    
    df['Reason']

    df['Hour'] = df['timeStamp'].apply(lambda time : time.hour)
    
    df['Month'] = df['timeStamp'].apply(lambda time : time.month)
    
    df['Day of Week'] = df['timeStamp'].apply(lambda time : time.dayofweek)
    
    df.head()

    dmap = {0:'Mon',1:'Tue',2:'Wed',3:'Thu',4:'Fri',5:'Sat',6:'Sun'}
    
    df['Day of Week'] = df['Day of Week'].map(dmap)
    
    df.head()

    sns.countplot(x = 'Month', data = df, hue= 'Reason')
    
    plt.legend(bbox_to_anchor =(1.05,1), loc = 2, borderaxespad = 0)

![image](https://github.com/IamQuangg/911-Calls/assets/128073066/32a96be7-30f3-436b-8861-d7317d229ffa)

# Phân tích xu hướng theo tháng 
    plt.figure()

    sns.barplot(x=byMonth.index, y='title', data=byMonth)

    plt.xlabel('Tháng')

    plt.ylabel('Số cuộc gọi cấp cứu')

    plt.title('Số cuộc gọi cấp cứu theo tháng')

    plt.show()
![image](https://github.com/IamQuangg/911-Calls/assets/128073066/dbeefece-dbf5-4f76-865a-ad972a260b2f)


    
    

