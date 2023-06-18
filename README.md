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
    
    

