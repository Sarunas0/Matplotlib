import numpy as np
import pandas as pd

%matplotlib inline

import matplotlib as mpl
import matplotlib.pyplot as plt



print('Matplotlib version: ', mpl.__version__)

from js import fetch
import io

URL = "https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DV0101EN-SkillsNetwork/Data%20Files/Canada.csv"
resp = await fetch(URL)
text = io.BytesIO((await resp.arrayBuffer()).to_py())
df_can = pd.read_csv(text)
print('Data read into a pandas dataframe!')



df_can.set_index('Country' , inplace=True)

df_can.head()


years = list(map(str, range(1980, 2014)))
df_line=df_can[years] # Creating df with years between 1980-2013

total_immigrants=df_line.sum() # Sum to get total immigrants year wise
total_immigrants



#Create figure and axes
fig, ax = plt.subplots()

total_immigrants.index = total_immigrants.index.map(int)


# Plot the line
ax.plot(total_immigrants)

#Setting up the Title
ax.set_title('Immigrants between 1980 to 2013') 
#Setting up the Labels
ax.set_xlabel('Years')
ax.set_ylabel('Total Immigrants')

#Display the plot
plt.show()

# Customizing the appearance of Plot
ax.plot(total_immigrants, 
        marker='s', #Including markers in squares shapes
        markersize=5, #Setting the size of the marker
        color='green', #Changing the color of the line
        linestyle="dotted") #Changing the line style to a Dotted line
