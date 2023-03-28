## working with notebooks
I have always found it easier to code in jupyter notebooks. I really like having my data loaded into memory and debugging or testing code very quickly. It is easy to hop between ideas. It is especially helpful when making plots or other task when you need to adjust how something looks.

There are a couple of downsides however. Code can get very messy. Code blocks can get disconnected and end up in the wrong order. In order to use code from one notebook in another you end up copying and pasting regularly. Which means if you ever change how you want a function to work you need to change every single copy of the function.

**advantages**
- skip data loading when writing and when testing functions
- can test and move around several ideas quickly
- can adjust and adapt code easily e.g. making plots 
**disadvantages**
- code can get messy. useful funcitons interspersed with random testing lines.
- code can get out of order. need to run a cell below to run cell above.
- end up copying a pasting code from cell to cell, from notebook to notebook.

### Tips
- delete temporry lines regularly.
- add titles and descriptions -> navigation e.g. import packages
- if you find yourself copying code more than once or twice or find yourself changing a variable -> make it a function.
- move large functions or frequently used code snippets to source code.
- make new notebooks for new ideas or tasks. 
- date your notebooks/write a summary at the top of a notebook with hwat it contains so you don't have to read the full thing when you come back to it in 3 months/a year.


## Importing code

Perhaps one of pythons most important features is the ability to import functions from other peoples code. You might be familiar with packages like [numpy](https://numpy.org/) or [pandas](https://pandas.pydata.org/docs/reference/index.html). 

There are three ways to import packages (collections of functions) or code from packages
1. import the package itself

```Python
import numpy
A = numpy.array([1,2,3,4,5])
print(numpy.mean(A))
```
2. import an individual function or functions

```Python
from numpy import array, mean
A = array([1,2,3,4,5])
print(mean(A))
```

3. import and rename a package

```Python
import numpy as np
A = np.array([1,2,3,4,5])
print(np.mean(A))
```


Here is a list of some of the packages I have found incredibly useful and use most commonly in my work.
- core
	- numpy
	- pandas
	- matplotlib
- general scientific/stats functions + machine learningn (not deep)
	- scipy
	- scikit-learn (sklearn)
- networks
	- networkx (commonly used but personally find it the weakest network python package)
	- igraph
	- graph-tool
- machine learning
	- torch
	- pytorch-geometric (graph learning)
- plotting
	- seaborn
	- plotly
- tqdm - progress bar
- click - command line arguments (way better than argparse)

Now packages are fantastic for using other peoples code or using software people have developed to solve particular problems. But what about your own code. How can you make use of code you  previously used. The answer: `.py` files

## relative imports

imagine a folder structure like this
```
└── project
    ├── source1
    │   ├── mycode1.py
    │   ├── mycode2.py
	│   └── mynotebook.ipynb
	├── mycode3.py
	└── mycode4.py
```

and that you are coding in mynotebook.ipynb
When you try to import a package like shown above python has a sequence it follows. First it looks in your current directory for 
```python
from .mycode1 import function1
from ..mycode3 import function2
```

**NOTE: Currently unfinished**