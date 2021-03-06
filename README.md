# tigju-lambdata

## Installation

```
# with pip
pip install -i https://test.pypi.org/simple/ tigju-lambdata
```

## Usage

```py
from tigju_lambdata import my_func

x = 5

print(my_func.enlarge(x))

df = pd.DataFrame({'a': [2, 4, None, None], 
                   'b': [4, None, 4, 5], 
                   'c': ['Cat', 'Dog', 'bird', 'fish'], 
                   'd': [3, 4, 5, 6], 
                   'e': [10, 56, 89, 67]})

# check the null values in dataframe
print(my_func.check_null(df))

# train/val/test split (splits 0.2/0.8)
train, val, test = my_func.train_val_test_split(df)

# print out confusion matrix
y_true = pd.DataFrame({"column": ['cat', 'dog', 'cat', 'cat', 'dog', 'cat']})
y_pred = pd.DataFrame({"column": ['cat', 'dog', 'dog', 'cat', 'cat', 'cat']})

print(my_func.cm(y_true, y_pred))

# split date into day/month/year and add columns to dataframe
df = pd.DataFrame({'firsname': ['Anna', 'Peter'], 
                   'lastname':['Smith', 'Peterson'], 
                   'DOB': ['10-12-1988', '01-03-2000']})
                   
print(my_func.date_split(df, 'DOB'))

##############################################################################

from tigju_lambdata.oop import ConfusionMatrix

y_true = pd.DataFrame({"column": ['cat', 'dog', 'cat', 'cat', 'dog', 'cat']})
y_pred = pd.DataFrame({"column": ['cat', 'dog', 'dog', 'cat', 'cat', 'cat']})

cm1 = ConfusionMatrix(y_true, y_pred, "Dogs and Cats", (6,4))

    print(cm1.x_axis)
    print(cm1.y_axis) 
    print(cm1.title)
    print(cm1.size) 
    print(cm1.color) 
    print(cm1.format_cm)
    print(cm1.cm())
    print(cm1.labels())
    print(cm1.make_df())
    print(cm1.plot_cm())
```
Examples are on colab notebook
https://colab.research.google.com/drive/1h2wSVxyiqFcr4XY_MFldS21A7blvlgLY?usp=sharing