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
