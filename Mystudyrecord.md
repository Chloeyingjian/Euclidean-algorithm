# Euclidean-algorithm
x=eval(input('number1'))
y=eval(input('number2'))
if x<y:
    x,y = y,x
while x%y!=0:
    r=x%y
    x=y
    y=r
print(y)

#count how many ways
i,j,k=0,0,0
t=0
for i in range(21):
    for j in range(51):
        k=100-i*5-j*2
        if k>=0:
            t+=1
print(t)


#Fibonacci number f(n)=f(n-1)+f(n-2)
def Fib(n):
    a=0,b=1 #a,b=0,1
    count=1
    while count<n:
        a,b=b,a+b
        count+=1
        print(a)
        
def Fib(n):
    if n==0 or n==1:
        return(n) #exit
    else:
        return Fib(n-1)+Fib(n-2)

#Filename: Hanoi
def hanoi(a,b,c,n): #把n个 从a经过b移到c
    if n==1:
        print(a,'->',c)
    else:
        hanoi(a,c,b,n-1) #把n-1个 从a经过c移到b
        print(a,'->',c)  #上一步完成后，把最底下那一个移到c或写作hanoi(a,c,1)
        hanoi(b,a,c,n-1) #把n-1个 从b经过a移到c
hanoi('a','b','c',4)

#全局变量
def f(x):
    global a #是全局变量，出来以后是修改后值，5
    print(a)
    a=5
    print(a+x)
a=3
f(8)
print(a)

#change the position
import os
os.getcwd()  #回到当前位置
path='/Users/apple/downloads'
os.chdir(path)
os.getcwd() #在Python shell里要一行一行地，先打开文件）
'/Users/apple/downloads'
os.rename('Simon-vs.-the-Homo-Sapiens-Agen-Albertalli_-Becky.txt','Simon-love.txt')
os.remove('test1.text')

#random函数
import random
random.choice(['C++','Java','python'])
random.randint(1,100)

#datetime函数
from datetime import date
date.today()
from datetime import time
tm=time(10,38,22) #设定时间
print(tm)
from datetime import datetime 
dt=datetime.now  #当下的日期+时间
print=(dt.strftime('%a,%b,%d,%Y,%H,%M') #打印
dt=datetime(2017,6,6,23,29) #计算机新纪元时间1970.1.1.0
print(dt) 
ts=dt.timestamp()          #timestamp把时间转换成时间戳
ts
print(datatime.fromtimestamp(ts))#fromtimestamp把时间戳转换成本地时间

#Try except处理异常
try:
    num1=int(input('Enter the first number'))
    num2=int(input('Enter the second number'))
    print(num1/num2)
except ZeroDivisionError as err:
    print('The second number cannot be zero')
    print(err)
#处理多种异常
try:
    num1=int(input('Enter the first number'))
    num2=int(input('Enter the second number'))
    print(num1/num2)
except Exception as err: #Exception 表示是异常的类型 
    print('Something went wrong')
    print(err) #err 输出异常的原因
else:
    print('Aha,everything is ok.')
While True: #可以多次输入
    try:
        num1=int(input('number1'))
        num2=int(input('number2'))
        print(num1/num2)
        break #位置视情况而定
    except ValueError:
        print('please input a digit')
    except ZeroDivisionError:
        print('The second number cannot be zero')
        
#with语句
with open('data.txt')as f:
    for line in f:
        print(line,end='')
        
#寻找亲密对数
def fac(n):
    for A in range(2, n):
        B = 0
        b = 0
        for j in range(1, A):  # 算出A的因子和B
            if A % j == 0:
                B += j         # B可能大于A
        for j in range(1, B):  # 算出B的因子和b
            if B % j == 0:
                b += j
        if b == A and A<=B:  # 如果a的因子和b等于i就说明找到了一对亲密数对，如何保证不重复，不漏解？
            print("{}-{}".format(A, B))
n = int(input())
fac(n)

def fac(n):
    for A in range(2, n):
        B = 0
        b = 0
        for j in range(1, A):  # 算出A的因子和B
            if A % j == 0:
                B += j
        if B<=A:              
            continue           # 避免重复计算
        for j in range(1, B):  # 算出B的因子和b
            if B % j == 0:
                b += j
        if b == A:  # 如果a的因子和b等于i就说明找到了一对亲密数对，如何保证不重复，不漏解？
            print("{}-{}".format(A, B))
n = int(input())
fac(n)
