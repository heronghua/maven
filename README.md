--私有maven 仓库--

使用方法：
在Project 的build.gradle 下添加如下依赖库代码
allprojects {
    repositories {
        google()
        jcenter()
        maven {
            url "https://raw.githubusercontent.com/heronghua/maven/snapshot"
        }
    }
}

其中 snapshot 是branch 名称，maven 是仓库名称

之后在需要引用的app moudle 的buidl.gradle 里面添加 引用maven 引用代码
implementation 'com.bestwise:libtest:1.0@aar'，maven 会在snapshot这个分支上根据groupId 进入到 com/bestwise 这个目录然后再根据artifactId：libtest 进入到libtest 这个文件夹，然后再根据version 进入到1.0 这个文件夹，之后找到 libtest-1.0.aar 这个文件
