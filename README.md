# ProjectEuler

I've put video descriptions for every problem too!

## [Euler 1](https://www.youtube.com/watch?v=itbnUmNY2Y4)
```python
def euler1(fin):
    biggest3 = (fin-1)//3
    biggest5 = (fin-1)//5
    biggest3in5s = biggest5//3
    result = 3 * (((biggest3+1)*biggest3)//2) + 5 * ( ((biggest5 +1)*biggest5)//2 - 3 * (biggest3in5s * (biggest3in5s+1)//2))
    return result
```


## [Euler 2](https://youtu.be/LgQKStFcPC4)

```python
def euler2(lim):
    even_sum, i, j = 0, 1, 2
    while j <= lim:
        if j&1 != 1:
            even_sum+=j
        j, i = i+j, j
    return even_sum
```

## [Euler 3](https://youtu.be/w3FNOlsoFlM)

```python 
def euler3(n):
    primes = [2]
    maxim, i = 1, 2
    while i < n:
        if all(i%p != 0  for p in primes):
            primes.append(i)
            if n%i ==0:
                maxim = i
                n//=i
                while n%i ==0:
                    maxim = i
                    n//=i
        i+=1
    return max(maxim, n)
```

## [Euler 4](https://youtu.be/xzM1Hbn6kno)
```python
def euler4(x, y):
    largest = 0
    for i in range(y, x-1, -1):
        for j in range(y, x-1, -1):
            p = i*j
            if p < largest:
                break
            s = str(p)
            if s[:len(s)//2] == s[-1:-1-len(s)//2:-1]:
                largest = p
    return largest
```



## [Euler 5](https://www.youtube.com/watch?v=MlucEbNI2jk)
```python
from math import gcd
def euler5(lim):
    return reduce(lambda x,y: x*y//gcd(x,y),range(2,lim),lim)
```

## [Euler 6](https://youtu.be/542cBTbxrsI)
```python
def euler6(n):
    return ((n*(n+1))//2)**2 - (n*(2*n+1)*(n+1))//6
```

## [Euler 7](https://youtu.be/FheegdrweTA)
```python
def euler7(n):
    primes = [2]
    curr = 3
    while len(primes) < n:
        if all(curr % p != 0  for p in primes):
            primes.append(curr)            
        curr +=1
    return primes[-1]
```

## Euler 8
```python
def euler8(s,n):
    nz = sum(c == '0' for c in s[:n])
    cprod = maxp = reduce(lambda x,y:max(1,x)*max(1,y), [int(x) for x in s[:n]] , 1)
    for i in range(n, len(s)):
        if s[i-n] == '0':
            nz-=1
        else:
            cprod //= int(s[i-n])
        if s[i] == '0':
            nz+=1
        else:
            cprod *= int(s[i])
        if nz == 0:
            maxp = max(maxp, cprod)
    return maxp
```
