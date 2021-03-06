# pitfalls-android

<img src="logo-pitfalls-android.png" width="" height="200"/>

#### 其他 pitfalls 系列：[Pitfalls Series](https://github.com/42Chapters/pitfalls)

### 1.如何进行仓库内容预览与搜索？

**预览：GitBook [pitfalls-android @ GitBook](https://42chapters.gitbook.io/pitfalls-android/)**

备注：GitBook 更新了新版样式，没有之前的样式好看（之前的样式参考：[http://android.developerdocumentation.cn](http://android.developerdocumentation.cn)），而且在 URL 路径上面的处理不太一样了，不像之前一样是通过你的文件夹和文件名来匹配，而是分析首行文字，如果是中文的话，会转化成中文对应的拼音，我觉得这个做法很难受，不喜欢这种“自以为是”的处理方式，相当于我们想要自定义 URL 的话，我的首行文字必须要和 URL 一样的内容。新用户注册 GitBook 已经是强制要求使用新的样式了，老用户如果你在组织底下点击升级到新的 GitBook，就回不去了。但是个人账号底下还是可以采用旧的样式，可以通过访问 legacy.gitbook.com 的方式来处理。新版本目前唯一的亮点就是增强了搜索功能。

**后期我们可以在自己的服务器架设 GitBook 服务，采用之前的样式。**

![](/img/new-gitbook-search.png)

**搜索：在 GitHub 中搜索当前仓库，在 GitBook 中搜索当前电子书（推荐）。**

### 2.这个仓库是做什么的？

`pitfall：n.陷阱；圈套；诱惑；` 在 pitfalls-android 中，我们可以将 pitfall 理解为“坑”的意思。此仓库是用来记录 Android 开发者在实际开发过程中所遇到“坑”以及“坑”解决方法，也为其他 Android 开发者提供相关的参考，避免再次掉“坑”里。

### 3.如何参与贡献此仓库？

#### 1°. 评估所提交“坑”的所属分类：

该“坑”属于 SDK/IDE/Third-Party Library/... 哪一个，追加到对应的文件中。如果不清楚属于哪个分类，可以提交到：`temporary-contribution.md` 中，仓库管理员会再次评估分类。

#### 2°. 统一提交的文本格式：

文本排版格式要求参照：[中文文案排版指北](https://github.com/sparanoid/chinese-copywriting-guidelines)

**参考格式：**

***
### 1.[问题关键内容描述]

#### 环境参数：

[参数描述]

#### 问题分析：

[分析描述]

#### 解决方法：

[方法描述]
***

**参考 Markdown 语言格式：**

***
```
### 1.[问题关键内容描述]

#### 环境参数：

[参数描述]

#### 问题分析：

[分析描述]

#### 解决方法：

[方法描述]
```
***

**参考样例 A：gradle.md**
*** 
### 1.Execution Failed for task :app:compileDebugJavaWithJavac

#### 环境参数：

```  
System:macOS High Sierra Version 10.13
IDE:Android Studio 3.1
Gradle:2.10
Gradle Plugin:2.1.2
```

#### 问题分析：

Gradle 构建的时候出现编译错误，但是没有得到具体的错误提示信息，所以我们需要通过特殊手段来获取更多有用的细节信息。


#### 解决方法：

通过以下常用的 Gradle 命令，可以获得更多有用的细节信息提示：

```
*clean project
./gradlew clean  

*build project
./gradlew build

*build for debug package
./gradlew assembleDebug or ./gradlew aD

*build for release package
./gradlew assembleRelease or ./gradlew aR

*build for release package and install
./gradlew installRelease or ./gradlew iR Release

*build for debug package and install
./gradlew installDebug or ./gradlew iD Debug

*uninstall release package
./gradlew uninstallRelease or ./gradlew uR

*uninstall debug package
./gradlew uninstallDebug or ./gradlew uD 

*all the above command + "--info" or "--debug" can get more detail information.
```

***

**参考样例 B：android-studio.md**
***
### 1.Android Studio Debug 模式不可用。

#### 环境参数：

```  
System:macOS High Sierra Version 10.13
IDE:Android Studio 3.1
Gradle:2.10
Gradle Plugin:2.1.2
```

#### 问题分析：

原因未知。

#### 解决方法：

可采用以下方法解决尝试解决：  
1).重启 Android Studio  
2).重启 macOS  
3).重装 Android Studio
***


#### 3°. 一般原则：

A.能用图片的情况下，不要用视频。能用文本的情况下，不要用图片。  
B.使用原始错误提示来作为问题关键内容描述，这个更方便别人查找参考。  
C.有代码内容的部分，请使用代码块。  
D.**如果想要引入视频和大量的图片，请引入外部链接。如果想要引入图片，少量的可以放置在 `img/` 目录底下，图片文件采用全部小写字母、横杠的命名方式。**  
E.**代码的引入方式有两种，一种是采用双"```"引入，另外一种是采用缩进方式引入，为了保持格式的美观，我们统一采用前者方式，而不采用缩进的方式引入代码。**

#### 4°. 目录结构和文件名称要求：

仓库管理者请注意，所有的目录和文件名称，除了特殊情况之外，全部采用小写字母与横杠的组合。每一层目录底下包含一个 `README.md` 文件，如果当前内容（比如：exception）没有下一级目录细分的话，就将包含内容的文件名称命名成：`exception.md`。



#### 5°. 不适合提交的内容：

非 Android 内容，非 Android “坑”内容，例如：小知识点、专题总结等。本仓库只接受 Android 的“坑”并且包含解决方法的总结。


### 4.已有内容索引

* [序言](README.md)
* [应用市场](app-store/README.md)
	* [Google Play](app-store/google-play.md)
	* [百度市场](app-store/baidu.md)
       * [360市场](app-store/360.md)
* [编程语言](programming-language/README.md)
	* [Java](programming-language/java.md)
	* [Kotlin](programming-language/kotlin.md)
	* [Dart](programming-language/dart.md)
* [IDE](ide/README.md)
	* [Android Studio](ide/android-studio/README.md)
		* [Gradle](ide/android-studio/gradle.md)
* [SDK](sdk/README.md)
	* [UI](sdk/ui.md)
	* [异常](sdk/exception.md)
	* [错误](sdk/error.md)
* [Apk 安装包](apk/README.md)
* [第三方库](third-party-library/README.md)
	* [Tinker](third-party-library/tinker.md)  


