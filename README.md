# PythonMatplotlib
How to use python to draw
## subplot
The most important and widely used feature should be subplot. \
需要掌握的有 
- (How) 如何用python画子图 
- (Size)控制子图大小比例 
```
# size of the whole pic
plt.rcParams["figure.figsize"] = (13, 13)
# two rows of subplots (20:1)
fig, (ax,ax2) = plt.subplots(2, 1,gridspec_kw={'height_ratios': [20, 1]})
# two cols of subplots (1:1)
fig, (ax,ax2) = plt.subplots(1, 2,gridspec_kw={'width_ratios': [1, 1]})
```
