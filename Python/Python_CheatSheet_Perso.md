# Fundamentals

### One line if statement
```python
expression_if_true if condition else expression_if_false #OR
if condition: statement
```

### Transform int to string
```python
str(nbr)
```

## List 

### Create list empty
```python
l = [None] * 10
```

### Reverse axis
```python
array[::-1]
```

### Count occurrences of elements in list
```python
import collections

c = collections.Counter( list )
c.most_common(3)                # three most common elements
sorted(c)                       # list all unique elements
c['a']                          # count of letter 'a'
del c['b']                      # remove all 'b'

d = Counter('simsalabim')       # make another counter
c.update(d)                     # add in the second counter
```

### Get the value and the index in the same way
```python
for i, value in enumerate(list):
	# code...
```

## Scripts

### Load main mode in script
```python
def main():
	# code...

if __name__ == '__main__':
	main()
```

### Parse command line arguments
```python
import optparse

op = optparse.OptionParser()
op.add_option("--report",
              action="store_true", dest="print_report", help="Print")
op.add_option("--chi2_select",
              action="store", type="int", dest="select_chi2", help="Sq")
(opts, args) = op.parse_args()
if len(args) > 0:
    op.error("this script takes no arguments.")
if opts.print_report:
    print("classification report:")
```

### Remove warnings (useful in notebook)
```python
import warnings
warnings.filterwarnings('ignore')
```

## Object

### Print
Add those functions in the object declaration
```python
# Converting the object in string or in print function
def __str__(self):
    return ('My print %s' % (self.ma_var))

# Representation of the object: (when $>obj and <enter>)
def __repr__(self):
    return ('My print %s' % (self.ma_var))
```

### Iterable
An iterable is an object that has an __iter__ method which returns an iterator, or which defines a __getitem__ method that can take sequential indexes starting from zero (and raises an IndexError when the indexes are no longer valid). So an iterable is an object that you can get an iterator from.

#### Access like an array
```python
#obj[0], obj[1]... OR
# for r in line:
#    print(r)
def __getitem__(self, key):
    if ( key == 0 ):
        return self.rho
    elif ( key == 1 ):
        return self.theta
    else:
        raise IndexError
```

#### Iterate over an object
Object should never return itself as iterator (break with double nested loop).
```python
# inside the object
def __iter__(self):
    iter([self.rho, self.theta])
```

----
# Numpy 

### Count occurrences of values in array
```python
unique, count = np.unique( array, return_counts=True )
dict( zip( unique, count ) )
```

### Creating a vector column from an array
```python
arr.reshape( -1, 1 ) # Use -1 for auto
```

### Do a grid
```python
# With x and y (arrays)
X, Y = np.meshgrid(x, y)
```

### Get a log range
```python
np.logspace( power_min, power_max, inter)
```

### Matrix multiplication
```python
np.dot(X, X2)
```

### Shuffle array
```python
inds = np.random.shuffle(inds)
array = array[inds] 
```

### Logical operation
```python
np.logical_...
```

### Concatenate
```python
np.c_[ arr1, arr2... ] # (col)
np.r_[ arr1, arr2... ] # (row)
```

-----
# Panda 

## Get info

### Get the unique values 
```python
df["col"].unique()
```

### Get the number of times the unique values appear
```python
df["col"].value_counts()
```

### Descriptive statistics summary
```python
df['var'].describe()
```

### Get correlation matrix from DataFrame
```python
corr = DataFrame.corr()
```

## Access

###  Extract a NumPy array
```python
dataFrame.values
```

###  Access columns
```python
df.columns
```

## Modification

###  Split data in different cases
```python
get_dummies
```

###  Change type
```python
DataFrame.astype( type )
```

###  Rename column
```python
df.rename(columns={'two':'new_name'}, inplace=True)
```

###  Remove rows
```python
df.drop(df.index[[2,3]])
```

###  Remove with conditions
```python
df.loc[df["tt"] > 5 | df["tt"] < 6]
```

----
# Matplotlib

## Figures

### Change size
```python
plt.figure(figsize=(20,10)) # OR
fig, ax = plt.subplots(figsize=(20, 10))
```

### Remove axes
```python
plt.axis('off') # OR
fig, ax = plt.subplots()
ax.get_xaxis().set_visible(False)
ax.get_yaxis().set_visible(False)
```

## Plots

### With log scale
```python
plt.semilogx(x, y)
plt.semilogy(x, y)
plt.loglog(x, y)
#-- OR -- 
plt.yscale('log')
plt.xscale('log')
```

----
# Jupyter

## History
```python
%hist or %history
Print the numbers: -n
```

## Write lines of code in the terminal
```python
%load 7-27 			# Lines from the history
%load -r 10-20,30,40: foo.py 	# From a file
```

## Save codes in a file 
```python
%save -a file codes
# -a is used to append the codes at the end of the file else the file is overwritten
```
