# 360��˾2018У԰��Ƹ�㷨������

<!-- TOC -->
* [��һ��](#��һ��)
* [�ڶ���](#�ڶ���)
* [������](#������)
<!-- TOC -->


## ��һ��

### ��Ŀ����
>��һ��������Ҫ�޽�������N����ӵ�����X,Y���ʰ���ô�����ȫ���������еĻ�������������С����Ƕ��٣�ע�⣬����Ϊƽ����������������Σ�

**��������:**
>��һ��ΪN����ʾ�����Ŀ��2��N��1000��
����ΪN�У�ÿ����������Xi��Yi����ʾ�þ�������꣨-1e9��xi,yi��1e9��


**�������:**
>����������С���

**������**
```
����
2
0 0
2 2

���
4

��������2
2
0 0
0 3
�������2
9
```

### �ο�����
```java
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int N = in.nextInt();
        int[][] loc = new int[N][2];
        for(int i=0;i<N;i++){
            loc[i][0]=in.nextInt();
            loc[i][1]=in.nextInt();
        }
        long min = 0;
        long min_x = loc[0][0];
        long max_x = loc[0][0];
        long min_y = loc[0][1];
        long max_y = loc[0][1];
        for(int i = 1; i < N; ++i) {
            if(min_x > loc[i][0])
                min_x = loc[i][0];
            if(max_x < loc[i][0])
                max_x = loc[i][0];
            if(min_y > loc[i][1])
                min_y = loc[i][1];
            if(max_y < loc[i][1])
                max_y = loc[i][1];
        }
        min = (max_y-min_y)>(max_x-min_x)?(max_y-min_y)*(max_y-min_y):(max_x-min_x)*(max_x-min_x);
        System.out.println(min);
    }
}
```

## �ڶ���

### ��Ŀ����
>С����һ����԰����԰����һ����m�仨������ÿһ�仨�����ǲ�һ���ģ�С����1��m�е�һ��������ʾÿһ�仨��
����ϲ��ȥ����Щ������һ��������n�Σ�����n����������������ʲô����ʱ��˳���¼������
��¼��a[i]��ʾ����ʾ��i��������a[i]��仨��
С��ܺ��棬����Q������,��[l,r]��ʱ���ڣ�С��һ�����˶��ٶ䲻ͬ�Ļ�����С����Ϊ��æ���������Ļ�������������������ش���Щ���⡣

**��������:**
>����������n,m;(1<=n<=2000,1<=m<=100);�ֱ��ʾn�ο�����m��ʾһ����m�仨����
����������n����a[1]~a[n]��a[i]��ʾ��i�Σ�С�����Ļ�������;
����һ����Q(1<=Q<=1000000);��ʾС�������������
����Q�� ÿ�������� l,r(1<=l<=r<=n); ��ʾС����֪���ڵ�l�ε���r�Σ�С��һ�����˶��ٲ�ͬ�Ļ�����


**�������:**
>һ��Q��
ÿһ�����һ���� ��ʾС����[l,r]��ʱ���ڿ��˶����ֻ���

**������**
```
����
5 3
1 2 3 2 2
3
1 4
2 4
1 5
���
3
2
3
```

### �ο�����
```java
import java.util.HashSet;
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int n = in.nextInt();
        int m = in.nextInt();
        int[] look = new int[n];
        for(int i=0;i<n;i++){
            look[i]=in.nextInt();
        }
        int k = in.nextInt();
        int[][] interval = new int[k][2];
        for(int i=0;i<k;i++){
            interval[i][0]=in.nextInt();
            interval[i][1]=in.nextInt();
        }
        for(int i=0;i<k;i++){
            HashSet<Integer> count = new HashSet<>();
            for(int j=interval[i][0]-1;j<=interval[i][1]-1;j++){
                count.add(look[j]);
            }
            System.out.println(count.size());
        }
    }
}

```

## ������

### ��Ŀ����
>С������������Ϊn������A��B��ÿ��������[1,n]����ɣ�����������ֶ��ǲ�ͬ�ġ�
����Ҫ�ҵ�һ���µ�����C��Ҫ���������������������λ��(i,j)����:
�����A������C[i]�������C[j]�ĺ��棬��ô��B��������ҪC[i]�������C[j]��ǰ�档
����C���еĳ����Ϊ�����أ�


**��������:**
>��һ��һ����������ʾN��
�ڶ���N����������ʾA���С�
������N����������ʾB���С�
����:N<=50000


**�������:**
>������ĳ���

**������**
```
����
5
1 2 4 3 5
5 2 3 4 1
����
2
```


### �ο�����

```java

```
