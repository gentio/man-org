# 整数平方根

## 牛顿法开平方
牛顿法本质是一种迭代解法，在数值分析里是一种方法，出现于《Hacker Delight》里作为一种整数求根的实现。

‘
    int isqrt(unsigned x)
    {
        unsigned x1;
        int s, g0, g1;

        if (x1 < 1) return x;
        s = 1;
        x1 = x - 1;
        if (x1 > 65535) {s = s + 8; x1 = x1 >> 16;}
        if (x1 > 255) {s = s + 4; x1 = x1 >> 8;}
        if (x1 > 15) {s = s + 2; x1 = x1 >> 4;}
        if (x1 > 3) {s = s + 1;}

        g0 =  1 << s;
        g1 = (g0 + (x >> s)) >> 1;
        while (g0 > g1) {
            g0 = g1;
            g1 = (g0 + (x / g0)) >> 1;
        }
        return g0;
    }
 
’
## 二分查找树

## 二分s
