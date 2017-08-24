# 百度地图官方Demo

## 申请AK

参考：https://github.com/YoungBear/BaiduLocDemo/blob/master/README.md

## 配置release编译

```
    signingConfigs {
        release {
            keyAlias 'ysx_test_alias'
            keyPassword '123456'
            storeFile file('ysx_test.jks')
            storePassword '1qaz2wsx'
        }
        debug{
            storeFile file("debug.keystore")
        }
    }

    buildTypes {
        release {
            minifyEnabled true
            proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
            signingConfig signingConfigs.release
            debuggable false
        }
    }
```

## 添加混淆忽略

app/proguard-rules.pro

```
# for baidu start
-keep class com.baidu.** {*;}
-keep class vi.com.** {*;}
-dontwarn com.baidu.**
# for baidu end
```

## 生成release包

```
./gradlew assembleRelease
```

默认路径为：

```
app/build/outputs/apk
```
