Android layer-list

```xml
<?xml version="1.0" encoding="utf-8"?><layer-list xmlns:android="http://schemas.android.com/apk/res/android">    
	<item android:id="@android:id/background">        
		<shape>
        	<corners android:radius="5dp"/>            
        	<solid android:color="#FF9E9E9E" />       
		</shape>    
	</item>    
	<item android:id="@android:id/progress">        
		<clip>            
			<shape>                
				<corners android:radius="5dp" />                
				<solid android:color="#FF2962FF" />            
			</shape>        
		</clip>    
	</item>
</layer-list>
```

```java
Drawable[] layers = new Drawable[2];
Drawable background = mContext.getResources().getDrawable(R.drawable.progress_background);
GradientDrawable progress = (GradientDrawable) mContext.getResources().getDrawable(R.drawable.progress_progress);
		 progress.setColor(mContext.getResources().getColor(R.color.red));
ClipDrawable clip = new ClipDrawable(progress,Gravity.LEFT, ClipDrawable.HORIZONTAL);
layers[0] = background;
layers[1] = clip;
LayerDrawable layer=new LayerDrawable(layers );
layer.setId(0, android.R.id.background);
layer.setId(1, android.R.id.progress);
mBbPlay.setProgressDrawable(layer);
```

```java
LayerDrawable layerDrawable =(LayerDrawable)mBbPlay.getProgressDrawable();
Drawable draw = layerDrawable.findDrawableByLayerId(android.R.id.progress);
GradientDrawable progress;
if(draw == null || !(draw instanceof ColorDrawable)){
	progress = (GradientDrawable) mContext.getResources().getDrawable(R.drawable.progress_progress);
	draw = new ColorDrawable(progress, Gravity.LEFT, ClipDrawable.HORIZONTAL);
	layerDrawable.setDrawableByLayerId(android.R.id.progress, draw);
}else{
	progress = ((ColorDrawable)draw).progress;
}
progress.setColor(mContext.getResources().getColor(R.color.red));
```

