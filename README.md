# flutter 安装


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

iOS setup

Install Xcode

To develop Flutter apps for iOS, you need a Mac with Xcode 9.0 or newer:

Install Xcode 9.0 or newer (via web download or the Mac App Store).
Configure the Xcode command-line tools to use the newly-installed version of Xcode by running the following from the command line:

$ sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer
This is the correct path for most cases, when you want to use the latest version of Xcode. If you need to use a different version, specify that path instead.

Make sure the Xcode license agreement is signed by either opening Xcode once and confirming or running sudo xcodebuild -license from the command line.
With Xcode, you’ll be able to run Flutter apps on an iOS device or on the simulator.

Set up the iOS simulator

To prepare to run and test your Flutter app on the iOS simulator, follow these steps:

On your Mac, find the Simulator via Spotlight or by using the following command:

$ open -a Simulator
Make sure your simulator is using a 64-bit device (iPhone 5s or later) by checking the settings in the simulator’s Hardware > Device menu.
Depending on your development machine’s screen size, simulated high-screen-density iOS devices may overflow your screen. Set the device scale under the Window > Scale menu in the simulator.
Start your app by running flutter run.
Deploy to iOS devices

To deploy your Flutter app to a physical iOS device, you’ll need some additional tools and an Apple account. You’ll also need to set up physical device deployment in Xcode.

Install homebrew.
Ensure that homebrew is up to date:

$ brew update
Install the tools for deploying Flutter apps to iOS devices by running the following commands:

$ brew install --HEAD usbmuxd
$ brew link usbmuxd
$ brew install --HEAD libimobiledevice
$ brew install ideviceinstaller ios-deploy cocoapods
$ pod setup
 Note: The first two commands above are necessary as a temporary workaround until the next release of libusbmuxd, as explained in libusbmuxd issue #46 and Flutter issue #22595.
If any of these commands fail, run brew doctor and follow the instructions to resolve any issues.

Follow the Xcode signing flow to provision your project:

Open the default Xcode workspace in your project by running open ios/Runner.xcworkspace in a terminal window from your Flutter project directory.
In Xcode, select the Runner project in the left navigation panel.
In the Runner target settings page, make sure your Development Team is selected under General > Signing > Team. When you select a team, Xcode creates and downloads a Development Certificate, registers your device with your account, and creates and downloads a provisioning profile (if needed).

To start your first iOS development project, you may need to sign into Xcode with your Apple ID. 
Xcode account add
Development and testing is supported for any Apple ID. Enrolling in the Apple Developer Program is required to distribute your app to the App Store. For details about membership types, see Choosing a Membership.

The first time you use an attached physical device for iOS development, you will need to trust both your Mac and the Development Certificate on that device. Select Trust in the dialog prompt when first connecting the iOS device to your Mac.

Trust Mac

Then, go to the Settings app on the iOS device, select General > Device Management and trust your Certificate.

If automatic signing fails in Xcode, verify that the project’s General > Identity > Bundle Identifier value is unique. 
Check the app's Bundle ID

Start your app by running flutter run.

