![Floyd-Warshall Algorithm](https://user-images.githubusercontent.com/26141133/76058948-a6256d00-5fa3-11ea-942e-0c923a9aa409.png)

```cpp
vector<vector<int> > Solution::solve(vector<vector<int> > &A) {
    for(auto &row: A){
        for(auto &ele: row){
            if(ele == -1)
                ele = INT_MAX/2;
        }
    }
    for(int k = 0; k < A.size(); ++k){
        for(int i = 0; i < A.size(); ++i){
            for(int j = 0; j < A.size(); ++j){
                A[i][j] = min(A[i][k] + A[k][j], A[i][j]);
            }
        }
    }
    for(auto &row: A){
        for(auto &ele: row){
            if(ele >= INT_MAX/2)
                ele = -1;
        }
    }
    return A;
}
```
