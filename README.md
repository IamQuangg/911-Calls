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

# Phân tích xu hướng theo ngày
    weekdays = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']

    df['Day of Week'] = pd.Categorical(df['Day of Week'], categories=weekdays, ordered=True)

    df =df.sort_values('Day of Week')

    byDayOfWeek = df.groupby('Day of Week').count()

    byDayOfWeek.head()
![image](https://github.com/IamQuangg/911-Calls/assets/128073066/4c684d6b-691a-46c4-859d-05bf5e7ee310)

 # Phân tích theo loại cuộc gọi
    byreason = df.groupby(df['Reason']).count()
    byreason.head()

    plt.figure()
    sns.barplot(x=byreason.index, y='title', data=byreason)
    
    plt.xlabel('Loại cuộc gọi')
    
    plt.ylabel('Số cuộc gọi')
    
    plt.title('Phân tích theo loại cuộc gọi')
    
    plt.show()

 ![image](https://github.com/IamQuangg/911-Calls/assets/128073066/4ab07e0f-953b-45ac-877c-e22a097758f8)

