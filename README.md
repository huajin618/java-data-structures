# java-data-structures
### 使用欧几里得算法求最大公约数
```
public class GCD{
public static int gcd(int m,int n){
  if(m%n==0)
    return n;
  else
    return gcd(n,m%n);
}

public static void main(String[] args){
Scanner input=new Scanner(System.in);
System.out.print("Enter first interger);
int m=input.nextInt();

System.out.println("The greatest common divisor for"+m+"and"+n+"is"+gcd(m,n);

}
```

欧几里得算法是求两个数的最大公约数(Greatest Common Divisor (GCD))的算法，我们首先假设有两个数 a 和 b，其中 a 是不小于 b 的数，

记 a 被 b 除的余数为 r，那么 a 可以写成这样的形式：

其中 q 是整数（我们不需要去管 q 到底是多少，这和我们的目标无关）。

现在假设 a 和 b 的一个约数为 u，那么 a 和 b 都能被 u 整除，即


s 和 t 都是整数（同样的，我们只需要知道存在这样的整数 s 和 t 就行）。

这样可以得出

 
所以 r 也能被 u 整除，一般规律如下

a 和 b 的约数也整除它们的余数 r，所以 a 和 b 的任一约数同时也是 b 和 r 的约数。  —— 条件一

反过来可以得出

b 和 r 的任一约数同时也是 a 和 b 的约数。  ——条件二

这是因为对 b 和 r 每一个约数 v，有



于是有

由条件一和条件二可知

 a 和 b 的约数的集合，全等于 b 和 r 的约数的集合。

于是

a 和 b 的最大公约数，就是 b 和 r 的最大公约数。

接下来用递推法，

a ÷ b 余 r，现在设

b ÷ r 余 r1

r ÷ r1 余 r2

……

r(n-3) ÷ r(n-2) 余 r(n-1)

r(n-2) ÷ r(n-1) 余 r(n)=0

因为 a>=b，可以看出余数 r(n) 会越来越小，最终变成 0.
当 r(n-1)≠0 且 r(n) = 0 时，可知 r(n-2) 可被 r(n-1) 整除（余数为0嘛）

此时 r(n-2) 和 r(n-1) 的约数就只有：r(n-1) 和 r(n-1) 的因数，所以他们的最大公约数就是 r(n-1)！

所以 r(n-1) 就是 a 和 b 的最大公约数。（若 r = 0，则 b 为最大公约数）
