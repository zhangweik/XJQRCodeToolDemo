# XJQRCodeToolDemo
XJQRCodeTool工具类


github链接:
https://github.com/lishengbing/XJQRCodeToolDemo

my.oschina.com链接：<友情推荐>
https://my.oschina.net/shengbingli/blog/753400
https://github.com/lishengbing/XJDragViewController


核心工具类:
QRCodeTool.swift



                  >>>支持最新swift3.0、全新二维码生成、识别、扫描<<<

>>>>>>>生成二维码一键调用：
override func touchesBegan(_ touches: Set<UITouch>, with event: UIEvent?) {
view.endEditing(true)
let str = qrCodeTextTV.text ?? "XJDomain"
let resultImage =  QRCodeTool.generatorQRCode(inputStr: str, centerImage: UIImage(named: "default_header"))
qrCodeImageView.image = resultImage
}


>>>>>>识别二维码一键调用:
guard let image = sourceImageView.image else { return }
let result = QRCodeTool.detectorQRCode(image: image, isDrawQRCodeFrame: true)
let strArr = result.resultStrs
let resultImage = result.resultImage
sourceImageView.image = resultImage



>>>>>>扫描二维码一键调用、增加蒙板蒙边、聚焦描边、扫描区域限定等功能
override func viewDidLoad() {
super.viewDidLoad()

starScanAnimation()
QRCodeTool.shareInstance.starScanQRCode(inView: view, isDrawFrame: true) { (resultStrs) in
print("--------",resultStrs)
}
QRCodeTool.shareInstance.setScanRectInterest(origenViewRect: scanBgView.frame)
}



>>>>>>最后这里⚠️:扫描只能真机测试
打开视频必须配置plist文件相应key : NSCameraUsageDescription
打开照片也需要配置plist文件响应的key : NSPhotoLibraryUsageDescription

>>>>>>使用的话：直接将我的工具类拷贝你的项目中就可以使用了,特别是扫描功能，因为是使用xib拖线控件的，也方便开发者任意更改自定义不同的UI界面，所以这里需要你自定义你的xib文件对应控制器，有什么不同的地方可联系在我的博客上留言: 谢谢！
https://my.oschina.net/shengbingli


谢谢！！！

