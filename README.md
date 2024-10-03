# Multiples-of-3-and-5
Problem Statement
You are given several test cases. For each test case, you are required to find the sum of all the multiples of 3 or 5 below a given number 
𝑁
N. The task is to compute this sum for each test case.

Input Format
The first line contains an integer 
𝑇
T, denoting the number of test cases.
The next 
𝑇
T lines each contain an integer 
𝑁
N, representing the upper limit (exclusive) for that test case.
Output Format
For each test case, output a single integer which is the sum of all multiples of 3 or 5 below 
𝑁
N.

Constraints
1
≤
𝑇
≤
1000
1≤T≤1000
1
≤
𝑁
≤
1
0
9
1≤N≤10 
9
 
Example
Input:
Copy code
2
10
100
Output:
yaml
Copy code
23
2318
Explanation:
For 
𝑁
=
10
N=10:

The multiples of 3 or 5 below 10 are: 
3
,
5
,
6
,
9
3,5,6,9.
Their sum is 
3
+
5
+
6
+
9
=
23
3+5+6+9=23.
For 
𝑁
=
100
N=100:

The multiples of 3 or 5 below 100 are: 
3
,
5
,
6
,
9
,
10
,
12
,
15
,
18
,
20
,
21
,
24
,
25
,
27
,
30
,
33
,
35
,
36
,
39
,
40
,
42
,
45
,
48
,
50
,
51
,
54
,
55
,
57
,
60
,
63
,
65
,
66
,
69
,
70
,
72
,
75
,
78
,
80
,
81
,
84
,
85
,
87
,
90
,
93
,
95
,
99
3,5,6,9,10,12,15,18,20,21,24,25,27,30,33,35,36,39,40,42,45,48,50,51,54,55,57,60,63,65,66,69,70,72,75,78,80,81,84,85,87,90,93,95,99.
Their sum is 
2318
2318.
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Solution
import sys


def t(n):
   
    return n * (n + 1) // 2


def sum_3_5(n):
    
    return 3 * t(n // 3) + 5 * t(n // 5) - 15 * t(n // 15)


if len(sys.argv) > 1:
    for i in sys.argv[1:]:
        print(i, sum_3_5(int(i) - 1))
else:
    nb = int(input().strip())
    for _ in range(nb):
        n = int(input().strip())
        print(sum_3_5(n - 1))
