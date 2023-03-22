# 如何在实验平台View中添加自定义功能

## 1添加自定义按钮“测试”

1.1添加宏定义

找到Resource.h文件，在这里面添加一条宏定义，如下图：

<img src="https://raw.githubusercontent.com/Ninot1Quyi/Typora-s-picture/master/img/image-20230321130641523.png" alt="image-20230321130641523" style="zoom:50%;" />

1.2找到“Experiment_Frame_one.clw”文件，找到下图内容并添加。

注意添加一个内容：

```.clw
Command6=TEST
```

修改一个内容

```
CommandCount=6
```

<img src="https://raw.githubusercontent.com/Ninot1Quyi/Typora-s-picture/master/img/image-20230321130949138.png" alt="image-20230321130949138" style="zoom:50%;" />

1.3找到文件“Experiment_Frame_One.rc”，在第420行处添加

```
    TEST                    "测试"
```

如图所示：

<img src="https://raw.githubusercontent.com/Ninot1Quyi/Typora-s-picture/master/img/image-20230321131304503.png" alt="image-20230321131534984" style="zoom:50%;" />



1.4为这个按钮“测试”添加函数声明：

找到文件“Experiment_Frame_OneView.h”，在第67行添加相关函数的声明：

```cpp
	afx_msg void OnTEST();
```

如图所示：

<img src="https://raw.githubusercontent.com/Ninot1Quyi/Typora-s-picture/master/img/image-20230321131534984.png" alt="image-20230321131923740" style="zoom:50%;" />

1.5找到文件“Experiment_Frame_OneView.cpp”，在大概248行左右的位置添加刚刚声明的函数的实现

```cpp
void CExperiment_Frame_OneView::OnTEST() 
{
	//实现“测试”功能

}
```

<img src="https://raw.githubusercontent.com/Ninot1Quyi/Typora-s-picture/master/img/image-20230321131923740.png" alt="image-20230321132115122" style="zoom:50%;" />

1.6保存所有文件，回到VC++6，根据提示选择重新加载代码，然后F5，左上角出现“测试”按钮

<img src="https://raw.githubusercontent.com/Ninot1Quyi/Typora-s-picture/master/img/image-20230321132115122.png" alt="image-20230321131304503" style="zoom:50%;" />

