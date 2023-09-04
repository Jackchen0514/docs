# Android基础

## 四大组件

1. Activity的生命周期
```
Activity的生命周期是由一系列回调方法组成的，这些方法在Activity从创建到销毁的过程中被调用。了解这些生命周期方法及其作用对于开发Android应用程序至关重要，因为它们决定了Activity的行为和状态。

以下是Activity生命周期的主要回调方法及其描述：

onCreate()：

当Activity首次被创建时调用。
在这个方法中，你通常会进行一次性的初始化操作，如设置布局、绑定数据等。
onStart()：

当Activity变得对用户可见时调用。
这意味着Activity已经进入了启动状态，但用户还不能与其进行交互。
onResume()：

当Activity准备好与用户进行交互时调用。
在此状态下，Activity位于前台并具有用户焦点。
onPause()：

当系统即将启动另一个Activity时调用。
通常在这个方法中，你会释放那些不需要的资源，或保存一些轻量级的用户数据。
onStop()：

当Activity不再对用户可见时调用。
如果Activity被完全覆盖或者是由于其他原因（如用户按下了“返回”按钮）而被隐藏，这个方法就会被调用。
onRestart()：

当Activity从停止状态重新启动到用户前台之前调用。
这个方法在onStop()之后和onStart()之前被调用。
onDestroy()：

当Activity即将被销毁时调用。
这是Activity生命周期中的最后一个回调，通常在这里你会进行清理资源的操作。
这些方法提供了一个框架，让你知道何时执行特定的操作，如创建用户界面、暂停动画或保存数据。正确处理这些生命周期回调可以确保你的应用程序行为正确，并为用户提供流畅的体验。

```

介绍下谈谈生命周期中onStart和onResume的区别
```
在Android的Activity生命周期中，onStart()和onResume()都是生命周期回调方法，它们在Activity启动和恢复时被调用。但它们的用途和调用时机有所不同。以下是onStart()和onResume()之间的主要区别：

调用时机：

onStart()：当Activity变得对用户可见时，onStart()被调用。这包括当Activity首次启动时，或者从完全不可见的状态（如后台）变为部分可见或完全可见的状态。
onResume()：当Activity开始与用户交互时，onResume()被调用。这通常发生在onStart()之后。此时，Activity位于前台，并且用户可以与它交互。
用途：

onStart()：通常用于执行使Activity对用户可见的操作，如初始化UI组件、注册广播接收器等。
onResume()：通常用于执行与用户交互相关的操作，如启动动画、监听键盘输入等。
生命周期位置：

onStart()：位于Activity生命周期的中间位置，介于onCreate()和onResume()之间。
onResume()：位于Activity生命周期的几乎末端，只有onPause()、onStop()和onDestroy()在其之后。
与其他状态的关系：

onStart()：当Activity从onStop()状态恢复时，会调用onStart()。
onResume()：当Activity从onPause()状态恢复时，会调用onResume()。
可见性：

onStart()：在此状态下，Activity对用户是可见的，但可能不是前台Activity，因此可能无法与用户交互。
onResume()：在此状态下，Activity不仅对用户可见，而且是前台Activity，可以与用户交互。
总的来说，onStart()和onResume()都是Activity生命周期的重要部分，但它们在Activity生命周期中的位置和用途有所不同。理解这两个方法及其在生命周期中的位置对于确保应用的正确行为和性能优化至关重要。
```
