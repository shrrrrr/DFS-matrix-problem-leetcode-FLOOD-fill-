# DFS-matrix-problem-leetcode-FLOOD-fill-
https://leetcode.com/problems/flood-fill/
class Solution {
public:
    void dfs(int i,int j,int ini_co,int new_co,vector<vector<int>>&image){
        int n=image.size();
        int m=image[0].size();
        
        if(i<0||j<0||i>=n||j>=m) return;
        
        if(image[i][j]!=ini_co) return;
        
         image[i][j]=new_co;
        dfs(i+1,j,ini_co,new_co,image);
        dfs(i-1,j,ini_co,new_co,image);
        dfs(i,j+1,ini_co,new_co,image);
        dfs(i,j-1,ini_co,new_co,image);
        
        
        
    }
    
    vector<vector<int>> floodFill(vector<vector<int>>& image, int sr, int sc, int newColor) {
        int ini_co=image[sr][sc];
        if(ini_co!=newColor)
   dfs(sr,sc,ini_co,newColor,image);
        return image;
    }
};
