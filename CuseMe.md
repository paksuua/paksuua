<div align="center" style="display:flex;">
	<img src="https://user-images.githubusercontent.com/39257919/71553942-423e6f80-2a5b-11ea-972f-364c5b896b60.png">
</div>
<div align="center">
๐ฃ CUSE ME_SERVER  ๐ป
<br>๋ฐ๋ฌ์ฅ์ ์ธ์ ์ํ ์นด๋ํ ์์ฌ์ํต๋๊ตฌ, ํ์ฆ๋ฏธ
</div>

[ํ์ฆ๋ฏธ ํ๋ ์ด์คํ ์ด ๋ค์ด](https://play.google.com/store/apps/details?id=com.cuseme.android.aac)
---
๋ฐ๋ฌ์ฅ์ ์ธ๋ค์๊ฒ ์ธ์์ ๋๊ณ  ๊น์ ๋ฐ๋ค์ ๊ฐ์ต๋๋ค.<br> 
๋ง์ด ํตํ์ง ์๋ ์ฌ๋๋ค๋ก ๊ฐ๋ํ ์ธ์์ ๊ทธ๋ค์๊ฒ ํจ๋ถ๋ก ๋์๊ฐ๊ธฐ ์ด๋ ต๊ณ , ๋ฌด์์ด ๊ณณ์ด๋๊น์.<br> 
 **์ฐ๋ฆฌ๋ ๋ฐ๋ฌ์ฅ์ ์ธ๋ค๋ ๋์ ์ธ์์ ์์ ๋กญ๊ฒ ํค์์น  ์ ์๊ธฐ๋ฅผ ๋ฐ๋๋๋ค.** 
<br> ์ฐ๋ฆฌ์ ์ต์ํ์ ์์ฌ์ํต์ด ๊ฐ๋ฅํ๋ค๋ฉด, ๋ฐ๋ฌ์ฅ์ ์ธ์ ์ธ์๋ ์กฐ๊ธ์ ๋์ด์ง์ง ์์๊น์?

&nbsp;

```
๐	์ฝ์๊ฐ ๋ฐฐ์ ๋์ง ์๋ ์ธ์์ ๊ฟ๊ฟ๋๋ค.
	์ผ์์์ ๋ง์ด ํตํ์ง ์๋๋ค๋ ์ด์ ๋ก ์ธ์์ ํฌ๊ธฐํ์ง ์์์ผ๋ฉด ์ข๊ฒ ์ต๋๋ค.
```
```
๐	์ด ์ฑ์ ๋ง์ฃผํ  ๋ชจ๋  ์ฌ์ฉ์๋ฅผ ์๊ฐํ์ต๋๋ค.
	๋ฐ๋ฌ์ฅ์ ์ธ ๋ฟ๋ง ์๋๋ผ ๋ณดํธ์, ์ด ์ฑ์ ๋ง์ฃผํ  ๋น์ฅ์ ์ธ๋ค์ ๋ชจ๋ ๊ณ ๋ คํ UX
```
```
๐	๊ธฐ์กด ์ฑ๋ณด๋ค ์ฌ์ฉ์ฑ์ ๋์์ต๋๋ค.
	TTS(Text To Speach), ์์ฑ ๋น์, ์นด๋ ๊ณต์  ๊ธฐ๋ฅ
```

------
### ๐ Service Work Flow
![แแฒแแณแแต_แแฏแแณแแณแฏแแฉแแฎ-1](https://user-images.githubusercontent.com/43192041/71722846-ccc50b80-2e6d-11ea-9385-5c8e0f581dba.png)

# CuseMe_Android :loudspeaker:

### ๐ 1.ํ๋ก์ ํธ ์ฌ์ฉ ๋ผ์ด๋ธ๋ฌ๋ฆฌ
๐Retrofit - ์๋ฒํต์ 
    
```       
    implementation 'com.squareup.retrofit2:retrofit:2.6.2'
    implementation 'com.google.code.gson:gson:2.8.6'
``` 

๐CardView - ์์ดํ(์นด๋) ๋์์ธ ์ ์ฉ
```
    implementation 'androidx.cardview:cardview:1.0.0'
    implementation 'com.google.android.material:material:1.0.0'
```

๐Fragment - ํ์ด์ง ์ ํ
```
    implementation "androidx.navigation:navigation-fragment-ktx:2.1.0-alpha05"
    implementation "androidx.navigation:navigation-ui-ktx:2.1.0-alpha05"
```
    
๐RecyclerView - ์์ดํ ์คํฌ๋กค
```
    implementation 'androidx.recyclerview:recyclerview:1.1.0'
```
    
๐Glide - ์ด๋ฏธ์ง ์ฌ์ฉ
```
    implementation 'com.github.bumptech.glide:glide:4.9.0'
    annotationProcessor 'com.github.bumptech.glide:compiler:4.9.0'
```
### ๐ 2.ํ๋ก์ ํธ ๊ตฌ์กฐ

|                  Activity                              |                 Description   |
| ----------------------------------- | ------------------------------------------- |
| DisabledActivity                                 |  ๋์ ์์ฒญ๊ณผ ๊ด๋ จํ ์ด๋ฏธ์ง, ์ค๋ช, ์์ฑ์ด ๋ํ๋จ    |
| UnlockActivity  | ์ ๊ธ ํด์ ์ ๋ณดํธ์ ๊ด๋ฆฌ ํ์ด์ง     |
| HelperActivity, HelperFragment  |  ์นด๋ ์์ดํ ํด๋ฆญ์   ์ญ์ , ์จ๊ธฐ๊ธฐ, ์์ , ์ทจ์ ๊ธฐ๋ฅ์ ํ๋จ๋ฐ ์์ฑ  |
| DetailCardActivity  | ์นด๋์ ์ด๋ฏธ์ง, ์จ๊น์ฌ๋ถ, ์ผ๋ ฌ๋ฒํธ, ์ ๋ชฉ, ์ค๋ช, ์นด๋ ์ฌ์ฉ์ ๋ณดํธ์์๋ฆผ ์ ์ก ์ฌ๋ถ, ์์ฑ ๋ฃ๊ธฐ  |
| HelperSortFragment  |  ์นด๋์ ๋ณด์ด๋ ์, ์ฌ์ฉ ๋น๋ ์, ์ด๋ฆ ์์ผ๋ก ์นด๋ ์ ๋ ฌ    |
| ManagementActivity  | ๋ณดํธ์๊ฐ ๋ฐ๋ฌ ์ฅ์ ์ธ์ด ๋ณผ ์ ์๋ ์นด๋๋ฅผ ์ ํ ๋ฐ ์ ๋ ฌ, ๋ฐ๋ฌ์ฅ์ ์ธ์ด ๋ณผ ์ ์๋ ์นด๋๋ฅผ ์ญ์ , ์จ๊ธฐ๊ธฐ, ์์   |
| DownloadCardActivity  | ์นด๋์ ์ผ๋ จ๋ฒํธ๋ฅผ ํตํด์ ์๋ก์ด ์นด๋๋ฅผ ๋ค์ด  |
| DetailCardActivity  | ์นด๋์ ์ธ๋ถ์ฌํญ(์ ๋ชฉ, ๋ด์ฉ, ์์ฑ, ์ด๋ฏธ์ง)๋ฅผ ํ์ธ  |
| AddCardActivity  | ์นด๋์ ์ ๋ชฉ, ๋ด์ฉ, ์์ฑ, ์ด๋ฏธ์ง๋ฅผ ๋ฃ๊ณ  ์๋ก์ด ์นด๋ ์์ฑ  |
| ModCardActivity  | ์นด๋์ ์ ๋ชฉ, ๋ด์ฉ, ์์ฑ, ์ด๋ฏธ์ง๋ฅผ ์์   |
| Setting Activity   | ๋ณดํธ์์ ๋น๋ฐ๋ฒํธ ๋ณ๊ฒฝ, ์ ํ๋ฒํธ ์ค์   |


### ๐ 3.ํต์ฌ ๊ธฐ๋ฅ ๊ตฌํ


1๏ธโฃ Zoom In / Zoom Out : ์นด๋์ ์ฌ์ด์ฆ๋ฅผ ๋ณ๊ฒฝ ํ  ์ ์๋ ๊ธฐ๋ฅ  


ํฐ์น๋๋ ์์ดํ์ ์์น๋ฅผ ๊ธฐ์ค์ผ๋ก ํ๋, ์ถ์ ๋๋๋กํ๋ฉฐ 1์ค์ 1-3๊ฐ๊น์ง ์ ๋ ฌ ๊ฐ๋ฅํ๋๋ก ์ ํํจ.

```
val mScaleGestureDetector = ScaleGestureDetector(
    this,
    object : ScaleGestureDetector.SimpleOnScaleGestureListener() {
        override fun onScale(detector: ScaleGestureDetector): Boolean {
            Log.v("Excuse", "์ค2")

            if (detector.currentSpan > 200 && detector.timeDelta > 200) {

                // 2์์ 3
                if (detector.currentSpan - detector.previousSpan < -1) {
                    if (mCurrentLayoutManager == gridManager2) {
                        mCurrentLayoutManager = gridManager3
                        rvDisabledCard.layoutManager = mCurrentLayoutManager
                        rvDisabledCard.scrollToPosition(position)
                        return true

                        //1์์ 2
                    } else if (detector.currentSpan - detector.previousSpan < -1) {
                        if (mCurrentLayoutManager == gridManager1) {
                            mCurrentLayoutManager = gridManager2
                            rvDisabledCard.layoutManager = mCurrentLayoutManager
                            rvDisabledCard.scrollToPosition(position)
                            return true
                        }
                    }
                }
                //3์์ 2
            } else if (detector.currentSpan - detector.previousSpan > 1) {
                if (mCurrentLayoutManager == gridManager3) {
                    mCurrentLayoutManager = gridManager2
                    rvDisabledCard.layoutManager = mCurrentLayoutManager
                    rvDisabledCard.scrollToPosition(position)
                    return true

                    //2์์ 1
                } else if (detector.currentSpan - detector.previousSpan > 1) {
                    if (mCurrentLayoutManager == gridManager2) {
                        mCurrentLayoutManager = gridManager1
                        rvDisabledCard.layoutManager = mCurrentLayoutManager
                        rvDisabledCard.scrollToPosition(position)
                        return true
                    }
                }
            }

            return false
        }
    })
    
```


2๏ธโฃ Long Click / Drag&Drop - DramanageAdapter๋ฅผ ์ฌ์ฉํ์ฌ 


์ฌ์ฉ์์ Long Click, Drag&Drop์ ๊ฐ์งํ๊ณ , ์นด๋์ ์์๋ฅผ swap ๊ฐ๋ฅํ๋๋ก ํจ.

```
class DragManageAdapter (adapter: RvHelperSortAdapter, context: Context, dragDirs: Int, swipeDirs: Int)
    : ItemTouchHelper.Callback(){

    var cardAdapter = adapter

    override fun onMove(
        recyclerView: RecyclerView,
        viewHolder: RecyclerView.ViewHolder,
        target: RecyclerView.ViewHolder
    ): Boolean {
        cardAdapter.swapItems(viewHolder.adapterPosition, target.adapterPosition)
        return true
    } // end onMove()

    override fun onSwiped(viewHolder: RecyclerView.ViewHolder, direction: Int) {
        // ์ฌ์ฉ์ํจ
    }

    override fun getMovementFlags(
        recyclerView: RecyclerView,
        viewHolder: RecyclerView.ViewHolder
    ): Int {
        val dragFlags: Int = ((ItemTouchHelper.UP.or(ItemTouchHelper.DOWN)).or(ItemTouchHelper.LEFT)).or(ItemTouchHelper.RIGHT)
        val swipeFlags = 0
        return makeMovementFlags(dragFlags,swipeFlags)
    }
}

```



3๏ธโฃ ์ค๋ณต ํฐ์น ๋ฐฉ์ง - ๋ฐ๋ฌ์ฅ์ ์ธ์ ๊ฒฝ์ฐ ๊ธฐ๋ฅ์ ์คํํ๊ธฐ ์ํ์ฌ ์ฌ๋ฌ๋ฒ ์ค๋ณตํ์ฌ ํฐ์นํ๋ ๊ฒฝ์ฐ๊ฐ ์๋ค. 


์ด๋ด ๊ฒฝ์ฐ์ ์์ฑ์ฌ์ ๋ฑ ์ค์๊ธฐ๋ฅ์ ์คํ์ด ์ ์์ ์ผ๋ก ๋์ง ์์ ์ ์๊ธฐ ๋๋ฌธ์, 


setOnClickListener๋ฅผ ์ฌ์ฉํ์ฌ ์์์ ์๊ฐ(5์ด)๋์ ์ค๋ณตํฐ์น๋ฅผ ๋ง๋๋ก ํจ.

```
btnDisabledUnlock.setOnClickListener(object : View.OnClickListener {

    private var mLastClickTime: Long = 0

    override fun onClick(v: View) {

        if (SystemClock.elapsedRealtime() - mLastClickTime > 5000) {
            Log.v("Excuse", "ํฐ์น")
            mLastClickTime = SystemClock.elapsedRealtime()
            count++
            tv2.setText("" + count)

        } else return
        Log.v("Excuse", "์ฐ์ ํฐ์น")

    }
})

```


4๏ธโฃ TTS - TextToSpeach ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ฅผ ์ด์ฉํ์ฌ ์นด๋์ ์์ฑ ๋น์ ๋ฐ์ดํฐ๊ฐ ์์ ์, 


์นด๋์ description์ ์์ฑ์ผ๋ก ์ถ๋ ฅ๊ฐ๋ฅ ํ๋๋ก ํจ.

```
class TTSActivity : AppCompatActivity() {
    private lateinit var tts: TextToSpeech

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_tts)

        tts = TextToSpeech(applicationContext,
            TextToSpeech.OnInitListener { status ->
                if(status == TextToSpeech.SUCCESS){
                    tts.setLanguage(Locale.KOREA).let {
                        if(it == TextToSpeech.LANG_MISSING_DATA
                            || it == TextToSpeech.LANG_NOT_SUPPORTED){
                            Toast.makeText(this@TTSActivity, "์ง๊ธ ์ง์๋์ง ์์ต๋๋ค.", Toast.LENGTH_LONG).show()
                        } else{
                            btnTTS.isEnabled = true
                        }
                    }
                }
            })
            
```
            
            
5๏ธโฃ ์ ๋๋ฉ์ด์

```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <scale
        android:fromXScale="0.8"
        android:fromYScale="0.8"
        android:toXScale="0.0"
        android:toYScale="0.0"
        android:pivotX="50%"
        android:pivotY="50%"
        android:duration="300"
        android:interpolator="@android:anim/linear_interpolator"/>

    <alpha
        android:fromAlpha="1.0"
        android:toAlpha="0.0"
        android:duration="300"
        android:interpolator="@android:anim/accelerate_interpolator"/>
</set>

```


6๏ธโฃ Sort(๋ณด์ด๋ ์, ๋น๋์, ์ด๋ฆ์) - ๋ฐ๋ฌ์ฅ์ ์ธ์ ๋ณดํธ์๊ฐ ์นด๋๋ฅผ ์ ๋ ฌํ๋ ๊ธฐ๋ฅ.


๋ฐ๋ฌ์ฅ์ ์ธ์๊ฒ ๋ณด์ด๋ ์์, ๋ฐ๋ฌ์ฅ์ ์ธ์ด ์์ฃผ ์ฌ์ฉํ๋ ์์, ์นด๋์ ์ด๋ฆ ์์ผ๋ก ์ ๋ ฌ ๊ฐ๋ฅ

```
private fun dataSort(sortStandard: Int) {
    when (sortStandard) {
        SORT_BY_VISIBILITY -> dummyData.sortByDescending { it.visibility }
        SORT_BY_COUNT -> dummyData.sortByDescending { it.count }
        SORT_BY_TITLE -> dummyData.sortBy { it.title }
        else -> "Wrong Standard Flag".logDebug(activity!!.baseContext)
    }
    selectSortAdapter.notifyDataSetChanged()
}

```


7๏ธโฃ Searching - ์นด๋์ Title์ ๊ฒ์ ํ  ์ ์๋ ๊ธฐ๋ฅ(์๋ฌธ ๋์๋ฌธ์ ํฌํจ)


```
    override fun getFilter(): Filter {
        return object : Filter() {
            override fun performFiltering(charSequence: CharSequence): FilterResults {
                val charString = charSequence.toString()
                if (charString.isEmpty()) {
                    searchedList = data
                } else {
                    val filteredList = ArrayList<DataHelperSortCard>()
                    //์ด๋ถ๋ถ์์ ์ํ๋ ๋ฐ์ดํฐ๋ฅผ ๊ฒ์
                    for (row in data) {

                        Log.d("search1","search data :  " + row.title.toLowerCase())
                        Log.d("search2","input data " + charString.toLowerCase())
                        if (row.title.toLowerCase().contains(charString.toLowerCase())) {
                            filteredList.add(row)
                        }
                    }
                    searchedList = filteredList
                }
                val filterResults = FilterResults()
                filterResults.values = searchedList
                return filterResults
            }
            override fun publishResults(charSequence: CharSequence, filterResults: FilterResults) {
                Log.d("search3","publishResults")
                searchedList = filterResults.values as ArrayList<DataHelperSortCard>
                notifyDataSetChanged()
            }
        }
    }
}

```


## โ Extention Function โ

โ๏ธ ๋ก๊ทธ ์ถ๋ ฅ
```
fun String.logDebug(any: Any) {
    Log.d(any::class.java.simpleName, this)
}
```
โ๏ธ Activity ์์ฑ
```
fun <T>Context.newStartActivity(toClass: Class<T>){
    val intent = Intent(this, toClass)
    startActivity(intent)
}
```
โ๏ธ์ฐ์ ํด๋ฆญ ๋ฐฉ์ง ๋ฆฌ์ค๋
```
fun View.setOnSingleClickListener(debounceTime: Long = 6000L, action: ()->Unit){
    this.setOnClickListener (object: View.OnClickListener{
	private var lastClickTime: Long = 0

	override fun onClick(p0: View?) {
	    if((SystemClock.elapsedRealtime() - lastClickTime) < debounceTime){
		Log.d("Single Click", "์ฐ์ ํด๋ฆญ ๋ฐ์")
		return
	    }
	    else {
		action()
		lastClickTime = SystemClock.elapsedRealtime()
	    }
	}
    })
}
```
โ๏ธ ํ ์คํธ ์ถ๋ ฅ
```
fun Context.toast(msg: String) {
    Toast.makeText(this, msg, Toast.LENGTH_LONG).show()
}
```
```
fun String.toast(context: Context) {
    Toast.makeText(context, this, Toast.LENGTH_LONG).show()
}
```
โ๏ธ ๊ถํ ์ฒดํฌ
```
fun Context.isPermissionNotGranted(permission: String): Boolean {
    return ContextCompat.checkSelfPermission(this, permission) != PackageManager.PERMISSION_GRANTED
}
```
โ๏ธ ์์คํ์์ ์ดํ๋ฆฌ์ผ์ด์ ํ๊ฒฝ ์ค์  ํ๋ฉด์ผ๋ก ์ด๋
```
fun Context.startSettingActivity() {
    startActivity(Intent().apply {
	action = Settings.ACTION_APPLICATION_DETAILS_SETTINGS
	data = Uri.fromParts("package", packageName, null)
    })
}
```

## โ Lamda์ ์ด์ฉ โ 
```
private fun showSelectVisibility(card: CardBean) {
        dialogBuilder.apply {
            setMessage("๋ณด์ด๋ ์นด๋ ๋ชฉ๋ก์\n๋ฐ๋ก ์ถ๊ฐํ์๊ฒ ์ต๋๊น?")
            setPositiveButton("์ถ๊ฐ") { dialogInterface, _ ->
                card.visibility = true
                requestCardEdit(card, dialogInterface)
            }
            setNegativeButton("์ทจ์") { dialogInterface, _ -> dialogInterface.cancel()}
            setCancelable(false)
            show()
        }
    }
```

## โ ConstraintLayout ์ด์ฉ โ 
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".feature.disabled.DisabledActivity">

    <Button
        android:id="@+id/btnDisabledUnlock"
        android:layout_width="34dp"
        android:layout_height="34dp"
        android:layout_marginStart="16dp"
        android:layout_marginTop="38dp"
        android:background="@drawable/btn_home_lock"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/btnDisabledChangeSort"
        android:layout_width="34dp"
        android:layout_height="34dp"
        android:layout_marginTop="38dp"
        android:layout_marginEnd="16dp"
        android:background="@drawable/btn_home_reload"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <ImageView
        android:id="@+id/img_home_quote_left"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="48dp"
        android:layout_marginEnd="12dp"
        app:layout_constraintEnd_toStartOf="@+id/tvDisabledShowCardText"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/btnDisabledUnlock"
        app:srcCompat="@drawable/img_home_quote_left" />
	... ์ดํ ์๋ต ...
```
