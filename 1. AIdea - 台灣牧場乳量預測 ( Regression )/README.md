# AIdea - 台灣牧場乳量預測 ( Regression )

## 介紹

這是一個簡單的「迴歸 ( Regression )」練習，可以進行「連續值」的預測。例如：預測房屋價格、預測股價、預測體重、預測購買機率 ... 等。

> <details>
> 
> <summary>更多 Regression 技術的說明</summary>
>
> ## Regression 迴歸模型
> 
> 線性迴歸 ( Linear regression ) 是一種資料分析技術，透過「最小平方法」找到一個方程式，讓所有預測值與真實值之間的「誤差和」最小。
> 
> > 其中，方程式就是迴歸模型，依照輸入計算出預測值，而誤差和是迴歸模型的成本函數。
> 
> ### 容易混淆：目的不同的迴歸模型
> 
> 邏輯迴歸 ( Logistic regression ) 是由線性迴歸變化而來的「分類」模型，其目標是要找出一條直線能夠將所有資料清楚地分開並做分類，也可以稱其為迴歸的分類器。
> 
> > 根據應變量( Y )的資料種類不同，適用不同的迴歸模型：
> > 
> > - 若 Y 為連續性資料 ( continuous data )，例如：房價、體重、分數...等等，「預測目標數值的任務」可以使用「線性迴歸」。
> > 
> > - 若 Y 為二元變量資料 ( binary data )，例如：生與死、是與否、錄取與不錄取，「預測目標類別的任務」則較適合使用「邏輯迴歸」。
> 
> </details>

## 功能

- [x] 讀取 csv 資料
- [x] 資料清洗與分割
- [x] 建立迴歸模型
- [x] 預測缺值資料

## 環境部屬

開發環境：Jupyter notebook

### 安裝套件

- numpy：多維陣列與矩陣運算。

- pandas：資料操縱與分析。

- math：常用的數學函式，例如 三角函數、四捨五入、指數、對數、平方根、總和。

- scipy：演算法函式庫 與 科學工程數學，例如 最佳化、線性代數、積分、插值、特殊函數、快速傅立葉轉換、訊號處理和圖像處理、常微分方程式求解。

- sklearn：機器學習套件。

- matplotlib：視覺化套件。

- seaborn：高級視覺化模組，專注於美化設計與統計圖形的繪製。


## Demo

> 完整執行結果顯示於 Jupyter Notebook (.ipynb) 檔：[milk.ipynb](./jupyter%20notebook/milk.ipynb)

1. report_data：讀取輸入資料。

    ![report_data](./assets/images/1.%20report_data.JPG)

2. Data Cleaning：資料清洗，擷取訓練所需的特徵。

    ![Data Cleaning](./assets/images/2.%20Data%20Cleaning.JPG)

3. Regression result：建立迴歸曲線，預測缺失值。

    ![Regression result](./assets/images/3.%20Regression%20result.JPG)
