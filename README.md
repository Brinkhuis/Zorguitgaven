# Reproducing a nice plot with ggplot

On [https://www.vtv2018.nl/zorguitgaven](https://www.vtv2018.nl/zorguitgaven) a very nice and colourful visualization was publiced on zorguitgaven (healthcare expenses).

Using the data provided online, I reproduced this visualization with ggplot.  

  
![](http://res.cloudinary.com/brinkhuis/image/upload/v1513194157/zorguitgave_rhocjx.png)


``` r
df = gather(read_csv('zorguitgaven.csv'), Type, Value, 2:5)
df$Type <- as.factor(df$Type)
df$Category <- factor(df$Category, levels = c("0-1", "1-5", "5-10", "10-15", "15-20", "20-25", "25-30", "30-35", "35-40", "40-45", "45-50", "50-55", "55-60", "60-65", "65-70", "70-75", "75-80", "80-85", "85-90", "90-95", "95 en ouder"))
rbind(head(df, 3), tail(df, 3))
```