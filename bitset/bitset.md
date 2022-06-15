# Bitset
```
我用#CSDN#这个app发现了有技术含量的博客，
小伙伴们求同去《C++ bitset的使用》, 一起
来围观吧 https://blog.csdn.net/sinat_41657218/article/details/122353820?utm_source=app&app_version=5.5.0&code=app_1562916241&uLinkId=usr1mkqgl919blen
```

```
bitset<N> 表示一个N位的固定大小的序列，可以用于整数和字符串的相互转换
例：5在bitset<8> temp中存储为 [0000 0101] (temp[0]=0,temp[8]=1)
采用逆向存储(低位存放高阶，高位存放低阶)，并且采用的是补码
空间长度不足正整数自动补0，负整数自动补1

满足：
1.可复制构造
2.可复制赋值
```

## 头文件
`#include <bitset>`


## bitset初始化
### 构造
#### 空构造
`bitset<N> temp(); // [0,0,0,0, 0,0,0,0]`

#### 自身构造，长度必须相同
```
bitset<N> temp1(string("00001001"));
bitset<N> temp2(temp1); // [0,0,0,0, 1,0,0,1]
// 或者
// bitset<N> temp2=temp1; // [0,0,0,0, 1,0,0,1]
```

### 整数初始化
```
bitset(N) temp((unsigned long long)(9));  // [0,0,0,0, 1,0,0,1]
bitset(N) temp((unsigned long long)(-9)); // [1,1,1,1, 0,1,1,1]
bitset(N) temp(0b11110111); // [1,1,1,1, 0,1,1,1]
```
* 如果初始化的整数长度大于N（长度不足）：
  * 数字19的二进制: 0001 0011，若bitset长度不足，将会保存保存低阶部分
`bitset<4> temp(19)  // [0,0,1,1]`


