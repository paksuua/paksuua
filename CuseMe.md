<div align="center" style="display:flex;">
	<img src="https://user-images.githubusercontent.com/39257919/71553942-423e6f80-2a5b-11ea-972f-364c5b896b60.png">
</div>
<div align="center">
🗣 CUSE ME_SERVER  💻
<br>발달장애인을 위한 카드형 의사소통도구, 큐즈미
</div>

---
발달장애인들에게 세상은 넓고 깊은 바다와 같습니다.<br> 
말이 통하지 않는 사람들로 가득한 세상은 그들에겐 함부로 나아가기 어렵고, 무서운 곳이니까요.<br> 
 **우리는 발달장애인들도 넓은 세상을 자유롭게 헤엄칠 수 있기를 바랍니다.** 
<br> 우리와 최소한의 의사소통이 가능하다면, 발달장애인의 세상도 조금은 넓어지지 않을까요?

&nbsp;

```
💕	약자가 배제되지 않는 세상을 꿈꿉니다.
	일상에서 말이 통하지 않는다는 이유로 세상을 포기하지 않았으면 좋겠습니다.
```
```
💕	이 앱을 마주할 모든 사용자를 생각했습니다.
	발달장애인 뿐만 아니라 보호자, 이 앱을 마주할 비장애인들을 모두 고려한 UX
```
```
💕	기존 앱보다 사용성을 높였습니다.
	TTS(Text To Speach), 음성 녹음, 카드 공유 기능
```

------
### 📄 Service Work Flow
![큐즈미_워크플로우-1](https://user-images.githubusercontent.com/43192041/71722846-ccc50b80-2e6d-11ea-9385-5c8e0f581dba.png)

# CuseMe_Android :loudspeaker:

### 📚 1.프로젝트 사용 라이브러리
👉Retrofit - 서버통신
    
```       
    implementation 'com.squareup.retrofit2:retrofit:2.6.2'
    implementation 'com.google.code.gson:gson:2.8.6'
``` 

👉CardView - 아이템(카드) 디자인 적용
```
    implementation 'androidx.cardview:cardview:1.0.0'
    implementation 'com.google.android.material:material:1.0.0'
```

👉Fragment - 페이지 전환
```
    implementation "androidx.navigation:navigation-fragment-ktx:2.1.0-alpha05"
    implementation "androidx.navigation:navigation-ui-ktx:2.1.0-alpha05"
```
    
👉RecyclerView - 아이템 스크롤
```
    implementation 'androidx.recyclerview:recyclerview:1.1.0'
```
    
👉Glide - 이미지 사용
```
    implementation 'com.github.bumptech.glide:glide:4.9.0'
    annotationProcessor 'com.github.bumptech.glide:compiler:4.9.0'
```
### 📚 2.프로젝트 구조

|                  Activity                              |                 Description   |
| ----------------------------------- | ------------------------------------------- |
| DisabledActivity                                 |  도움 요청과 관련한 이미지, 설명, 음성이 나타남    |
| UnlockActivity  | 잠금 해제시 보호자 관리 페이지     |
| HelperActivity, HelperFragment  |  카드 아이템 클릭시   삭제, 숨기기, 수정, 취소 기능의 하단바 생성  |
| DetailCardActivity  | 카드의 이미지, 숨김여부, 일렬번호, 제목, 설명, 카드 사용시 보호자알림 전송 여부, 음성 듣기  |
| HelperSortFragment  |  카드의 보이는 순, 사용 빈도 순, 이름 순으로 카드 정렬    |
| ManagementActivity  | 보호자가 발달 장애인이 볼 수 있는 카드를 선택 및 정렬, 발달장애인이 볼 수 있는 카드를 삭제, 숨기기, 수정  |
| DownloadCardActivity  | 카드의 일련번호를 통해서 새로운 카드를 다운  |
| DetailCardActivity  | 카드의 세부사항(제목, 내용, 음성, 이미지)를 확인  |
| AddCardActivity  | 카드의 제목, 내용, 음성, 이미지를 넣고 새로운 카드 생성  |
| ModCardActivity  | 카드의 제목, 내용, 음성, 이미지를 수정  |
| Setting Activity   | 보호자의 비밀번호 변경, 전화번호 설정  |


### 📚 3.핵심 기능 구현


1️⃣ Zoom In / Zoom Out : 카드의 사이즈를 변경 할 수 있는 기능  


터치되는 아이템의 위치를 기준으로 확대, 축소 되도록하며 1줄에 1-3개까지 정렬 가능하도록 제한함.

```
val mScaleGestureDetector = ScaleGestureDetector(
    this,
    object : ScaleGestureDetector.SimpleOnScaleGestureListener() {
        override fun onScale(detector: ScaleGestureDetector): Boolean {
            Log.v("Excuse", "줌2")

            if (detector.currentSpan > 200 && detector.timeDelta > 200) {

                // 2에서 3
                if (detector.currentSpan - detector.previousSpan < -1) {
                    if (mCurrentLayoutManager == gridManager2) {
                        mCurrentLayoutManager = gridManager3
                        rvDisabledCard.layoutManager = mCurrentLayoutManager
                        rvDisabledCard.scrollToPosition(position)
                        return true

                        //1에서 2
                    } else if (detector.currentSpan - detector.previousSpan < -1) {
                        if (mCurrentLayoutManager == gridManager1) {
                            mCurrentLayoutManager = gridManager2
                            rvDisabledCard.layoutManager = mCurrentLayoutManager
                            rvDisabledCard.scrollToPosition(position)
                            return true
                        }
                    }
                }
                //3에서 2
            } else if (detector.currentSpan - detector.previousSpan > 1) {
                if (mCurrentLayoutManager == gridManager3) {
                    mCurrentLayoutManager = gridManager2
                    rvDisabledCard.layoutManager = mCurrentLayoutManager
                    rvDisabledCard.scrollToPosition(position)
                    return true

                    //2에서 1
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


2️⃣ Long Click / Drag&Drop - DramanageAdapter를 사용하여 


사용자의 Long Click, Drag&Drop을 감지하고, 카드의 순서를 swap 가능하도록 함.

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
        // 사용안함
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



3️⃣ 중복 터치 방지 - 발달장애인의 경우 기능을 실행하기 위하여 여러번 중복하여 터치하는 경우가 있다. 


이럴 경우에 음성재생 등 중요기능의 실행이 정상적으로 되지 않을 수 있기 때문에, 


setOnClickListener를 사용하여 임의의 시간(5초)동안 중복터치를 막도록 함.

```
btnDisabledUnlock.setOnClickListener(object : View.OnClickListener {

    private var mLastClickTime: Long = 0

    override fun onClick(v: View) {

        if (SystemClock.elapsedRealtime() - mLastClickTime > 5000) {
            Log.v("Excuse", "터치")
            mLastClickTime = SystemClock.elapsedRealtime()
            count++
            tv2.setText("" + count)

        } else return
        Log.v("Excuse", "연속 터치")

    }
})

```


4️⃣ TTS - TextToSpeach 라이브러리를 이용하여 카드의 음성 녹음 데이터가 없을 시, 


카드의 description을 음성으로 출력가능 하도록 함.

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
                            Toast.makeText(this@TTSActivity, "지금 지원되지 않습니다.", Toast.LENGTH_LONG).show()
                        } else{
                            btnTTS.isEnabled = true
                        }
                    }
                }
            })
            
```
            
            
5️⃣ 애니메이션

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


6️⃣ Sort(보이는 순, 빈도순, 이름순) - 발달장애인의 보호자가 카드를 정렬하는 기능.


발달장애인에게 보이는 순서, 발달장애인이 자주 사용하는 순서, 카드의 이름 순으로 정렬 가능

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


7️⃣ Searching - 카드의 Title을 검색 할 수 있는 기능(영문 대소문자 포함)


```
    override fun getFilter(): Filter {
        return object : Filter() {
            override fun performFiltering(charSequence: CharSequence): FilterResults {
                val charString = charSequence.toString()
                if (charString.isEmpty()) {
                    searchedList = data
                } else {
                    val filteredList = ArrayList<DataHelperSortCard>()
                    //이부분에서 원하는 데이터를 검색
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


## ✅ Extention Function ✅

✔️ 로그 출력
```
fun String.logDebug(any: Any) {
    Log.d(any::class.java.simpleName, this)
}
```
✔️ Activity 생성
```
fun <T>Context.newStartActivity(toClass: Class<T>){
    val intent = Intent(this, toClass)
    startActivity(intent)
}
```
✔️연속 클릭 방지 리스너
```
fun View.setOnSingleClickListener(debounceTime: Long = 6000L, action: ()->Unit){
    this.setOnClickListener (object: View.OnClickListener{
	private var lastClickTime: Long = 0

	override fun onClick(p0: View?) {
	    if((SystemClock.elapsedRealtime() - lastClickTime) < debounceTime){
		Log.d("Single Click", "연속 클릭 발생")
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
✔️ 토스트 출력
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
✔️ 권한 체크
```
fun Context.isPermissionNotGranted(permission: String): Boolean {
    return ContextCompat.checkSelfPermission(this, permission) != PackageManager.PERMISSION_GRANTED
}
```
✔️ 시스템에서 어플리케이션 환경 설정 화면으로 이동
```
fun Context.startSettingActivity() {
    startActivity(Intent().apply {
	action = Settings.ACTION_APPLICATION_DETAILS_SETTINGS
	data = Uri.fromParts("package", packageName, null)
    })
}
```

## ✅ Lamda식 이용 ✅ 
```
private fun showSelectVisibility(card: CardBean) {
        dialogBuilder.apply {
            setMessage("보이는 카드 목록에\n바로 추가하시겠습니까?")
            setPositiveButton("추가") { dialogInterface, _ ->
                card.visibility = true
                requestCardEdit(card, dialogInterface)
            }
            setNegativeButton("취소") { dialogInterface, _ -> dialogInterface.cancel()}
            setCancelable(false)
            show()
        }
    }
```

## ✅ ConstraintLayout 이용 ✅ 
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
	... 이하 생략 ...
```
