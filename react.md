## Props验证
> 使用propTypes验证，react.PorpTypes提供验证器
## 生命周期
> 生命周期分为3个状态:Mounting、Updating、Unmounting
> 生命周期方法有：
* componentWillMount >渲染前调用
* componentDidMount
* componentWillReceiveProps >初始化render不调用
* shouldComponentUpdate
* componentWillUpdate
* componentDidUpdate
* componentWillUnmount

重写配置：https://github.com/timarney/react-app-rewired



> 安卓打包：
https://reactnative.cn/docs/0.51/signed-apk-android.html#content
* 生成发行apk:gradlew assembleRelease
* 测试发行版本：gradlew installRelease

安装指定版本的rn来初始化项目，初始化的时候显示详情
react-native init demo --verbose --version 0.38.0


> 编译安卓项目
./gradlew :Examples:UIExplorer:android:app:installDebug
/packager/packager.sh

http://blog.csdn.net/hpu_zyh/article/details/50408392

http://www.lcode.org/%E8%B6%85%E8%AF%A6%E7%BB%86windows%E7%89%88%E6%9C%AC%E7%BC%96%E8%AF%91%E8%BF%90%E8%A1%8Creact-native%E5%AE%98%E6%96%B9%E5%AE%9E%E4%BE%8Buiexplorer%E9%A1%B9%E7%9B%AE%E5%A4%9A%E5%9B%BE%E6%85%8E/

## create-react-native-app
> --scripts-version    react-native-scripts-ts||react-native-scripts(默认)
> --package-manager  yarn || npm

## gradle
> settings.gradle

    include  设置子目录

> build.gradle（三个小节点）

* buildscript

    第一个子节点声明仓库源
    第二个子节点声明android gradle plugin版本，

* allprojects

    声明所有project默认的仓库源
    
* task clean
    
    每当修改settings.gradle重新拉取包
    
> app/build.gradle(三个小节点)

* apply
* android

    buildTypes:默认release
    minifyEnabled:是否需要混淆
    proguardFiles:表示混淆配置文件的名称
    productFlavors:表示多渠道包

* dependencies

    引用包
