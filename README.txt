# Informatika_11Klass
Задание 2:
print(' x y z w F')
for x in range(2):
    for y in range(2):
        for w in range(2):
            for z in range(2):
                if ((not x) + y + z) == ((not y) * z * w):
                    print(x,y,z,w, int(((not x) + y + z) == ((not y) * z * w)))
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
3.
f = open()
s = f.readline()
c = ''
m = 0
for i in range(len(s)):
   c += s[i]
   if 'AD' not in C:
     m = max(len(c),m)
   else:
     c = 'D'
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
1.:
for x in range(3500,4000+1):
    b = []
    for g in range(2,int(x**0.5)+1):
        if g * g == x:
          if g % 2 != 0:
              b.append(g)
        elif x % g == 0:
          if g % 2 != 0 :
              b.append(g)
          if (x//g) % 2 != 0:
              b.append(x//g)
          if len(b)>5:
              break
    if len(b)==5:
        print(b, x)
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

4.
def prost(x):
    for i in range(2,x):
        if x % i == 0:
            return True
    return False

def AllDivs(x):
    divs = [1,x]
    for i in range(2, int(x**0.5)+1):
        if x % i == 0:
            if prost(i):
                divs += [i]
            if x // i != i and prost(x//i):
                divs += [x//i]
    divs.sort()
    return divs

for i in range(350000, 350300):
    print(i, AllDivs(i))

5.
def AllDivs(x):
    divs = [1,x]
    for i in range(2, int(x**0.5)+1):
        if x % i == 0:
            divs.append(i)
            if x // i != i:
                divs.append(x//i)
    divs.sort()
    return divs

for x in range(452022, 452065):
    s = AllDivs(x)
    p = s[1]+s[-2]
    if p > x:
        pass
    else:
        k = s[1]+s[-2]
    if k % 7 == 3:
        print(x,k)
6. 
for x in range(100,300+1):
    c = 0
    for d in range(2,x):
        if x % d == 0:
            c += 1
    if c == 0:
        print(x)
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

2.
f = open("E:/27A_11_1.txt")
a = []
n = int(f.readline())
kr34 = 0
kr2 = 0
kr17 = 0
nekr = 0
para = 0
for i in range(5):
    x=int(f.readline())
    a.append(x)
for i in range(n-5):
    if a[0] % 34 == 0:
        kr34+=1
    elif a[0] % 17 == 0:
        kr17+=1
    elif a[0] % 2 == 0:
        kr2+=1
    else:
        nekr += 1
    x=int(f.readline())
    if x % 34 == 0:
        para += (kr2+kr17+kr34+nekr)
    elif x % 2 == 0:
        para += (kr17+kr34)
    elif x % 17 == 0:
        para += (kr2+kr34)
    else:
        para += kr34
    del a[0]
    a.append(x)
print(para)
2.1
f = open("E:/27A_11_1.txt")
n = int(f.readline())
kr6 = 0
kr3 = 0
kr2 = 0
for i in range(n):
   x=int(f.readline())
   if x % 6 == 0:
        kr6+=1
   elif x % 3 == 0:
        kr3+=1
   elif x % 2 == 0:
        kr2+=1
print(kr2*kr3+kr6*(n-kr6)+kr6*(kr6-1)//2)
3.
f = open()
n = int(f.readline())
a = []
for i in range(n):
    a.append(int(f.readline()))
otrezok = 0
for i in range(n-1):
    for j in range(i+1, n):
        if sum(a[i:j+1])%73 == 0:
            otrezok = max(otrezok, sum(a[i:j+1]))
print(otrezok)
