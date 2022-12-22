# activit

## 新增 activit
onCreate() -> onStart() -> onResume()

## 關閉 activit
onPause() -> onStop() -> onDestroy()

## 手機轉換方向
onPause() -> onSaveInstanceState() -> onStop() -> onDestroy() -> onCreate() -> onStart() -> onRestoreInstanceState() -> onResume()

## activity 切換

### ActivityA switch to ActivityB

ActivityA = onPause()
ActivityB = onCreate()-> onStart() -> onStart() -> onResume()
ActivityA = onStop() -> onDestroy()

### ActivityB back to ActivityA

ActivityB = onPause()
ActivityA = onRestart() -> onStart() -> onResume()
ActivityB = onStop() -> onDestroy()

## onClick Home Button

onPause() -> onStop() ->  onRestart() -> onStart() -> onResume

## service

### startService (create to finish)
**startService()** -> onCreat() -> onStartCommand() -> **stopService()** ->onDestory()


## bindService (bind to unbind)
**bindService()** -> onCreate() -> onBind() -> **unbindService()** -> onUnbind() -> onDestory()

## startService + bindService
**startService()** -> onCreat() -> onStartCommand() -> **bindService()** -> onBind() **stopService()** ->onDestory()

> **粗體** method表示需要手動去呼叫

## fragment

## 建立
onAttach() -> onCreate() -> onCreateView() -> onActivityCreated() -> onStart() -> onResume() -> 

### 不在前景(最上層)時
onPause() -> onStop

### 消滅
onPause() -> onStop() -> onDestroyView() -> onDestroy() -> onDetach()

## view

onMeasure() -> onLayout() -> onDraw()

## viewModel

### create
onCreate() -> onStrat() -> onResume()

### rotated
onPause() -> onStop() -> onDestory() -> onCreate() -> onStart() -> onResume()

### finish
onPause() -> onStop() -> onDestory()