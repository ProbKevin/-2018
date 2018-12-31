# 我的2018
A big year~
由于天气太冷，不想出门，于是躺在床上写点东西，下面有煽情（schmaltzy，对不起最近在精读:relaxed:），有电影，有音乐，有照片，有代码，当然也有数学

## 2018年1月

**这个时代不缺完美的人，缺的是心里给出的真心，正义，无畏和同情**

当时我刚考完试验设计，心理还沉浸在时间紧张把treatment字母打错的遗憾中，然后立马去看《无问西东》，第一部让我看哭的电影，也是这么多年最让我感动的一部电影！从里面我看到了一个大学在每个时代的担当，四个青年在四个时代里毅然决然的选择，他们对于真实、快乐和责任的理解，无问西东，只问绽放。
![](http://n.sinaimg.cn/sinacn/w1366h768/20180117/31c8-fyqtwzu0690536.jpg)

## 2018年3月

**我的第一份实习**

大三下学期刚开始的时候，心里大概是又慌又闲，慌的是研究生上学，闲的是课太少了，那就去实习吧:ok_woman:~于是找到了一份数据分析的实习，工作内容比较自由，大致就是研究一份数据集然后写出文章放到公众号上。真正收获的地方是关于数据可视化的实践，下面是我觉得比较酷的几个

- [How to Calculate the Age of the Universe](https://github.com/zonination/galaxies)

这个图是收集了4240个星系距离地球的距离以及速度，然后用回归的方法估计得到宇宙年龄为13.773 billion years old（普遍接受的数值为13.799）

![](https://upload-images.jianshu.io/upload_images/12117152-3b9bdd76afc12a3e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- [gganimate](https://github.com/thomasp85/gganimate)

*A simple demo*
```r
# install.packages('devtools')
devtools::install_github('thomasp85/gganimate')
library(gapminder)
ggplot(gapminder, aes(gdpPercap, lifeExp, size = pop, colour = country)) +
  geom_point(alpha = 0.7, show.legend = FALSE) +
  scale_colour_manual(values = country_colors) +
  scale_size(range = c(2, 12)) +
  scale_x_log10() +
  facet_wrap(~continent) +
  # Here comes the gganimate specific bits
  labs(title = 'Year: {frame_time}', x = 'GDP per capita', y = 'life expectancy') +
  transition_time(year) +
  ease_aes('linear')
 ```
 ![](https://github.com/thomasp85/gganimate/blob/master/man/figures/README-unnamed-chunk-4-1.gif?raw=true)
 
 - **ggplot2+plotly**
 
 `plotly`是交互式可视化的神器，在R里面与ggplot2搭配的方式更是简洁到了极致，只需`(ggplot())%>%ggplotly`
 
 ```r
library(ggplot2)
library(dplyr)#调用管道函数%>%
library(plotly)
 (ggplot(teamdata,aes(x=TRB,y=FGA))+
  geom_point(aes(color=Year),alpha=0.8)+
  scale_color_hue( h= c(80, 300))+
  geom_smooth(method = 'lm')+
  xlab('Total Rebounds')+
  ylab('Field Goal Attempts')+
  ggtitle('TRB vs FGA')+
  theme_light()+
  theme(plot.title =element_text(hjust = 0.5,face ='bold.italic',size = 12,
                                 color='black'),
        axis.title = element_text(face = 'bold',size=10,color = 'black'),
        axis.text = element_text(face = 'bold',size=9,color='black'),
        legend.title=element_text(size = 10,color='black',face = 'bold',
                                  hjust = 0.5)))%>%
  ggplotly()
 ```
 ![](https://github.com/ProbKevin/-2018/blob/master/plotly.png?raw=true)
 
 ## 2018年5月

 **Sheldon和Amy结婚了**
 
也许我不像很多生活大爆炸粉丝一样是从第一季追到现在，大概我真正的入坑时间是上大学以后吧，当时从第三季开始补一路到第11季。有时候经常自己一个人吃饭，经常看一集TBBT，晚上回到寝室到睡觉的一段时机也是TBBT，大概是把我一天的笑全在睡前哈哈哈哈出来，之后差不多每集看过至少两遍。从第3季23集到第11季24集，Shemy终于结婚了！


 ## 2018年6月
 
 **交大夏令营**
 
当时已经确定了要读博士，只报了交大数院统计直博的夏令营，期间准备了从数分高代概率论数理统计随机过程回归分析多元统计7门课。夏令营期间非常吸引我的一个地方是[自然科学研究院](http://ins.sjtu.edu.cn/)（INS），第一次了解到有这么多激动人心的前沿数学交叉领域（内心非常想去）~

考试除了随机微分方程写了个解字之外，其他东西也有一些平时没有刻意注意的东西：
 
 - 关于矩估计相合性的证明
 
当时考试先是要求一个Gamma分布中参数 $\alpha$与$\beta$ 的矩估计，然后要求证明两个矩估计是相合估计，当时的我是懵逼的:full_moon_with_face:，只想到强行证明$P(\hat \alpha \to\alpha)=1$ or $P(\hat \alpha \to\alpha)\to 1$，失败了:sob:......后来暑假狠狠地把数理统计复习了一遍，除了教材之外又看了陈家鼎的《数理统计讲义》和陈希孺《数理统计学教程》，才真正意识到数理统计的**数理**两个字~复习发现了如下，然后一切都简单了：
* 原点矩与中心距是强相合的
 
* 若$\hat \theta_{n1},...,\hat \theta_{nk}$是$\theta_{n1},...,\theta_{nk}$的相合估计，$\eta=g(\theta_{n1},...,\theta_{nk})$是连续函数，则$\hat \eta_n=g(\hat \theta_{n1},...,\hat \theta_{nk})$是$\eta$的相合估计

- 关于多元正态分布$N(\pmb \mu,\pmb \Sigam)$的$\pmb \mu$和$\pmb \Sigma$的MLE估计的证明

其实上数学分析的时候，老师就会考很多大定理的证明，当时还不是特别理解。后来觉得这些经典的证明确实是需要记住的，和学其他任何东西需要积累一样，学习证明也是需要积累的。有时候觉得这些技巧太神了吧，当积累量多的时候，这些技巧也不再是技巧，而是自己的方法了~
 
## 2018年9月初

**从黑暗爬了出来**

8月底到9月初大概是我大学里面最难熬最挣扎的一段时间了，白天为保研考研做准备，晚上睁眼到两三点才能睡着，甚至有天晚上一个人洗完澡跑到宿舍楼天台吹了半个小时的风，压力大到不想和任何人说话~最终一步步走过来，真的很幸运，只有两个字“感恩！”

## 2018年11月

**开启了毕业论文**

因为要读博，所以想称毕业论文这个机会练一练理论，感谢姚大大给了我一个方向

## 2018年12月

**R会议**

感动和收获都很多，圆了主席梦吧2333




 
