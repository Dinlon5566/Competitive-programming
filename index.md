<h1>競賽快速參考筆記</h1>

本文若無特別標記皆為 C++，用於比賽前快速複習。  
若有新發現會再更新  
- [Code](https://github.com/Dinlon5566/Competitive-programming/tree/main/code)

# 技巧

## 宣告

萬用標頭
```cpp
#include <bits/stdc++.h>
```

正無限替代，可以應用於 memset、inf+inf 等
```cpp
#define INF 0x3f3f3f3f
```

long long 縮寫
```cpp
using ll = long long;
```

放在 main 開頭，若只用 cin/cout 可以加速 (1.取消同步指針2.取消cin/cout綁定)  
***不要混用 printf & scanf ! ***
```cpp
(std::)ios::sync_with_stdio(false);
(std::)cin.tie(NULL);
```

## 常用
設定 arr 全部為 0  
***不要對 non-POD 容器進行 memset，會非法存取!***
```cpp
memset(arr,0,sizeof(arr)); 
```
快速輸出 2D 陣列
```cpp
for(auto a:v2d){
        for(auto b:a)
            cout<<b<<" ";
        puts("");
}
```
執行時間 ta~tb
```cpp
int ta=clock();
/* Code */
int tb=clock();
cout<<v.size()<<endl;
```
++i 比 i++ 快了一點點點 ( 還不如 cout 改成 printf )  
  
scanf 到 EOF
```cpp
while(cin>>n){}
```

### 字串讀入

單個字符
```cpp
ch=cin.get();
```
清除緩衝
```cpp
cin.ignore();
```
string 讀入一行
```cpp
getline(cin,str);
```
char[n] 讀入 n 字
```cpp
cin.getline(cha,n);
gets(cha);
```

# STL

## Vector

生成 n*m 二維vector
```cpp
vector<vector<int>> v2d(n,vector<int>(m,0));
```
將 obj 推入 v 
```cpp
v.push_back(obj);
```
重設大小，若 size 大於原本補上 num
```cpp
v2d[n].resize(size,num);
 ```
重設大小，全替換成 num
```cpp
v2d[n].assign(size,num);
 ```
Sort 
```cpp
sort(v.begin(),v.end());
```

## Algorithm

# Struct

Binary tree
```cpp
struct TreeNode {
      int val;
      TreeNode *left;
      TreeNode *right;
      TreeNode() : val(0), left(nullptr), right(nullptr) {}
      TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
      TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
  };
```

Link list
```cpp
    struct ListNode {
      int val;
      ListNode *next;
      ListNode() : val(0), next(nullptr) {}
      ListNode(int x) : val(x), next(nullptr) {}
      ListNode(int x, ListNode *next) : val(x), next(next) {}
  };

```

# 算法

尚未更新

# 愚蠢錯誤檢查

當出現一些無法解釋的問題，試試看以下常見問題

-   = 跟 == 符號誤寫
-   Debug 輸出刪除
-   換行 空格
-   邊際條件

---

# 後記

這些方法並不是我想出來的，由各種地方各個大神所得出的結論中整理而來。

如果能幫到你我會很高興，有問題或是建議歡迎提出 Issues 。
