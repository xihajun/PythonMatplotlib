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


## output
写paper的话需要输出svg文件，如何进行输出呢？
```
# example
# 防止名字重复
if self.outdir != False:
    savefilename = self.outdir+gene_name+'_'+str(self.win)
    while(os.path.isfile(savefilename+".svg")):
        savefilename = savefilename +'-'
    print("Save to"+ savefilename+".svg")
    
    # bbox_inches='tight'防止输出不全
    fig.savefig(savefilename+".svg", format="svg", bbox_inches='tight')
```
