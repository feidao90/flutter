# flutter
flutter for ios


1、安装Flutter SDK
//1.终端中输入以下指令克隆项目
git clone -b beta https://github.com/flutter/flutter.git
//2. 导出到Flutter保存路径
export PATH=`pwd`/flutter/bin:$PATH

由于国内网络限制我们可以通过修改镜像地址来解决, 好在Google良心,专门给我们大陆提供了方案, 终端中一次输入以下命令即可解决

export PUB_HOSTED_URL=https://pub.flutter-io.cn
export FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn
git clone -b dev https://github.com/flutter/flutter.git
export PATH="$PWD/flutter/bin:$PATH"
cd ./flutter
flutter doctor

2、flutter doctor 检测环境执行结果如下

[✓] Flutter (Channel beta, v0.5.1, on Mac OS X 10.13.5 17F77, locale zh-Hans-CN)
[✓] Android toolchain - develop for Android devices (Android SDK 27.0.3)
[!] iOS toolchain - develop for iOS devices (Xcode 9.4.1)
   ✗ libimobiledevice and ideviceinstaller are not installed. To install, run:
       brew install --HEAD libimobiledevice
       brew install ideviceinstaller
[✓] Android Studio (version 3.1)
[!] IntelliJ IDEA Ultimate Edition (version 2018.1.1)
   ✗ Flutter plugin not installed; this adds Flutter specific functionality.
   ✗ Dart plugin not installed; this adds Dart specific functionality.
[!] VS Code (version 1.24.1)
[✓] Connected devices (1 available)

! Doctor found issues in 3 categories.
第一个对勾是说我的Flutter安装没问题
第二个对勾是说我的安卓工具也OK
第三行是说iOS工具没安装好, 具体就是需要安装他提供的两个库 按照他的说法终端执行如下操作

brew install --HEAD libimobiledevice

brew install ideviceinstaller

注意上面这两个东西第一次没安装成功就是因为我网络的原因, 有可能你第一次执行完 flutter doctor 就不会报这个错,  对于网络原因的话我建议大家去
