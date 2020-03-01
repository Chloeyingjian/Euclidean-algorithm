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
