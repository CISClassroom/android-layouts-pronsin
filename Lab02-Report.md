# รายงานผลการทดลอง

<นาย พรสิน มีสีบู>

## Relative Layout

แสดง Control `title` และ `Detail`

```xml
android:layout_alignParentTop="true"
        android:layout_alignParentEnd="true"
```

แอดทริบิ้วที่แสดงความสัมพันธ์ระหว่าง control ทั้งสอง
    RelativeLayout คือ View Group ตัวหนึ่งที่เอาไว้สำหรับแสดง Child View โดยที่การจัดเรียงกันจะมีความสัมพันธ์หรือเกี่ยวข้องกัน เช่น
TextView 1 ตัว จะต้องเกี่ยวข้องกับ Parent View ของมัน เช่น อยู่ขวามือของ Parent View หรือ อยู่กึ่งกลาง Parent View
TextView ตัวแรก อาจจะสัมพันธ์กับ TextView ตัวที่สองคือ ตั้งค่าให้ TextView ตัวแรก อยู่บน ตัวสอง ฉะนั้น หากเราขยับ TextView ตัวสองไปไหน ตัวแรกมันก็จะขยับตามไปอยู่ด้านบนตลอด
จะเห็นว่า RelativeLayout ต่างจาก LinearLayout โดยสิ้นเชิง เนื่องจากว่า LinearLayout จะเรียงกันแบบเป็นลำดับ ไม่เป็นแนวตั้ง ก็แนวนอนเท่านั้น

```xml
 android:layout_alignParentEnd="true"
        android:layout_alignParentBottom="true"
```

## Linear Layout

แสดง Control `to`, `subject`, `tag` และ `message`

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".LinearLayoutActivity3">

    <LinearLayout
        android:id="@+id/linearLayout2"
        android:layout_width="408dp"
        android:layout_height="74dp"
        android:orientation="horizontal"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="1.0" >

        <Button
            android:id="@+id/button6"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="Button" />
    </LinearLayout>

    <LinearLayout
        android:layout_width="409dp"
        android:layout_height="652dp"
        android:orientation="vertical"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.0" >

        <TextView
            android:id="@+id/textView14"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="เกมที่ชอบ ?"
            android:textSize="38sp" />

        <EditText
            android:id="@+id/editText2"
            android:layout_width="match_parent"
            android:layout_height="177dp"
            android:ems="10"
            android:inputType="textPersonName"
            android:text="เพราะอะไร ?" />
    </LinearLayout>

</androidx.constraintlayout.widget.ConstraintLayout>
```
อธิบายความแตกต่างระหว่าง vertical และ horizontal orientation

```
// คำตอบ vertical คือจัดเรียงให้อยู่ในเเนวตั้ง ส่วน horizontal orientation จัดเรียนให้อยู่ในแนวนอน
```

## Constrant Layout

จงออกแบบและสร้างหน้า Constrant layout สำหรับแสดงข้อมูลนักศึกษา ประกอบไปด้วย รูปโปรไฟล์ รูปพื้นหลัง ชื่อ-นามสกุล รหัสนักศึกษา และเกรดเฉลี่ยรวม

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.coordinatorlayout.widget.CoordinatorLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".ConstrantLayoutActivity">

    <com.google.android.material.appbar.AppBarLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:theme="@style/AppTheme.AppBarOverlay">

        <androidx.appcompat.widget.Toolbar
            android:id="@+id/toolbar"
            android:layout_width="match_parent"
            android:layout_height="?attr/actionBarSize"
            android:background="?attr/colorPrimary"
            app:popupTheme="@style/AppTheme.PopupOverlay" />

    </com.google.android.material.appbar.AppBarLayout>

    <include layout="@layout/content_constrant_layout" />

    <com.google.android.material.floatingactionbutton.FloatingActionButton
        android:id="@+id/fab"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="bottom|end"
        android:layout_margin="@dimen/fab_margin"
        app:srcCompat="@android:drawable/ic_dialog_email" />

</androidx.coordinatorlayout.widget.CoordinatorLayout>
```
