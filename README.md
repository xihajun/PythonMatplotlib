# Python Visualisation
How to use python to draw: `matplotlib`, `sns`, `plotly`
## subplot
The most important and widely used feature should be subplot. \
需要掌握的有 
- (How) 如何用python画子图 
- (Size) 控制子图大小比例 
```
# size of the whole pic
plt.rcParams["figure.figsize"] = (13, 13)
# two rows of subplots (20:1)
fig, (ax,ax2) = plt.subplots(2, 1,gridspec_kw={'height_ratios': [20, 1]})
# two cols of subplots (1:1)
fig, (ax,ax2) = plt.subplots(1, 2,gridspec_kw={'width_ratios': [1, 1]})
```
## zoom

```
fig, (ax,ax2) = plt.subplots(2, 1,gridspec_kw={'height_ratios': [20, 1]})

# 可以储存label，legend可以用到
dots1 = []
for i in yourlist:
    if i != -1:
        dots1.append(ax.scatter(x, y, label=i))

# (x,y)起始点，(w,h)长宽比例：分别为 (1.1, -0.1) 、 (0.3, 1)
ax1 = ax.inset_axes([1.1, -0.1,0.3, 1])

dots1 = []
for i in yourlist:
    if i != -1:
        dots1.append(ax1.scatter(x, y, label=i))

# 选择x,y范围
ax1.set_xlim(start-2000, start+2000)
ax1.set_ylim(0,max_v)
# 不显示 x, y 轴
ax1.get_xaxis().set_visible(False)
ax1.get_yaxis().set_visible(False)
# 图片标题
ax1.set_title('zoom in - windows 2000')
ax1.legend(dots1[1:2],['第1个label','第2个label'])
ax.indicate_inset_zoom(ax1)
ax.set_ylabel('filename',fontsize =20)

ax2.hist(x,y)
# 让ax2和ax拥有一样的横坐标范围，方便对比
plt.setp(ax2, xlim =ax.get_xlim(), ylim=ax.get_ylim())

```

## circos 和弦图
参考：https://zhuanlan.zhihu.com/p/56744904
## 打断坐标
需要安装一个包\
参考：https://blog.csdn.net/maryyu8873/article/details/84313423

## sns 
- linear plot: https://seaborn.pydata.org/generated/seaborn.regplot.html
    - `lmplot` or `regplot`
- violin plot
    - sns: https://seaborn.pydata.org/generated/seaborn.violinplot.html
    - https://mode.com/blog/violin-plot-examples/
- Raincloud plot
    - url: https://www.marsja.se/python-data-visualization-techniques-you-should-learn-seaborn/
    - `import ptitprince as pt` `pt.RainCloud(x = 'Species', y = 'Sepal.Length', data = df) `
    - `pointplot = True`
    
## plotly
- violin: https://plotly.com/python/violin/
    - Ridgeline
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
