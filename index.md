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
***不要混用 printf & scanf !***
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
重設大小
+ 若 size 大於原本補上 num
```cpp
v2d[n].resize(size,num);
 ```
+ 全替換成 num
```cpp
v2d[n].assign(size,num);
 ```

## Set
初始化及插入值
```cpp
    set<int> mySet{3,8,9};
    mySet.insert(num);
```
刪除值及清空
```cpp
    mySet.erase(num);
    mySet.clear();
 ```
 找尋物件
 ```cpp
    //方法一 return bool
    mySet.count(num)
    //方法二 return iterator
    auto iter=mySet.find(num);
    if(iter!=mySet.end())
        puts("found");
```

## map
初始化及插入值
```cpp
    myMap.insert(pair<int,string>(1,"one"));
    myMap[3]="Three";
```
刪除值
```cpp
    myMap.erase(num);
    myMap.clear();      
```
遍歷
```cpp
    cout<<myMap.at(3);
    for(auto s:myMap){
        cout<<s.first<<" "<<s.second<<endl;
    }
    
    map<int,string>::iterator it;
    for(it=myMap.begin();it!=myMap.end();it++){//rbegin()~rend();
        cout<<(*it).first<<" "<<(*it).second<<endl;
    }
```
## Sort

範例陣列
```cpp
    int arr[]= {3,9,8,6,2,5,4,1,7};
    vector<int> v= {3,9,8,6,2,5,4,1,7};
```
升序排序
```cpp
    // std::begin() 取得 c-style 陣列首尾
    sort(begin(arr),end(arr));
    sort(v.begin(),v.end());
```
升序與降序
```cpp
    sort(begin(arr),end(arr),less<int>());
    sort(begin(arr),end(arr),greater<int>());
```
自訂方法
+ 自訂函數
```cpp
bool cmp(int a,int b){
    return a>b;
}
    sort(v.begin(),v.end(),cmp);
```
+ 反向指針
```cpp

    sort(v.rbegin(),v.rend());
 ```
+ lambda
```cpp
    sort(v.begin(),v.end(),[](int a,int b){ return a>b; });
```
+ operator
```cpp
class myclass{
    int first,second;
    bool operator()(myclass a,myclass b){
        return a.first<a.first;
    }
};
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
