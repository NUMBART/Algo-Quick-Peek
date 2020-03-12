## Pseudocode   

![Floyd-Warshall Algorithm](https://user-images.githubusercontent.com/26141133/76058948-a6256d00-5fa3-11ea-942e-0c923a9aa409.png)

## Code  

```cpp
int solve(vector<vector<int> > &A) {
    for(auto &row : A)
        for(int &ele : row)
            if(ele == -1) ele = INT_MAX;
    
    for(int k = 1; k < A.size(); ++k){
        for(int i = 1; i < A.size(); ++i){
            for(int j = 1; j < A.size(); ++j){
                if(A[i][k] != INT_MAX && A[k][j] != INT_MAX)
                    A[i][j] = min(A[i][k]+A[k][j], A[i][j]);
            }
        }
    }
    
}
```
