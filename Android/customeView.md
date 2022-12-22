# CustomView

## 繼承既有ViewGroup元件

繼承既有View元件(Ex: FrameLayour...)，在使用View.inflate函數把定義UI的xml填充進去

***Example***

```kotlin
class GameResultView(context: Context) : FrameLayout(context) {
    
    init {
        this.inflate()
    }

    private inflate() {
        View.inflate(context, R.layout.view_custom_view, this)
    }
}
```

## 繼承View

繼承最底層View，然後在透過onMeasure定義View Size，在onLayout呈現位置，最後在onDraw再使用canvas進行繪製UI動作