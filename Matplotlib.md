### Import
```
from matplotlib import pyplot as plt
```

### plt.plot() and plt.show()
```
x_values = [0, 1, 2, 3, 4]
y_values = [0, 1, 4, 9, 16]
plt.plot(x_values, y_values)  # create a simple line graph using .plot() and display it using .show()
plt.show()
```
```
import codecademylib
from matplotlib import pyplot as plt

time = [0, 1, 2, 3, 4]
revenue = [200, 400, 650, 800, 850]
costs = [150, 500, 550, 550, 560]
plt.plot(time,revenue)  #一幅图可以show两条线或更多
plt.plot(time,costs)
plt.show()
```

### linestyle
```
# Dashed:
plt.plot(x_values, y_values, linestyle='--')
# Dotted:
plt.plot(x_values, y_values, linestyle=':')
# No line:
plt.plot(x_values, y_values, linestyle='')
```
```
# A circle:
plt.plot(x_values, y_values, marker='o')
# A square:
plt.plot(x_values, y_values, marker='s')
# A star:
plt.plot(x_values, y_values, marker='*')
```
```
plt.plot(days, money_spent, color='green')
plt.plot(days, money_spent_2, color='#AAAAAA')
```
```
plt.plot(days, money_spent, color='green', linestyle='--')
plt.plot(days, money_spent_2, color='#AAAAAA',  marker='o')
```
### Axis and Labels
```
plt.axis([0, 3, 2, 5])
```
a plot from x=0 to x=3 and from y=2 to y=5

### Labeling
```
hours = [9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20]
happiness = [9.8, 9.9, 9.2, 8.6, 8.3, 9.0, 8.7, 9.1, 7.0, 6.4, 6.9, 7.5]
plt.plot(hours, happiness)
plt.xlabel('Time of day')
plt.ylabel('Happiness Rating (out of 10)')
plt.title('My Self-Reported Happiness While Awake')
plt.show()
```

### Subplot
```
plt.subplot(2, 3, 4)  
```
```
The number of rows of subplots
The number of columns of subplots
The index of the subplot we want to create.即第几个subplot
```
```
import codecademylib
from matplotlib import pyplot as plt

months = range(12)
temperature = [36, 36, 39, 52, 61, 72, 77, 75, 68, 57, 48, 48]
flights_to_hawaii = [1200, 1300, 1100, 1450, 850, 750, 400, 450, 400, 860, 990, 1000]

plt.subplot(1, 2, 1)
plt.plot(months, temperature)

plt.subplot(1, 2, 2)
plt.plot(temperature, flights_to_hawaii, "o")

plt.show()
```

### plt.subplots_adjust()
```
plt.subplots_adjust()
```
```
left — the left-side margin, with a default of 0.125. You can increase this number to make room for a y-axis label
right — the right-side margin, with a default of 0.9. You can increase this to make more room for the figure, or decrease it to make room for a legend
bottom — the bottom margin, with a default of 0.1. You can increase this to make room for tick mark labels or an x-axis label
top — the top margin, with a default of 0.9
wspace — the horizontal space between adjacent subplots, with a default of 0.2
hspace — the vertical space between adjacent subplots, with a default of 0.2
```
```
import codecademylib
from matplotlib import pyplot as plt

x = range(7)
straight_line = [0, 1, 2, 3, 4, 5, 6]
parabola = [0, 1, 4, 9, 16, 25, 36]
cubic = [0, 1, 8, 27, 64, 125, 216]

# Subplot 1
plt.subplot(2, 1, 1) # 占据了整个第一行
plt.plot(x, straight_line)

# Subplot 2
plt.subplot(2, 2, 3) # 两行两列的第两行一列的图
plt.plot(x, parabola)

# Subplot 3
plt.subplot(2, 2, 4)
plt.plot(x, cubic)

plt.subplots_adjust(wspace=0.35, bottom=0.2)

plt.show()
```

### Legends
```
plt.plot([0, 1, 2, 3, 4], [0, 1, 4, 9, 16])
plt.plot([0, 1, 2, 3, 4], [0, 1, 8, 27, 64])
plt.legend(['parabola', 'cubic'], loc=6)  #loc决定legend的位置
plt.show()
```
也可以是
```
plt.plot([0, 1, 2, 3, 4], [0, 1, 4, 9, 16],
         label="parabola")
plt.plot([0, 1, 2, 3, 4], [0, 1, 8, 27, 64],
         label="cubic")
plt.legend() # Still need this command!
plt.show()
```

### ticks
```
import codecademylib
from matplotlib import pyplot as plt

month_names = ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep","Oct", "Nov", "Dec"]

months = range(12)
conversion = [0.05, 0.08, 0.18, 0.28, 0.4, 0.66, 0.74, 0.78, 0.8, 0.81, 0.85, 0.85]

plt.xlabel("Months")
plt.ylabel("Conversion")
ax = plt.subplot() 想要有ticks就必须设定subplot()，即使只有一张图

plt.plot(months, conversion)
ax.set_xticks(months)
ax.set_xticklabels(month_names)
ax.set_yticks([0.10, 0.25, 0.5, 0.75])
ax.set_yticklabels(['10%', '25%', '50%', '75%'])
# Your work here

plt.show()
```

### plt.figure()
We can use the command plt.figure() to create new figures and size them how we want.
```
# Figure 2
plt.figure(figsize=(4, 10))  #宽4inches，长10inches
plt.plot(x, parabola)
plt.savefig('tall_and_narrow.png')
```
In order to be sure that you don’t have any stray lines, you can use the command, 
```
plt.close('all')
```
 to clear all existing plots before you plot a new one.
 ```
 import codecademylib
from matplotlib import pyplot as plt

word_length = [8, 11, 12, 11, 13, 12, 9, 9, 7, 9]
power_generated = [753.9, 768.8, 780.1, 763.7, 788.5, 782, 787.2, 806.4, 806.2, 798.9]
years = [2000, 2001, 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009]

plt.close('all')
plt.figure()
plt.plot(years, word_length)
plt.savefig('winning_word_lengths.png')
plt.figure(figsize=(7, 3))
plt.plot(years, power_generated)
plt.savefig('power_generated.png')
```



