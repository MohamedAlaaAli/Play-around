<h1 style="text-align: center; color: black; opacity: 0.90">Fibonacci sequence problem</h1>

<h2 style="color:black; opacity: 0.90">Submitted by <h2>

<ul>
-Mohamed Alaa Ali Mahmoud<br><br>
-SEC2<br><br>
-BN 21 <br><br>
</ul>

<h3 style="color: grey; opacity:0.90;">Statement:<br>In this task, you are required to list as many solutions as possible to the Fibonacci sequence problem. "given an integer n, output the nth Fibonacci number"
Explain the algorithm of each solution mentioning the space and time complexity.<h3>


[![](https://cdn-images-1.medium.com/max/1200/1*bfSmmMFLEaeDEHtQo0Ca_w.jpeg)](https://cdn-images-1.medium.com/max/1200/1*bfSmmMFLEaeDEHtQo0Ca_w.jpeg)

  <p>What is <strong>Fibonacci</strong> Number?
A Fibonacci number is a series of numbers in which each Fibonacci number is obtained by adding the two preceding numbers. It means that the next number in the series is the addition of two previous numbers. Let the first two numbers in the series be taken as 0 and 1. By adding 0 and 1, we get the third number as 1. Then by adding the second and the third number (i.e) 1 and 1, we get the fourth number as 2, and similarly, the process goes on. Thus, we get the Fibonacci series as 0, 1, 1, 2, 3, 5, 8, ……. Hence, the obtained series is called the Fibonacci number series.

We can also obtain the Fibonacci numbers from the pascal’s triangle as shown in the below figure </p>

[![](https://cdn1.byjus.com/wp-content/uploads/2021/03/Fibonacci-Numbers-1.png)](hhttps://cdn1.byjus.com/wp-content/uploads/2021/03/Fibonacci-Numbers-1.pngttp://)


<br><p>Fibonacci Numbers Formula
The sequence of Fibonacci numbers can be defined as:

F<sub>n</sub> = F<sub>n-1</sub> + F<sub>n-2</sub>

Where F<sub>n</sub> is the nth term or number
  


F<sub>n-1</sub> is the (n-1)th term

F<sub>n-2</sub> is the (n-2)th term

From the equation, we can summarize the definition as, the next number in the sequence, is the sum of the previous two numbers present in the sequence, starting from 0 and 1. Let us create a table to find the next term of the Fibonacci sequence, using the formula.<p>[Link to source](https://byjus.com/maths/fibonacci-numbers/ "Link to source")<br>

| F<sub>n-1</sub>  | F<sub>n-2</sub>  |  F<sub>n</sub> |
| :---        |    :----:   |          ---: |
| 0 | 1   | 1   |
| 1 | 1   | 2   |
| 1 | 2   | 3   |
| 2 | 3   | 5   |
| 3 | 5   | 8  |


<br><br><h1>Next is the ***Algorithms***</h1><br>
  The first naive solution to this problem is ***this recursive approach***

$${\color{blue}Python\space\color{blue}implementation}$$
```python
def fib1(n: int):
	#base case
    if n<=1:
        return n
	#Notice here 2 recursive calls
    return fib1(n-1) + fib1(n-2)
```
$${\color{blue}Complexity:\space\color{blue}time\space\color{blue}O(2^{\{n}}),\space\color{blue}Space\space\color{blue}O(n)}$$






This is ***a good*** solution to this problem using ***recursive  approach***

$${\color{blue}Python\space\color{blue}implementation}$$
```python
def fib(n: int,first = 0,second = 1):
	#base cases
	#The first element
    if n-1 == 0:
        return second
	#the zeroth element
    elif n-1 == -1:
        return first
	#anything else
    else:
        next = first + second
        first = second
        return fib(n-1, first, next)
```
$${\color{blue}Complexity:\space\color{blue}time\space\color{blue}O(n),\space\color{blue}Space\space\color{blue}O(n)}$$


<h3>I think we can do better than the first naive solution,</h3>
<h3 style="color: red; opacity:0.90">so what about dynamic programming approach ?</h3>

$${\color{blue}Dyn\color{black}amic\space\color{blue}prog\color{black}ramming}$$
```python
"""memo is a dictionary mapping each fibonacci number to its order or index"""
def fib1(n: int, memo={0:0,1:1,2:1}):
	#if the order is included in the memo find it from there
    if n in memo.keys():
        return memo[n]
	# if not find the nth fibonacci then add it to the memo
    else:
        memo[n] = fib1(n-1, memo) + fib1(n-2, memo)
    return memo[n]
```
$${\color{blue}Complexity:\space\color{blue}time\space\color{blue}O(n),\space\color{blue}Space\space\color{blue}O(n)}$$
	
another loop based solution :
```python
def fib_loop(n:int):
    n1, n2 = 0, 1
    next = 0
	#start from 2 end in n+1 exclusive
    for i in range(2,n+1):
        n1, n2 = n2, n1+n2

    return n2
```

$${\color{blue}Complexity:\space\color{blue}time\space\color{blue}O(n),\space\color{blue}Space\space\color{blue}O(1)}$$

## Are we done right now ? Well, We have not thaught about mathmatics yet !
the golden rectange and the golden ratio :smiling_imp: :


[![](https://th.bing.com/th/id/R.841f98741ca81e159478f0a2286f476e?rik=Od9IP28emNml4g&riu=http%3a%2f%2f4.bp.blogspot.com%2f-TTWog5TwhHg%2fU-SlTLvdxuI%2fAAAAAAAAN9s%2fzh0TSSCU86M%2fs1600%2fPicture2.png&ehk=r0YLCIW3R5dtxg6inv%2fKDc1wAK2IK%2b8A%2bjtywBCP%2bko%3d&risl=&pid=ImgRaw&r=0)](https://th.bing.com/th/id/R.841f98741ca81e159478f0a2286f476e?rik=Od9IP28emNml4g&riu=http%3a%2f%2f4.bp.blogspot.com%2f-TTWog5TwhHg%2fU-SlTLvdxuI%2fAAAAAAAAN9s%2fzh0TSSCU86M%2fs1600%2fPicture2.png&ehk=r0YLCIW3R5dtxg6inv%2fKDc1wAK2IK%2b8A%2bjtywBCP%2bko%3d&risl=&pid=ImgRaw&r=0)
[Reference Link](https://www.mathsisfun.com/numbers/fibonacci-sequence.html "Reference Link")

When we take **any two successive** (one after the other) *Fibonacci* Numbers, their ratio is very close to the Golden Ratio **"φ" which is approximately 1.618034...**
# Formula :
### F<sub>n</sub> = (((√5 + 1)/2) ^ n) / √5F<sub>n</sub> = (((√5 + 1)/2) ^ n) / √5

***Mathmatical approach*** :smirk:

$${\color{blue}Python\space\color{blue}implementation}$$
```python
def fib(n):
	#calculate the golden ratio phi
    phi = (1 + math.sqrt(5)) / 2
	#use the formula for nth fibonacci number
    return round(pow(phi, n) / math.sqrt(5))

```

$${\color{blue}Complexity:\space\color{blue}time\space\color{blue}O(logn),\space\color{blue}Space\space\color{blue}O(1)}$$


# Using **Linear algebra**** :[link1](https://math.stackexchange.com/questions/61997/proof-of-this-result-related-to-fibonacci-numbers-beginpmatrix11-10-end "Reference Link") [link2](https://www.programmersought.com/article/92534124972/ "https://www.programmersought.com/article/92534124972/")

[![](https://th.bing.com/th/id/R.bc3d3581246e7c3616087576441aa157?rik=O%2bZmnTeVBiu%2btA&pid=ImgRaw&r=0)](https://th.bing.com/th/id/R.bc3d3581246e7c3616087576441aa157?rik=O%2bZmnTeVBiu%2btA&pid=ImgRaw&r=0)

$${\color{blue}Diagonalization\space\color{blue}of\space\color{blue}matrix,\space\color{blue}Recurrence\space\color{blue}relation}$$
```python
def fib_matrix(n: int):
	#array initialized
    F = np.array([[1, 1],
                 [1, 0]])
    if n == 0:
        return 1
	#Array diagonalization
    result = np.matmul(F, F)
    for i in range(3,n+1):
        result = np.matmul(result, F)
    return result[0][0]
```

$${\color{blue}Complexity:\space\color{blue}time\space\color{blue}O(n),\space\color{blue}Space\space\color{blue}O(1)}$$
	
| Algorithm  |  time complexity | space complexity  |
| ------------ | ------------ | ------------ |
|  naive recursive approach | O( 2^N )  | O( N )  |
|  modified recursive approach | O(N)  | O(N)  |
|  Dynamic programming | O(N)  | O(N)  |
| Loop based solution  | O(N)  | O(N)  |
|  Golden ratio  | O(log(N))  |  O(1) |
|Linear Algebra| O(N) | O(1)|
