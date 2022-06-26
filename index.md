<h1>競賽快速參考筆記</h1>

本文若無特別標記皆為 C++，用於比賽前快速複習。  
若有新發現會再更新  
- [Code](https://github.com/Dinlon5566/Competitive-programming/tree/master/Code)

# 技巧

## 宣告

```cpp
//萬用標頭
#include <bits/stdc++.h>

//正無限替代，可以應用於 memset、inf+inf等
#define INF 0x3f3f3f3f

// long long 縮寫
using ll = long long;

// 放在 main 開頭，若只用 cin/cout 可以加速 (1.取消同步指針2.取消cin/cout綁定)
/* <span style="color:red">不要混用 printf scanf !</span> */
(std::)ios::sync_with_stdio(false);
(std::)cin.tie(NULL);
```

## 常用

```cpp
//設定 arr 到前 sizeof(arr) 設為字節 0
/* <span style="color:red">不要對 non-POD 容器進行 memset，會非法存取!</span> */
memset(arr,0,sizeof(arr)); 

//快速輸出 2D 陣列
for(auto a:v2d){
        for(auto b:a)
            cout<<b<<" ";
        puts("");
}

//執行時間 ta~tb
int ta=clock();
/* . . . 程式碼 . . . */
int tb=clock();
cout<<v.size()<<endl;

// ++i 比 i++ 快了一點點點 ( 還不如 cout 改成 printf )

//scanf 到 EOF
while(cin>>n){}

```

### 字串讀入

```cpp
// 單個字符
ch=cin.get();
// 清除緩衝
cin.ignore();
// string 讀入一行
getline(cin,str);
// char[n] 讀入 n 字
cin.getline(cha,n);
gets(cha);
```

# STL

## Vector

```cpp
//生成 n*m 二維vector
vector<vector<int>> v2d(n,vector<int>(m,0));

// 將 obj 推入 v 
v.push_back(obj);

// 重設大小，若 size 大於原本補上 num
v2d[n].resize(size,num);

// 重設大小，全替換成 num
v2d[n].assign(size,num);

// Sort 
sort(v.begin(),v.end());
```

## Algorithm

# Struct

```cpp
// Binary tree
struct TreeNode {
      int val;
      TreeNode *left;
      TreeNode *right;
      TreeNode() : val(0), left(nullptr), right(nullptr) {}
      TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
      TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
  };
// Link list
    struct ListNode {
      int val;
      ListNode *next;
      ListNode() : val(0), next(nullptr) {}
      ListNode(int x) : val(x), next(nullptr) {}
      ListNode(int x, ListNode *next) : val(x), next(next) {}
  };

```

# 算法

## 

# 愚蠢錯誤檢查

當出現一些無法解釋的問題，試試看以下常見問題

- [ ]  = 跟 == 符號誤寫
- [ ]  Debug 輸出刪除
- [ ]  換行 空格
- [ ]  邊際條件

---

# 後記

這些方法並不是我想出來的，由各種地方各個大神所得出的結論中整理而來。

如果能幫到你我會很高興，有問題或是建議歡迎提出 Issues 。
