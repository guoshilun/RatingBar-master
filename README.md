# RatingBar

##[中文版][3]
##a custom Ratingbar in android
![image](https://github.com/hedge-hog/RatingBar/blob/master/ic_demo.png)

# How to use
###Android Studio：
```groovy
    dependencies {
        compile 'com.hedgehog.ratingbar:app:1.1.2'
    }
```
###1，In xml

    <com.hedgehog.ratingbar.RatingBar
        android:id="@+id/ratingbar"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:layout_gravity="center"
        android:layout_marginTop="50dp"
        hedgehog:clickable="true"
        hedgehog:halfstart="true"
        hedgehog:starCount="5"
        hedgehog:starEmpty="@mipmap/star_empty"
        hedgehog:starFill="@mipmap/star_full"
        hedgehog:starHalf="@mipmap/star_half"
        hedgehog:starImageHeight="90dp"
        hedgehog:starImageWidth="70dp"
        hedgehog:starImagePadding="20dp"/>
      

###method statement
| method|    action | 
| :-------- | :--------|
|hedgehog:clickable="true"   |Could you click|
|hedgehog:halfstart="true"|Whether to support half a star|
|hedgehog:starCount="N"|The total number of stars （int）|
|hedgehog:starEmpty="@mipmap/star_empty"|empty star|
|hedgehog:starFill="@mipmap/star_full"|full star|
|hedgehog:starHalf="@mipmap/star_half"|half star|
|hedgehog:starImageHeight="90dp"|the height of the stars|
|hedgehog:starImageWidth="70dp"|the width of the star|
|hedgehog:starImagePadding="20dp"|the padding of the star|
###Don't forget to namespace

```
xmlns:hedgehog="http://schemas.android.com/apk/res-auto"
```
###2，In Java code

    ```
       RatingBar mRatingBar = (RatingBar) findViewById(R.id.ratingbar);
        mRatingBar.setStarEmptyDrawable(getResources().getDrawable(R.mipmap.star_empty));
        mRatingBar.setStarHalfDrawable(getResources().getDrawable(R.mipmap.star_half));
        mRatingBar.setStarFillDrawable(getResources().getDrawable(R.mipmap.star_full));
        mRatingBar.setStarCount(5);
        mRatingBar.setStar(2.5f);
        mRatingBar.halfStar(true);
        mRatingBar.setmClickable(true);
        mRatingBar.setStarImageWidth(120f);
        mRatingBar.setStarImageHeight(60f);
        mRatingBar.setImagePadding(35);
        mRatingBar.setOnRatingChangeListener(
                new RatingBar.OnRatingChangeListener() {
                    @Override
                    public void onRatingChange(float RatingCount) {
                        Toast.makeText(MainActivity.this, "the fill star is" + RatingCount, Toast.LENGTH_SHORT).show();
                    }
                }
        );

        ```

###method statement
| method      |    action | 
| :-------- | :--------:|
|mRatingBar.setStarCount(5);|The total number of stars|
|mRatingBar.setStar(2.5f);|Fill the total number of the stars|
|mRatingBar.halfStar(true);|Whether set up half a star|
|mRatingBar.setmClickable(true);|Whether the Settings can be click|
|mRatingBar.setStarImageWidth(120f);|the width of the stars|
|mRatingBar.setStarImageHeight(60f);|the height of the stars|
|mRatingBar.setImagePadding(35);|the padding of the stars|


#about
Because the project need this function, but the android itself on the propagation of the Ratingbar support is very bad, so intend to write their own a, because my ability is limited, a lot of the function is not perfect, if you have a better solution, welcome to tell me, thank you

#unsolved
- You can set the padding between the stars，But because the Ratingbar is rewriting Imageview, so distance setting still need to fine tune
- You can set up half a star，but this method is very bad，Using this method is not recommended，Look at the code if you want to know the details，Please let me know if you have a good solution


#Thank
Thanks the  [Android_custom_ratingbarview][1] You can look at it  
Thanks[lingguohui][2]for his code

[1]:https://github.com/JackWong025/Android_custom_ratingbarview
[2]:https://github.com/lingguohui
[3]:https://github.com/hedge-hog/RatingBar/blob/master/README_CH.md

#License
```
Copyright 2015 hedge_hog

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
