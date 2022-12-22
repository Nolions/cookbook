# android

## 四大元件

### Activity

與用戶交互的入口點，每個 Activity 都獨立於其他 Activity 而存在。

### Sevice

沒有UI的Activity，運行在背景中

有以下兩張Sevice

 1. bindService

 2. startService 

### Content Provider

管理與其他應用程式的對於共享資料存取的方法

### Broadcast 

用來接收來自系統和應用中的廣播

## efficacy

### Out of Memory (OOM)

APP使用記憶體超出允許使用上限

### Memory Leak

未被使用的物件，未順利GC，造成記憶體一直占用情況。

當一個物件持有一個生命週期比它短的物件的引用，就有可能引起記憶體洩漏，因為生命週期比較短的物件如期GC。