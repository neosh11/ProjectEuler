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
