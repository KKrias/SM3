# SM3
## 概述:
  对长度为l(l < 2^64) 比特的消息m，SM3杂凑算法经过填充和迭代压缩，生成杂凑值，杂凑值长度为256比特。  
## 填充:  
  填充后的消息m′ 的比特长度为512的倍数。  
## 迭代压缩  
### 迭代过程
  将填充后的消息m′按512比特进行分组：m′ = B(0)B(1)...B(n−1)  
  其中n=(l+k+65)/512。 
  对m′按下列方式迭代： 
  for i=0 to n-1:  
    V(i+1)=CF(V(i),B(i))  
  V(0)为256bit初始值IV  
### 消息扩展  
![image](https://user-images.githubusercontent.com/105533242/181223460-b93bb51f-fc59-43e5-b4ed-23bbf1386afb.png)
### 压缩函数
![image](https://user-images.githubusercontent.com/105533242/181223608-bde414e0-69f7-45e3-8820-6d5c51cec5a9.png)
## 杂凑值
  ABCDEFGH <- V(n)  
  输出256比特的杂凑值y = ABCDEFGH。
## 项目代码说明
def zero_fill(a,n): #不够位数的在前面补零  
def cycle_shift_left( B, n): #循环左移  
def T(j):    #加密部件  
def FF(X,Y,Z,j):  
def GG(X,Y,Z,j):  
def P0(x):  
def P1(x):  
def Message_extension(a):  #a的数一定要满足512bit,不够要补零!!  ,承接的是字符串  
def CF(V,Bi):  #V是字符串  
def SM3(plaintext):#加密函数    
## 实验结果
![image](https://user-images.githubusercontent.com/105533242/181225201-82298f9a-57e8-481f-860d-3177c67ff171.png)
![image](https://user-images.githubusercontent.com/105533242/181225299-e20ff513-43d4-4b2e-96be-fc55ccef224a.png)
