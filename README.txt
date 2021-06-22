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
3)Отрезки:
p1, p2, q1, q2 = 8, 16, 25, 40

P = [i / 10 for i in range(p1 * 10, p2 * 10 +1)]
Q = [i / 10 for i in range(q1 * 10, q2 * 10 +1)]

def f(x,A):
    return ((x in P) + (x in Q)) <= (x in A)

Если мин:
A = set ()
for x in [i / 10 for i in range(10, 401)]:
    if not f(x,A):
        A.add(x)
Если макс:
A = set ([i / 10 for i in range(10, 201)])
for x in [i / 10 for i in range(10, 201)]:
    if not f(x,A):
        A.remove(x)

print(sorted(A))

Тождественно:
import itertools

def f(x,y,A):
    return ((x in A) <= (x * x <= 81)) * ((y * y <= 36) <= (y in A))

A = set(range(-100, 100))
for x, y in itertools.product(range(-100,100), repeat=2):
    if not f(x,y,A):
        A.remove(x)

print(sorted(A))
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
0.
def AllDivs(x):
    divs = [1,x]
    for d in range(2, int(x**0.5)+1):
        if x % d == 0:
            divs += [d]
            if x // d != d:
                divs += [x//d]
    divs.sort()
    return divs

for i in range(20, 30):
    print(i, AllDivs(i))
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
2. Несколько делителей (найти кол-во и минимальное):
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
3.	Нахождение простых чисел (В порядке возрастания + слева его номер):
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
Задание 26: 
f = open
n = int(f.readline())
a = [int(f.readline)) for i in range(n)]
print(a[2: 5])
Задание 27:
1. 
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
