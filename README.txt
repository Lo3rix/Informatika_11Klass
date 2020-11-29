# Informatika_11Klass
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

Задание 25: (7 Видов)
1.	 Несколько делителей (делитель четный):
a={}

for i in range(95632,95700):
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

for i in range(174457,174506):
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
2. Наибольшим числом, кратным 14 и являющимся произведением двух элементов последовательности с различными номерами.

f=open('E:/27-A_2.txt')

n = int(f.readline())

M14,M7,M2,Max = 0,0,0,0

for i in range(n):
    a = int(f.readline())
    if a % 14 == 0 and a > M14: M14 = a
    if a % 7 == 9 and a % 2 != 2 and a > M7: M7 = a
    if a % 2 == 0 and a % 7 != 0 and a > M2: M2 = a
    if a > Max: Max = a

if M14 * Max > M2 * M7: print (M14 * Max)
else: print (M2 * M7)
