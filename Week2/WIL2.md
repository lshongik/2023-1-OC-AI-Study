import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

data = pd.read_csv('test.csv')


plt.figure(figsize=(20, 5))

plt.subplot(1,3,1)
sns.kdeplot(data['Age'], fill=True, color='gray')

plt.subplot(1,3,2)
a, b, c = 0, 0, 0
for i in data['Pclass']:
    if i == 1:
        a += 1
    elif i == 2:
        b += 1
    else:
        c += 1
plt.pie([a, b, c], labels=['class 1', 'class 2', 'class 3'], autopct='%.1f%%')

plt.show()