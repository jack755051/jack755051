# 演算法第一週

網址：

## Matchmacker
given N men and n women , find a suitable matching.
- each companion have two gender
- input:
![](https://i.imgur.com/JaWBrNN.png)


> The Stable Match Problem
> - perfect match => everyone is matched monogamously
> - stability=>用unstable 反向證明，Unstable pair(M,W)could each improve by eloping.

>###### <font color="#ff0">stable matching : Perfect matching without unstable pair</font>

### Random matching and fixing up

>Simple-But-invalid
1.start matching
2.while do
3.swap
    
### Propose & Reject (2012 Noble Prize in Econ)

>Status of each person:free~<font color="#f00">engaged</font>~married
>
> - Deferred decision making
>###### every step:男生對女生propose

> <font color="#f00">Gale-Shapley</font>
> ![](https://i.imgur.com/Xp1g0rd.png)

>男生有propose權利 / 女生有acess | reject 權利
