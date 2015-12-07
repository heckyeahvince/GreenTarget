# Greet Target ( Custom View Demo) 

This assignment illustrates the creation of a custom view and basic drawing in Android.


## Problem:

Design and implement a target (drawing) custom view.   

## Keypoints:

Custom view GreenTarget.java:  
```Java
public class GreenTarget extends View {

    public GreenTarget(Context context, AttributeSet attrs) {
        super(context, attrs);
    }

    @Override
    protected void onDraw(Canvas canvas) {
        super.onDraw(canvas);

        Paint green = new Paint();
        green.setARGB(255, 0, 255, 0);

        Paint white = new Paint();
        white.setARGB(255, 255, 255, 255);

        // Get center
        int w = canvas.getWidth();
        int h = canvas.getHeight();
        int x = (w < h)? w : h;

        for (int i = 0; i < 11; i++) {
            canvas.drawCircle(w/2, h/2, x*(10-i)/20, i % 2 == 0 ? green : white);
        }
    }

}
```

In the layout xml:
```xml
    <com.cabatuan.greentarget.GreenTarget
        android:id="@+id/targetview"
        android:layout_height="wrap_content"
        android:layout_width="wrap_content"
        android:layout_centerInParent="true"
        />
```
