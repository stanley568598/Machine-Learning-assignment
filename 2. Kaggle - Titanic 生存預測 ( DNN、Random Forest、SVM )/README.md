# Kaggle - Titanic 生存預測 ( DNN、Random Forest、SVM )

## 介紹

這是一個簡單的「分類 ( Classification )」練習，可以進行「不連續的值 ( 項目種類 )」的預測。例如：核貸與否、信用評等、語意分析 ( 文章正負面 )、垃圾郵件偵測 ... 等。

> <details>
> 
> <summary>更多 Classification 技術的說明</summary>
> 
> ## Classification 分類模型
> 
> 二元分類 ( binary classification ) 是一種機器學習中最常見的任務，其目的是從兩個不同類別中將每個資料歸類為其中之一。
> 
> 適用於從一堆資料中進行任何是非問題的判斷，對新數據進行預測時，模型對預測類別的輸出結果通常是 ( 0 或 1 )。
> 
> 常見的模型演算法：
> - **神經網路 ( Neural Network )**
> - 樸素貝葉斯 ( Naive Bayes )
> - 決策樹 ( Decision Tree )
> - **隨機森林 ( Random Forest )**
> - 邏輯迴歸 ( Logistic Regression )
> - **支援向量機 ( Support Vector Machine，SVM )**
> - K-最近鄰演算法 ( k Nearest Neighbor，kNN )
> 
> <details>
> 
> <summary>模型觀念介紹</summary>
> 
> <br>
> 
> > ### DNN ( Deep Neural Network，深度神經網路 ) 
> > 
> > <details>
> > 
> > <summary>詳細說明</summary>
> >
> > <br>
> > 
> > 神經網路是使用神經元形成節點網路的模型。像大腦一樣，這些神經元是離散的功能 ( 如同一群小機器 )，它們接受非常有限的輸入，並產生非常有限的輸出。這些節點按層排列，其中一層中神經元的輸出成為下一層神經元的輸入，直到網路外層的神經元產生最終結果。
> > 
> > 可以將其視為：因素分析 ( factor analysis )，將資料分成個別的因子，在這些神經元之中進行兩因素的討論，計算後的結果以啟動函數 ( activation function ) 加權總和進行非線性轉換，再將其輸出訊號傳遞給下一層。
> > 
> > | 啟動函數 | 說明 |
> > | :---- | :---- |
> > | Step | $f = \begin{cases} 0 & x < 0 \\ 1 & x \geq 0 \end{cases}$。常用於感知器。 |
> > | ReLU | $f = max(0, x)$，值域 [0, x]。常用於隱藏層。 |
> > | Sigmoid | $f = \frac{1}{( 1 + e^{(-x)})}$，值域為 [0, 1]。常用於輸出層 (二元分類)。 |
> > | Tanh | $f = tanh(x)$，值域 [-1, 1]。常用於輸出層 (二元分類)。 |
> > | Softmax | $f = \frac{e^{x}}{\sum e^{x}}$，值域 [0, 1], 常用於輸出層 (多元分類)。 |
> > 
> > </details>
> 
> > ### Random Forest ( 隨機森林 )
> > 
> > <details>
> > 
> > <summary>詳細說明</summary>
> >
> > <br>
> >
> > 隨機森林，將資料集取樣成多個子資料集，個別建立決策樹模型，這些決策樹不互相影響，最終使用民主多數決的方式決定最後結果。
> > 
> > - 整合法 ( Ensemble Method )：結合多個「弱學習器」來建構一個更強的模型「強學習器」，也就是「三個臭皮匠勝過一個諸葛亮」的概念。
> > 
> > - 隨機森林的「隨機」抽樣，使決策樹更加多元，有多元的結果，綜合起來會更具有準確度。
> >     
> >     - 採取抽後放回的方法，也就是同一個樣本，被抽了之後，下一次還是有可能抽到他，一個人可能抽到很多次，也有可能都沒抽到。
> > 
> >     - 包含「隨機樣本」和「隨機變數」：這樣每顆決策樹，不僅樣本數不同，連 變數 ( 特徵 ) 也不一樣。
> > 
> > - 透過隨機樣本與隨機特徵來建構多棵的決策樹，每一棵決策樹會對輸入的樣本產出一個分類，最後使用民主多數決的方式決定最後結果。
> > 
> > </details>
> 
> > ### SVM ( Support Vector Machine，支援向量機 )
> > 
> > <details>
> > 
> > <summary>詳細說明</summary>
> >
> > <br>
> > 
> > 支援向量機，將資料點視為 P 維向量，並且想透過 ( P - 1 ) 維的「超平面」來分開這些點。
> > 
> > - 針對小樣本、非線性、高維度等問題具有相對的優勢。
> > 
> >     - 對於線性可分的樣本，多種模型都可以得到好的分類結果。
> >     
> >     - 但是，一般來說，我們總是會遇到比較複雜的樣本，很可能是線性不可分，甚至是高維度錯綜複雜的問題。
> >     
> >     - 因此，SVM 就是將在低維度空間的「線性不可分」樣本映射到高維度空間，再找到一個超平面將這些樣本做有效的切割。
> > 
> > - 支持向量 ( support vector )：離兩條「超平面間隔線」距離最近的點。
> > 
> >     - 目標：找到一個決策邊界 ( decision boundary )，讓兩個類別之間的間隔 ( margins ) 寬度最大化，使其可以完美區隔開來。
> > 
> >     - 這個超平面的兩側樣本要盡可能地遠離這個超平面，因為這樣可以縮小分類器的泛化誤差。
> > 
> > </details>
> 
> </details>
> 
> </details>

## 功能

- [x] 讀取 csv 資料
- [x] 資料觀察與分析
- [x] 資料清洗與拆分
- [x] 建置 DNN 模型
- [x] 分類模型 ( DNN、Random Forest、SVM ) 的 訓練與驗證 
- [x] 儲存分類模型

## 環境部屬

開發環境：Jupyter notebook

### 安裝套件

- numpy：多維陣列與矩陣運算。

- pandas：資料操縱與分析。

- math：常用的數學函式，例如 三角函數、四捨五入、指數、對數、平方根、總和。

- scipy：演算法函式庫 與 科學工程數學，例如 最佳化、線性代數、積分、插值、特殊函數、快速傅立葉轉換、訊號處理和圖像處理、常微分方程式求解。

- sklearn：機器學習套件。

- keras：神經網路套件，深度學習模型。

- warnings：過濾警告消息。

- joblib：平行化計算和資料預處理，支援模型保存與讀取。

- matplotlib：視覺化套件。

- seaborn：高級視覺化模組，專注於美化設計與統計圖形的繪製。

## Demo

> 完整執行結果顯示於 Jupyter Notebook (.ipynb) 檔：[titanic.ipynb](./jupyter%20notebook/titanic.ipynb)

1. titanic_data：讀取輸入資料。

    ![titanic_data](./assets/images/1.%20titanic_data.JPG)

2. Data Visualization：資料視覺化，stacked bar chart。

    ![Data Cleaning](./assets/images/2.%20Data%20Visualization%20(%20stacked%20bar%20chart%20).JPG)

3. Data Distribution：資料分布，KDE plot ( kernel density estimate )。

    ![Data Distribution](./assets/images/3.%20Data%20Distribution%20(%20KDE%20plot%20-%20kernel%20density%20estimate%20).JPG)

4. DNN 

    - Training and Validation Accuracy Curves。

        ![DNN Accuracy Curves](./assets/images/4.%20DNN%20(%20Training%20and%20Validation%20Accuracy%20Curves%20).JPG)

    - Training and Validation Loss Curves。

        ![DNN Loss Curves](./assets/images/5.%20DNN%20(%20Training%20and%20Validation%20Loss%20Curves%20).JPG)
    
    - DNN result
  
        ![DNN result](./assets/images/6.%20DNN%20result.JPG)

5. Random Forest result
  
    ![Random Forest result](./assets/images/7.%20Random%20Forest%20result.JPG)

6. SVM result
  
    ![SVM result](./assets/images/8.%20SVM%20result.JPG)
