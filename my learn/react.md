REACT
===

###### tags: `react`


## 為什麼需要框架
#### Design Pattern工廠模式
* 某一個程式模組只負責製造一種東西
* ==讓「製造、產生Menu」的過程變成「共同行為」==
* 實體(Instance)與類別(class)
> 以人類來比喻的話，
> 人類是一種class，但joy與mark是兩個不同的instance
> 雖然joy與mark都是人類，但兩人是不同個體


---
## ES6


#### 常數const
- 穩定
- 可用於複合型的dataType，物件與陣列宣告
> 函式與陣列均為物件
- 可用於函式表達式
> 箭頭函式是函式表達式的一種


#### const與let
1. 優先使用const
2. 使用let時需要指定初始值，若不確定值的類型，可使用null
3. 一行語句宣告一個變數
4. 區塊作用域(block)vs函式作用域(function)
5. for 迴圈中的let會重新綁定
6. for loop圓括號中的let仍是在block

![](https://i.imgur.com/ggVuYIY.png)

### 展開運算符與其餘運算符 (spread operator & rest operator)
![](https://i.imgur.com/GaoFZHI.png)



### 類別(class)
>以駝峰方式命名
>

### 模組(moudule)語法
用於組織與管理，搭配npm，方便使用與導入現有模組
````javascript
//模組輸出
expert defalt Myclass
//模組輸入
import Myclass from ',/myclass'
````


## React基本觀念
#### 用來建立UI的JS lib
1. 由FB創造與維護
2. 用於開發網頁應用程式
3. 非完整Framework，偏向傳統MVC中的V

>MVC模式(Model–view–controller)
>一種軟體架構，傳統分為系統、視圖、控制器
>
>模型（Model） - 程式設計師編寫程式應有的功能（實現演算法等等）、資料庫專家進行資料管理和資料庫設計(可以實現具體的功能)。
>視圖（View） - 介面設計人員進行圖形介面設計。
>控制器（Controller）- 負責轉發請求，對請求進行處理。

![](https://upload.wikimedia.org/wikipedia/commons/f/f0/ModelViewControllerDiagramZh.png)


#### FB發展react原因
1. DOM動態生成，使用者操作後變多
2. 網站功能多，需應對不同資料源
3. 程式碼分離平行運行、優先權排程

>應用範圍
>![](https://i.imgur.com/i1KIRRz.png)

#### React 五大特性
- 虛擬DOM
>React中自行管理DOM物件
>用於差異比較後與真實DOM做渲染


- 單向資料流
>元件間依靠屬性特性傳遞資料
>只能由父母元件傳遞子女元件
>在複雜結構中容易出錯與最佳化

- 宣告是程式開發
>使用類似HTML語法撰寫
>DOM事件與處理全部交由React
>React協助開發者建立容易維護與除錯的APP

- 以元件為基礎
>以類別或函式，加入狀態(state)與屬性(prop)特性來開發

- JSX語法
> JSX中使用({})嵌入JS表達式
> 是React.createElement的簡寫法，只能寫在React
> 須透過babel編譯

==react 不建議直接改陣列，如：push、splice、shift、pop 、unshift==

#### Props(屬性)

* 資料傳遞方式，只有父母元件能夠單向傳遞給子女元件
* Props值是一種物件，可以透過函式的傳入參數得到
````javascrpt
function Child(props){
    return <h1>{props.text}</h1>
    }
````
````javascrpt
function Parents(){    
    return <Child text="我今天很棒">
    }
````

- prop傳遞方式
![](https://i.imgur.com/YaThwKP.png)




---


## Hook(用來簡化class寫法)

#### Hook使用準則
* 只能在最上層呼叫 Hooks
* 只能在 React 函式型元件中呼叫 Hooks

#### ==useState==
- 是一種function
- 設定每一個元件之間的狀態，透過狀態去顯現出想要呈現的樣子
````javascript
const[a ,setA] = useState(num)
````
> num - 初始值。
> setA - 相對應的工具，用來更改a的內容。(onClick...)
> a - 經setA操作後，最終呈現的值

````javascript
const[a ,setA] = useStat(100)

function plus (){
    setA(function(prev){
        return prev+200
    })
}

{a}

return <button onClick={plus}>加法</button>
````
範例：按下button後，會將初始值100＋setA提供的200，回傳值300


#### ==useEffect==
- 理解：改變了什麼東西 會觸發 useEffect
- 不支援asysnc
- 重新render時會useEffect會執行一次

````javascript
  useEffect(() => {}, [data]);
````
````javascript
const Home = () => {
  const [data, setData] = useState([]);
  useEffect(() => {
    // 外面的function是每次是每次執行會做的事情
    // return () => {
    // 裏面的function是在兩次渲染之間會做的事情
    // };
    //將網址外包
    fetchData(setData);
  }, []);
  ````

若data變動時候，function會執行一次

#### ==Fetch API==



延伸閱讀：fetch與axios比較

#### ==key==
- 需要是唯一值
- 不可用index當成key，會影響效能






---


## 08/10 內容
> 推薦以函式元件做，牽扯到==生命週期==問題

> 函式型元件會流行是因為==HOOK==
### index.js
1. render  - 渲染，主要是將虛擬DOM轉為真實DOM
2. strictMode - 嚴格模式，react檢查工具，2020出現


### App.js
1. return 的東西就是要網頁要render的
2. 函式型元件的return 相當於 類別型元件的render

````javascript
import React from 'react'
// 'react'是放在node_moudel的模組
// import 導入
function App() {
  // 解構賦值語法
  const [total, setTotal] = useState(0)
  //狀態
  return (
  //return只能有一個
    <>
      <h1
        onClick={() => {
          setTotal(total + 1)
        }}
      >
        {/* 屬性 */}
        {total}
      </h1>
    </>
  )
}


````