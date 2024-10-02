# LARGEST-PRIME-NUMBER
Problem Statement
Given a number 
𝑁
N, find its largest prime factor. For a prime number, the largest prime factor is the number itself.

Input Format
The first line contains an integer 
𝑇
T, representing the number of test cases.
The next 
𝑇
T lines each contain an integer 
𝑁
N, representing the number for which the largest prime factor is to be determined.
Constraints
1
≤
𝑇
≤
1
0
5
1≤T≤10 
5
 
2
≤
𝑁
≤
1
0
12
2≤N≤10 
12
 
Output Format
For each test case, print the largest prime factor of the given number 
𝑁
N.
SOLUTION:
#include <bits/stdc++.h>
using namespace std;

long long FindPrime(long long x)
{    
    for(int i=3; i<=sqrt(x); i+=2)
    {
        if(x % i == 0)
        {            
            x /= i;
            i = 1;
            continue;
        }
    }
    return max(x, (long long)2);
}


int main() 
{
    int t;
    cin >> t;
    
    while(t--)
    {
        long long int n;
        cin >> n;

        while(n >= 1)
        {
            if(n == 1)
            {
                cout << 2 << endl;
                break;
            }
            if(n % 2 == 0)
            {
                n /= 2;
                continue;
            }
            cout << FindPrime(n) << endl;
            break;
        }
    }
    return 0;
}
