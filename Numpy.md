### Creating an Array from a CSV
```
csv_array = np.genfromtxt('sample.csv', delimiter=',') # delimiter的符号取决于额csv中的符号
```
### Logical Operations with Arrays
```
import numpy as np

porridge = np.array([79, 65, 50, 63, 56, 90, 85, 98, 79, 51])

cold = porridge[porridge <= 60]

hot = porridge[porridge >= 80]

just_right = porridge[(porridge > 60) & (porridge < 80)]
print(cold, hot, just_right)
```
```
(array([50, 56, 51]), array([90, 85, 98]), array([79, 65, 63, 79]))
```
```
porridge > 60
```
```
[True, True, False, True, False, True, True, True, True, True]
```

### Mean and Logical Operations
```
import numpy as np

class_year = np.array([1967, 1949, 2004, 1997, 1953, 1950, 1958, 1974, 1987, 2006, 2013, 1978, 1951, 1998, 1996, 1952, 2005, 2007, 2003, 1955, 1963, 1978, 2001, 2012, 2014, 1948, 1970, 2011, 1962, 1966, 1978, 1988, 2006, 1971, 1994, 1978, 1977, 1960, 2008, 1965, 1990, 2011, 1962, 1995, 2004, 1991, 1952, 2013, 1983, 1955, 1957, 1947, 1994, 1978, 1957, 2016, 1969, 1996, 1958, 1994, 1958, 2008, 1988, 1977, 1991, 1997, 2009, 1976, 1999, 1975, 1949, 1985, 2001, 1952, 1953, 1949, 2015, 2006, 1996, 2015, 2009, 1949, 2004, 2010, 2011, 2001, 1998, 1967, 1994, 1966, 1994, 1986, 1963, 1954, 1963, 1987, 1992, 2008, 1979, 1987])

millennials = np.mean(class_year > 2005)
print(millennials)
```

### Sorting
```
import numpy as np

temps = np.array([86, 88, 94, 85, 97, 90, 87, 85, 94, 93, 92, 95, 98, 85, 94, 91, 97, 88, 87, 86, 99, 89, 89, 99, 88, 96, 93, 96, 85, 88, 191, 95, 96, 87, 99, 93, 90, 86, 87, 100, 187, 98, 101, 101, 96, 94, 96, 87, 86, 92, 98,94, 98, 90, 99, 96, 99, 86, 97, 98, 86, 90, 86, 94, 91, 88, 196, 195,93, 97, 199, 87, 87, 90, 90, 98, 88, 92, 97, 88, 85, 94, 88, 93, 198, 90, 91, 90, 92, 92])

sorted_temps = np.sort(temps)
print(sorted_temps)
```

### Percentile
```
import numpy as np

patrons = np.array([ 2, 6, 14, 4, 3, 9, 1, 11, 4, 2, 8])

thirtieth_percentile = np.percentile(patrons, 30)

seventieth_percentile = np.percentile(patrons, 70)

print(thirtieth_percentile, seventieth_percentile)
```
```
(3.0, 8.0)
```

### Standard deviation
The larger the standard deviation, the more spread out our data is from the center. The smaller the standard deviation, the more the data is clustered around the mean.

### Histogram
```
# This imports the plotting package.  We only need to do this once.
from matplotlib import pyplot as plt 

# This plots a histogram
plt.hist(data) 
# When we enter plt.hist with no keyword arguments, matplotlib will automatically make a histogram with 10 bins of equal width that span # the entire range of our data.

# This displays the histogram
plt.show()
```
 ### Normal Distribution
 ```
 a = np.random.normal(0, 1, size=100000)
 ```
loc: the mean for the normal distribution
scale: the standard deviation of the distribution
size: the number of random numbers to generate
