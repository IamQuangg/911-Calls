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
    
    
    
    

