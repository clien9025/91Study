## 2020.11.6--LeetCode--66--加一

```
### 思路

1.对所有数组的每一位(从后置位开始)进行进位的判断(1+9=10)
2.针对999这类特殊的数字，采取这样的思路：[999]-->[1000]，直接新建一个新的数组(比原先容量大一位)，[0]位置上置1，返回

### 代码


​```java
class Solution {
    public int[] plusOne(int[] digits) {

        // 对数组的每一位进行是否进位判断
        for(int count = digits.length - 1;count >= 0;count--){
            // 依次的对数组的每一个后置位 +1
            digits[count]++;
            // 取余的操作：对 +1 的那个后置位进行判断，该位上的数字是否进位了
            digits[count] = digits[count] % 10;

            // 判断每次的后置位是否进位了，取余的结果为：零，则进位了：否则，没有进位，返回 disgit
            if(digits[count] != 0){return digits;}
        
        }
        // 若是出现了例如：999 这类的数字
        int[]disgits = new int[digits.length + 1];
        disgits[0] = 1;
        return disgits;
    }
}

​```

