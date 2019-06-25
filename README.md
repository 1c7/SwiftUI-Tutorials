![](https://repository-images.githubusercontent.com/190505979/0618a700-889e-11e9-9543-7cf88db49659)

<p align="center">
  <a href="https://github.com/WillieWangWei"><img src="https://img.shields.io/badge/language-swift-orange.svg"></a>
  <a href="https://github.com/WillieWangWei"><img src="https://img.shields.io/github/repo-size/WillieWangWei/SwiftUI-Tutorials.svg"></a>
  <a href="https://github.com/WillieWangWei/SwiftUI-Tutorials/blob/master/LICENSE"><img src="https://img.shields.io/github/license/WillieWangWei/SwiftUI-Tutorials.svg"></a>
</p>

> **构建示例项目需要以下环境：**
> 
> * macOS 10.15 beta 或更高
> * Xcode 11.0 beta 或更高

# 概述 

此项目为 [SwiftUI Tutorials](https://developer.apple.com/tutorials/swiftui) 的翻译及代码示例，具体内容请翻阅：

**🎉 [SwiftUI 教程（中文）](https://github.com/WillieWangWei/SwiftUI-Tutorials/wiki)**

此仓库的代码为完成所有教程后的最终成品，你可以直接体验多种 `SwiftUI` 特性。另外，你也可以在每个教程章节中下载对应的起始和完成代码。

完成本教程，你将获得一个这样的 App 以及一套精彩的 `SwiftUI` 代码：

![](https://github.com/WillieWangWei/SwiftUI-Tutorials/blob/master/preview.gif)

> **觉得不错？给个 Star 或 Follow 👌**

## 调整

### 图片

为了优化阅读体验，部分图片加上了 `#000000`  `50%`  `10 Blur` 的阴影。

### 视频

由于 `GitHub Wiki` 的限制，所有视频已转码成 `GIF` 。

### 代码

在实际编码中，由于本地环境和官方教程不一致，导致部分方法的声明和调用方式、代码风格等与官方教程有细微出入，例如：

官方教程：

```
...
struct MapView: UIViewRepresentable {
    func makeUIView(context: Context) -> MKMapView {
        MKMapView(frame: .zero)
    }
}
...
```

这里的 `UIViewRepresentable` 是一个协议，它的声明中包含一个 `associatedtype` :

```
/// The type of `UIView` to be presented.
associatedtype UIViewType : UIView
```

在开发中，给此 `associatedtype` 赋值后 Xcode 对方法的签名补全会有变化，最终写作：

```
...
struct MapView : UIViewRepresentable {
    
    typealias UIViewType = MKMapView
    
    func makeUIView(context: UIViewRepresentableContext<MapView>) -> MKMapView {
        return MKMapView(frame: .zero)
    }
}
...
```

如此修改不再一一列举，只需记得**此类修改不会改变原教程的构建结果**即可，不必过于纠结。

## License

This project is licensed under the MIT License - see the [LICENSE.md](https://github.com/WillieWangWei/SwiftUI-Tutorials/blob/master/LICENSE) file for details.
