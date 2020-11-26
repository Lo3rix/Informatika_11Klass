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
for y in range (100,999):
    x=y   

L=n   
M=n

функция    

if L == k and M == k:
            
   print (x)

Задание 24: (3 Вида)
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

Задание 25: (2 Вида)
1.	 Несколько делителей (делитель четный):
for i in range(95632,95700):
    b = []
    
    for g in range(1, i + 1):
         
        if i % g == 0 and g % 2 == 0:
             
             b.append(g)
             
             if len(b) == 7:
              
                 break
    
    if len(b) == 6:
            
        print (*b)

2.	Несколько делителей (при этом единица и само число не считается + любой          делитель):
for i in range(174457,174506):
    b = []
    
    for g in range(2, i - 1):
         
        if i % g == 0:
             
             b.append(g)
             
             if len(b) == 3:
              
                 break
    
    if len(b) == 2:
            
        print (*b)

Задание 26: (3 вида) (Обязательно проверять осталось ли свободное   место)
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

2.	 Если остается свободное место (Универсальная)
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
