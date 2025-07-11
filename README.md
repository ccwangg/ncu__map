# NCU Map
中央大學地標搜尋

## 技術
JS前端框架：Vue.js
CSS框架：Bootstrap

## 分工：
```
汪宸宇：分類按鈕、點擊顯示、搜尋功能

羅宣祐：地標資料蒐集、tooltip顯示

楊昊：網頁架構、地圖Canvas顯示
```
## 功能
* 進入頁面
![image](https://github.com/user-attachments/assets/56e917db-5f9a-49e3-9266-59dc57e264ca)
* 地標資料
![image](https://github.com/user-attachments/assets/4c3050f3-b556-49fd-a909-36a106a1fdc9)
* 分類顯示
![image](https://github.com/user-attachments/assets/dd46c166-cc9f-4b36-8ae0-a2216bf11644)
* 搜尋地標
![image](https://github.com/user-attachments/assets/ebe61e18-a8f9-4756-b74b-bd70edecace9)



## DATA格式

JSON 在/src/assets 

```
格式
{
  "name": "",
  "intro": "...",
  "tag": []
  "classify" : []
  "pic" : "" #包含圖片的相對路徑 可以直接用 vue記得加@/
  "Position": {
      "x": ...,  #背景圖片為900*600 左上為(0,0) 該座標紀錄大致位置 
      "y": ...
    }
}

# classify 為0-3 預設是 0:食物 1:系所 2:宿舍 3:行政 分類按鈕可以用
```

## 功能串接

- 輸入字串搜尋

File: `.\src\components\SearchBar.vue`

```
...

search() {
  if (this.searchInput) {
    // 程式碼
    this.showResult(result);
  }
}

...

```

Input: ```this.searchInput```
Type: ```String```
Format: `Text\Plain`

<br>

- 顯示地圖圖標

File: `.\src\components\MapCanvas.vue`

```
...a

showResult(result) {
  // 程式碼
},

...
```

Input: ```result```
Type: ```Array```
Format: `[Loc1, Loc2, ...]`
( `data.json` 中的 `name` )

<br>

- 顯示詳細資訊

File: `.\src\components\?.vue`

```
...

showDetail(name) {
  // 程式碼
},

...
```

Input: ```name```
Type: ```String```
Format: `Loc`
( `data.json` 中的 `name` )
