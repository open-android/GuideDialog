# StepDialog
一行代码实现ofo app首次注册时的步骤控件

# Preview


![](http://upload-images.jianshu.io/upload_images/4037105-792ce84d29b4f98e.gif?imageMogr2/auto-orient/strip)


### 1. 在project的build.gradle添加如下代码(如下图)

	allprojects {
	    repositories {
	        ...
	        maven { url "https://jitpack.io" }
	    }
	}
### 2. 添加依赖
```
dependencies {
     compile 'com.github.open-android:GuideDialog:0.1.0'
}
```

# Usage
```
StepDialog.getInstance()
                .setImages(new int[]{R.drawable.new_user_guide_1, R.drawable.new_user_guide_2, R.drawable.new_user_guide_3, R.drawable.new_user_guide_4})
                .show(getFragmentManager());
```

# API
| API           | 释义           |
| ------------- |:-------------:|
| setPageTransformer      | ViewPager切换动画方式，分为DepthPageTransformer和ZoomOutPageTransformer两种方式 |
|   setCanceledOnTouchOutside    | 点击四周是否取消dialog,默认取消      | 
| setOutsideIsTransparent | 设置背景四周是否透明,调用时需要放到show方法后面      |

## ViewPager的两种切换方式
### DepthPageTransformer方式
#### 示例
```
StepDialog.getInstance()
                        .setImages(new int[]{com.zqg.dialogviewpager.R.drawable.new_user_guide_1, com.zqg.dialogviewpager.R.drawable.new_user_guide_2, com.zqg.dialogviewpager.R.drawable.new_user_guide_3, com.zqg.dialogviewpager.R.drawable.new_user_guide_4})
                        .setPageTransformer(new DepthPageTransformer())
                        .show(getFragmentManager());
```

![](http://upload-images.jianshu.io/upload_images/4037105-08d258e6b4cd2b62.gif?imageMogr2/auto-orient/strip)

### ZoomOutPageTransformer方式
#### 示例
```
StepDialog.getInstance()
                        .setImages(new int[]{com.zqg.dialogviewpager.R.drawable.new_user_guide_1, com.zqg.dialogviewpager.R.drawable.new_user_guide_2, com.zqg.dialogviewpager.R.drawable.new_user_guide_3, com.zqg.dialogviewpager.R.drawable.new_user_guide_4})
                        .setPageTransformer(new ZoomOutPageTransformer())
                        .show(getFragmentManager());
```

![](http://upload-images.jianshu.io/upload_images/4037105-e2d0136ba815dfdb.gif?imageMogr2/auto-orient/strip)

