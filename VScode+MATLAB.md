# VScode+MATLAB

个人看法，MATLAB的编辑器十分之丑，而且代码补全非常鸡肋。总结起来，写MATLAB代码是一件折磨人的事情。

如果能在VScode里面写MATLAB代码，并且进行调试运行，那是再好不过的事情了。VSC里面的MATLAB插件有很多，然而要基本取代MATLAB的原生编辑器只需要其中四款插件。

## [Matlab Interactive Terminal](https://marketplace.visualstudio.com/items?itemName=apommel.matlab-interactive-terminal)

这个插件提供了三个功能：

- 命令行MATLAB
- 执行当前选定MATLAB代码
- 执行当前所在MATLAB文件

你可以Ctrl+Shift+P打开命令搜索，然后搜索`Open a Matlab Terminal`，执行它，然后就能在VSC的终端看到：

![image-20200804201034488](https://gitee.com/wei_hong_liang/My_Picture_Bed/raw/master/20200804221740.png)

这就是MATLAB交互命令行。

至于执行选定MATLAB代码，你可以用光标选中代码文件中的一小段，Ctrl+Shift+P并执行`Run current selection in Matlab`指令。这个功能其实类似于VSC里面对Python代码的支持。Python代码中也可以选中运行，只不过Python已经预绑定`Shift+Enter`快捷键；而这款插件里面的所有功能都没绑定快捷键。

我的建议是可以为`Run current selection in Matlab`绑定一个快捷键。如何为某个单一操作绑定快捷键可以参考官方文档[Key Bindings for Visual Studio Code](https://code.visualstudio.com/docs/getstarted/keybindings)

绑定快捷键实际上就是写入特定操作和快捷键和触发条件。

![image-20200804201850966](https://gitee.com/wei_hong_liang/My_Picture_Bed/raw/master/20200804221740-1.png)

建议将when条件写成`editorLangId == 'matlab'`。如果不设置When条件的话就会默认任何时候按下快捷键都会执行这个指令。我个人将所有类似操作都绑定`Shift+Enter`，所以会有冲突问题（我不希望执行Python代码的键被覆盖掉）。当你设置我刚刚提到的这个when条件就会使得只有当前语言是matlab时才会将代码递交给MATLAB处理。

值得一提的是，**即使在这个命令行里面输入画图指令也是能执行的**，它会调用MATLAB来画出图像。这可比Mathematica Kernel的待遇好一点。终端执行MMA指令是没法画图的（伤）

我写得比较简略，只是提供概述，建议亲自看插件文档。

## [MatlabSnippets](https://marketplace.visualstudio.com/items?itemName=slaier.matlab-complete)

个人觉得MATLAB的代码补全功能非常糟糕。

但是在VSC里面使用这款插件能为你提供全新体验。看图就知：

![图像](https://github.com/slaier/MatlabSnippets/raw/master/media/preview.gif)

## [matlab-formatter](https://marketplace.visualstudio.com/items?itemName=AffenWiesel.matlab-formatter)

自动代码格式，能够一键缩进你的代码。

![](https://github.com/affenwiesel/matlab-formatter-vscode/raw/master/images/example.gif)

## [Matlab](https://marketplace.visualstudio.com/items?itemName=Gimly81.matlab)

这个插件提供以下几个功能：

- 代码着色（其实前面你看到的那些代码应该是无色的，有色是因为我预先装了这个插件）
- ![](https://github.com/Gimly/matlab-vscode/raw/master/images/syntax.png)
- Snippets（上一个插件的Snippets远好于这个）
- 代码检查（调用MATLAB自带的mlint检查器）

![](C:\Users\QQ\AppData\Roaming\Typora\typora-user-images\image-20200804232232281.png)

## 编码问题

当你打开一份以前写好的.m文件的时候，可能看到所有的中文注释都变成了乱码。

![image-20200804232633903](C:\Users\QQ\AppData\Roaming\Typora\typora-user-images\image-20200804232633903.png)

这是因为MATLAB默认的字符编码格式跟VSC不同。

从我的VSC底栏能看到

![image-20200804232733729](C:\Users\QQ\AppData\Roaming\Typora\typora-user-images\image-20200804232733729.png)

我此时采用的是UTF-8编码。

你只需要将它换成你的.m文件的编码即可。

为了得知你的编码，只需在MATLAB中运行` feature('locale')` 即可。

我的是GBK编码：

![image-20200804233201708](C:\Users\QQ\AppData\Roaming\Typora\typora-user-images\image-20200804233201708.png)

因此将VSC的编码方式改成

![image-20200804233233490](C:\Users\QQ\AppData\Roaming\Typora\typora-user-images\image-20200804233233490.png)

这时，

![image-20200804233254314](C:\Users\QQ\AppData\Roaming\Typora\typora-user-images\image-20200804233254314.png)

当然，VSC也支持“猜测”该文件的编码方式，但是这个功能并不是默认激活的，你可以在settings.json文件中修改这个选项（如果没有就自己创建选项）：

```json
"files.autoGuessEncoding":true,
```

但是这个猜测功能效果如何我也不知道。。

## 调试

虽然上述插件并没有显式给出Debug功能。不过我个人认为划段执行的功能已经算是一个相当好的debug功能了。



