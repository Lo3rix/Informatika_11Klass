# Informatika_11Klass
Задание 12:
s = '8'*69
while s.find('3333')>-1 or s.find('8888')>-1:
  if s.find('3333')>-1:
    s = s.replace('3333','88',1)
  else:
    s = s.replace('8888','33',1)
print(s)
Задание 14.
n = 16677181742713263
b = '' 
while n > 0:
    b = str(n % 3) + b
    n = n // 3
print(b)
Задание 15. 1)
for A in range(-100,400):
 flag = 0
 for x in range(0,101):
  for y in range(0,101):
   if (функция) or (функция) == False:
    flag = 1
    break
  if flag == 1:
   break
 if flag == 0:
  print(A)
2)
def dell(n,m):
 return n % m == 0
 
for A in range(1,100):
  found = False
  for x in range(1, произведение всех известных чисел +1):
   if not (вся функция, при этом если дано не - это (not функция) импликация - это <=):
    found = True
    break
  if not found:
   print(A)
Задание 16. 
s = 0
def G( n ):
    global s
    s = s + (n+2)
    if n > 1:
        s = s + (n+6)
        G(n-1)
        G(n-2)
for n in range(100):
    s = 0
    G(n)
    if s > 120000:
        break
print(n, s)

def f(n):
    if n <= 15:
        return n*n + 3*n + 9
    if n > 15 and n % 3 == 0:
        return f(n-1) + n-2
    if n > 15 and n % 3 != 0:
        return f(n-2) + n+2
c = 0
for n in range(1,1001):
    x = str(f(n))
    k = 0
    for j in range(0,len(x)):
        if int(x[j]) % 2 == 0:
            k += 1
        if k == len(x):
            c += 1
print(c)
Задание 17:
1.	Кол-во и максимум
k=0
M=1

for i in range(1016,7937+1):
  
 if i % 3 == 0 and i % 7 != 0 and i % 17 != 0 and i % 19 != 0 and i % 27 != 0:    
            
   k+=1
   M=i

print(k,M)

2.	Кол-во и минимум
k=0
M=7937

for i in range(1016,7937+1):
    if i % 3 == 0 and i % 7 != 0 and i % 17 != 0 and i % 19 != 0 and i % 27 != 0:    
        k+=1
         
    if M>i:
        M=i

print(k,M)

Задание 22 (Находим число x)
for x in range(0,400):
    y = x
    a = 0
    b = 1

    while x > 0:
        if x % 2 > 0:
            a += x % 12
        else: 
            b *= x % 12
        x = x // 12
        if a == 5 and b == 16:
            print(y)

Задание 24: (2 Вида)
1.	Cреди которых каждые два соседних различны.
f=open('D:/24.txt')
s=f.readline()
m=1
k=1
for i in range(1,len(s)):    
    if s[i]!=s[i-1]:        
        k+=1       
        m=max(k,m)    
    else:        
         k=1
print(m) 

2.	Последовательность одной буквы
f=open('D:/24.txt')
s=f.readline()
m=0
k=0
for i in range(1,len(s)):    
     if s[i]=="R":        
         k+=1         
         m=max(m, k)    
     else:        
          k=0
print(m)
3.	Нахождение комбинации (с вхождением в слово)
f = open('E:/24-j5.txt')
s = str(f.readline())
f.close()
while 'STOCK' in s:
    t = s.find('STOCK')
    s = s[:t] + '$' + s[t+5:]
c = 0
while 'KTO' in s:
    c += 1
    t = s.find('KTO')
    s = s[:t] + '$' + s[t+3:]
print(c)
4.	Нахождение комбинации (без вхождения в слово)
f = open('E:/24-j5.txt')
s = str(f.readline())
f.close()
c = 0
while 'KTO' in s:
    c += 1
    t = s.find('KTO')
    s = s[:t] + '$' + s[t+3:]
print(c)
5. 
f = open("E:/")
lines = f.readlines()
s = ''
for line in lines:
    if line.count('G') < s.count('G'):
        s = line
a = {}
for i in range(len(s)):
    if s[i] not in a:
        a[s[i]] = 1
    else:
        a[s[i]] += 1
print(a)
Задание 25: (7 Видов)
0.def deliteli_sq(x):
    a = [] # объявление а-ля динамический массив
    for i in range(2,int(x**0.5)+1): #sqrt(x) == x**0.5
        if x%i == 0:
            a.append(i) # добавление в список
            if i != x//i:# ачтобы 2 раза не добавить корень
                a.append(x//i)
    #не сортированный результат
    return sorted(a) #list(set(a))
for i in range(600,141250+1):
    res = deliteli_sq(i)
    if len(res) == 3:
        print(res)
Супер короткий вариант с оптимизацией:
for i in range(19960,20001):
    sqri=int(i**0.5)
    a = []
    for j in range(2,sqri+1):
        if i % j == 0:
            a.append(j)
            if j != i//j:
                a.append(i//j)
    if len(a) == 2:
        print(a)
1.	 Несколько делителей (делитель четный):
a={}

for i in range(95632,95700+1):
    n= 0   
    for g in range(1, i + 1):         
        if i % g == 0 and g % 2 == 0:           
             n += 1             
             if n > 6:              
                 break
             a[n] = g
    if n == 6:   
        print (a[1],a[2],a[3],a[4],a[5],a[6])
2. Несколько делителей (В порядке возрастания)
a = {}
for i in range(489421,489440 + 1):
    n=0
    for g in range(1, i + 1):
        if i % g == 0:
             n += 1
             if n > 4:
                 break
             a[n]=g
    if n == 4:    
        print (a[1],a[2],a[3],a[4])
3.	Несколько делителей (при этом единица и само число не считается + любой делитель):
a={}

for i in range(174457,174506+1):
    n= 0 
    for g in range(2, i - 1):        
        if i % g == 0:             
             n += 1               
             if n > 2:              
                 break
             a[n] = g    
    if n == 2:            
        print (a[1],a[2])
4. Несколько делителей (найти кол-во и минимальное):
min, max = 0,0

for i in range(568023,569230+1):
    n = 0
    for g in range(1,i+1):
        if i % g == 0:
            n += 1
    if n > max:
            max = n
            min = i

print(max,min)
5.	Несколько делителей (делители для каждого числа в порядке возрастания):
a = {}

for i in range(201455,201470+1):
    n = 0
    for g in range(1,i+1):
        if i % g == 0:
            n += 1
            if n <= 4: a[n] = g
            else: break
    if n == 4:
        sorted(a)
        print(a)
6.	Нахождение простых чисел (В порядке возрастания + слева его номер):
a = {}
k = 0
b = False

for i in range(2422000,2422080+1):
    n = 0
    for g in range(2, int(i ** 0.5)):
        if i % g == 0:
            b = False
            break
        else:
            b = True
    if b:
        k += 1
        a[k] = i 
        print(k, a[k])
Задание 26: (2 вида) (Обязательно проверять осталось ли свободное   место)
1.	 Если не остается свободного места
f=open('E:28132.txt')

a=f.readline()
s = int(a.split()[0])
n = int(a.split()[1])

b = []

for i in range(n):
    b.append(int(f.readline()))   

b.sort()

i,c,aMax,sum = 0,0,0,0

while s - b[i] >=0:
    sum += b[i]
    s -= b[i]   
    c += 1
    aMax = b[i]
    i += 1

print(c,aMax,sum)

1.	 Если остается свободное место (Универсальная)
f=open('E:28132.txt')

a=f.readline()
s = int(a.split()[0])
n = int(a.split()[1])

b = []

for i in range(n):
    b.append(int(f.readline()))
    
b.sort()

i,c,aMax,sum,s0,iMax = 0,0,0,0,s,0

while s - b[i] >=0:
    sum += b[i]    
    s -= b[i]       
    c += 1    
    iMax = i
    aMax = b[i]
    i += 1

s = sum - aMax

for i in range(iMax,n):
    
    if s + b[i] <= s0: 
        aMax = b[i]

print(c,aMax,sum)
Задание 27 (4 вида):
1. Сумма всех выбранных чисел не делилась на 3 и при этом была максимально возможной

f=open('E:/27-B_demo.txt')

n = int(f.readline())
s = 0
Min = 100000

for i in range(n):
    a = f.readline()
    x = int(a.split()[0])
    y = int(a.split()[1])
    if x > y:
        s +=x
        if x - y < Min and x - y != 0 and (x-y) % 3 != 0: Min = x - y
    else:
        s +=y
        if y - x < Min and y - x != 0 and (y-x) % 3 != 0: Min = y - x

if s % 3 != 0: print (s)
else: print (s - Min)
2. 
f = open("E:/27-29b.txt")
n = int(f.readline())
s = 0
m=100000000000
for i in range(n):
    x,y,z = map(int,f.readline().split())
    kz = [x,y,z]
    kz.sort()
    s += kz[2]
    if (kz[2] - kz[1]) % 5 != 0 and (kz[2]-kz[1]) <m:
        m = kz[2] - kz[1]
    if (kz[2] - kz[0]) % 5 != 0 and (kz[2]-kz[0]) <m:
        m = kz[2] - kz[0]

if(s%5!=0):
    print(s)
else:
    print(s-m)
