# Automatic-Removal-of-Highly-Correlated-Columns-for-AutoML

This project automatically drops minimum number of highly correlated columns.

## Code:
1. Data is loaded using pd.read() method.
2. A correlation dataFrame is obtained using data.corr() method.
3. Filter the corr() data frame using desired threshold(for example : data.corr() > 0.85)
4. **Set the diagonal to np.nan as diagonal of correlation matrix is always 1.0**
5. Remove all rows and columns with absolute np.nan
**Important**
6. If the current shape of correlation matrix is (0,0), there are no highly correlated columns.
7. Else: 
    While the corr.shape is not equal to zero,
      Keep removing columns with max(corr)
      remove all rows and columns with absolute np.nan
      store removed columns in a list removed_cols[]
      
8. Now drop the removed_cols from original data frame.
9. This dataFrame will not have any column correlated with another with a value greater than the threshold(in this case 0.85).

## Advantages
There's minimum loss in number of columns dropped, by using this method.

## How to run it:
1. Download the .ipynb file
2. Open it in Jupyter Notebook/Google Colab
3. In the **Test your data here section** edit and uncomment the pd.read_csv() line
4. Run all cells
5. For visualization, uncomment the last three cells, to note the difference in **heatmap of df.corr()**

## Requirements:
1. Anaconda 3 for Jupyter Notebook

# Thank You
