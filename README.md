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
 
