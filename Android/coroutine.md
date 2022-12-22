# Coroutine

## Scope

| 類型 | 生命週期 |
| --- | ---- |
| Global | 存活於整個application |
| LifeCycle | 存活於該activity |
| ViewModel | 存活於該viewmodel |

## withContext 

| 類型 | 說明 |
| --- | ---- |
| Default | 使用的thread會取決於當下的thread，最大thread數將取決於cpu 核心數量 |
| IO | 會建立一個 Worked Thread，並在上面執行，適合用在 IO 之類的耗時操作 |
| Main | 處理UI物件，ui thread |
| Unconfined | 一開始是在thread main之後會轉到thread default |
| newSingleThreadContext | 每次都新增一個thread |

## setValue VS postValue 

setValue -> use on main thread

postValue -> use on background thread