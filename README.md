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

We can also obtain the Fibonacci numbers from the pascal’s triangle as shown in the below figure <p>

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
$${\color{blue}Complexity:\space\color{blue}time\space\color{blue}O(n),\space\color{blue}Space\space\color{blue}O(n)}$$







This is ***a good*** solution to this problem using ***recusion with a recursive  approach***

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

$${\color{blue}Complexity:\space\color{blue}time\space\color{blue}O(n),\space\color{blue}Space\space\color{blue}O(n)}$$
