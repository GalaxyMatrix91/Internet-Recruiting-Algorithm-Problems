# �����չ�˾2018У԰��Ƹ�㷨������

<!-- TOC -->
* [��һ��](#��һ��)
* [�ڶ���](#�ڶ���)
* [������](#������)
<!-- TOC -->


## ��һ�� ƴ��������

### ��Ŀ����
>ţţ��4��ľ��,���ȷֱ�Ϊa,b,c,d��������ṩ�ı�ľ�����ȵķ���,���ţţ֧��һ��Ӳ�ҾͿ�����һ��ľ���ĳ��ȼ�һ���߼�һ��
ţţ��Ҫ�����ĸ�ľ��ƴ��һ�������γ���,ţţ������Ҫ֧������Ӳ�Ҳ��������ĸ�ľ��ƴ�ճ������Ρ�

**��������:**
>�������һ��,�ĸ�����a,b,c,d(1 �� a,b,c,d �� 10^6), �Կո�ָ�


**�������:**
>���һ������,��ʾţţ������Ҫ֧����Ӳ��

**������**
```
����
4 1 5 4

���
4
```

### �ο�����
```java
import java.util.*;

public class Main{
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        int[] arr = new int[4];
        for(int i=0;i<4;i++){
            arr[i]=in.nextInt();
        }
        Arrays.sort(arr);
        int edge = arr[1];
        int result = 0;
        for(int i=0;i<arr.length;i++){
            result+=Math.abs(edge-arr[i]);
        }
        System.out.println(result);
    }
}
```

## �ڶ��� ������

### ��Ŀ����
>ţţ����ʦ������һ������Ķ���:����x �� y,[x, y]��ʾx��y֮��(����x��y)�����������������ϡ�����[3,3] = {3}, [4,7] = {4,5,6,7}.ţţ������һ������Ϊn�ĵ�������,ţţ��֪����Ҫ���ٸ����䲢��������������С�
����:
{1,2,3,4,5,6,7,8,9,10}����ֻ��Ҫ[1,10]��һ������
{1,3,5,6,7}����ֻ��Ҫ[1,1],[3,3],[5,7]���������� 

**��������:**
>�����������,��һ��һ������n(1 �� n �� 50),
�ڶ���n������a[i](1 �� a[i] �� 50),��ʾţţ������,��֤�����ǵ����ġ�


**�������:**
>���һ������,��ʾ�������������

**������**
```
����
5
1 3 5 6 7

���
3
```

### �ο�����
```java
import java.util.*;

public class Main{
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        int n = in.nextInt();
        int[] arr = new int[n];
        for(int i=0;i<n;i++){
            arr[i]=in.nextInt();
        }
        int result = 1;
        for(int i=1;i<n;i++){
            if(arr[i]-arr[i-1]>1){
                result++;
            }
        }
        System.out.println(result);
    }
}
```

## ������ ȱʧ������

### ��Ŀ����
>һ�������������ַ��������������:
1�����ַ����������ġ�
2�����s���������ַ�������ô(s)Ҳ�������ġ�
3�����s��t���������ַ��������������������γɵ�stҲ�������ġ�
���磬"(()())", ""��"(())()"�������������ַ�����"())(", "()(" �� ")"�ǲ������������ַ�����
ţţ��һ�������ַ���s,������Ҫ����������λ�þ����ٵ��������,����ת��Ϊһ�������������ַ���������ţţ������Ҫ��Ӷ��ٸ����š� 

**��������:**
>�������һ��,һ����������s,���г���length(1 �� length �� 50).
s��ÿ���ַ����������Ż���������,��'('����')'.


**�������:**
>���һ������,��ʾ������Ҫ��ӵ�������

**������**
```
����
(()(()

���
2
```

### �ο�����
```java
import java.util.*;

public class Main{
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        String s = in.nextLine();
        Stack<Character> stack = new Stack<Character>();
        for(int i=0;i<s.length();i++){
            if(stack.empty()){
                stack.push(s.charAt(i));
            }else{
                if(s.charAt(i)==')'){
                    if(stack.peek()=='('){
                        stack.pop();
                    }
                    else{
                        stack.push(')');
                    }
                }else{
                    stack.push('(');
                }
            }
        }
        System.out.println(stack.size());
    }
}
```
