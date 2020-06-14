## 1. vertical-align

CSS 的属性 `vertical-align` 用来指定行内元素（inline）或表格单元格（table-cell）元素的垂直对齐方式。

就像定义说的，这个属性允许你垂直对齐文本。它对于顺序指示器(`st`, `nd`等)、需要的输入星号(`*`)或没有正确居中的图标特别有用。`vertical-align`取其中一个值:`super | top | middle | bottom | baseline (default) | sub | text-top | text-bottom`，或从基线开始的长度(`px`，`%`， `em`, `rem`等等)。

**baseline:** 使元素的基线与父元素的基线对齐。HTML规范没有详细说明部分可替换元素的基线，如`<textarea>` ，这意味着这些元素使用此值的表现因浏览器而异。

**sub：**使元素的基线与父元素的下标基线对齐。

**super：**使元素的基线与父元素的上标基线对齐。

**text-top：**使元素的基线与父元素的上标基线对齐。

**text-bottom：**使元素的底部与父元素的字体底部对齐。

**middle：**使元素的中部与父元素的基线加上父元素`x-height`（译注：x高度）的一半对齐。

![img](https://cdn.nlark.com/yuque/0/2020/gif/1292672/1592023532622-e5ee4d2a-9523-4304-aa56-614f20736c47.gif)

**注意 vertical-align 只对行内元素、表格单元格元素生效：不能用它垂直对齐块级元素。**

资源:[MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align)。

## 2. writing-mode

`writing-mode` 属性定义了文本水平或垂直排布以及在块级元素中文本的行进方向。为整个文档设置书时，应在根元素上设置它（对于 HTML 文档应该在 html 元素上设置）。 它采用以下值之一`horizontal-tb (default) | vertical-rl | vertical-lr`。

![img](https://cdn.nlark.com/yuque/0/2020/webp/1292672/1592023532595-da9ecf96-0060-4e44-b7f2-62950a89cb63.webp)

**horizontal-tb：**对于左对齐(ltr)脚本，内容从左到右水平流动。对于右对齐(rtr)脚本，内容从右到左水平流动。下一水平行位于上一行下方。

**vertical-rl：**对于左对齐(ltr)脚本，内容从上到下垂直流动，下一垂直行位于上一行左侧。对于右对齐(rtr)脚本，内容从下到上垂直流动，下一垂直行位于上一行右侧。

**vertical-lr：**对于左对齐(ltr)脚本，内容从上到下垂直流动，下一垂直行位于上一行右侧。对于右对齐(rtr)脚本，内容从下到上垂直流动，下一垂直行位于上一行左侧。

资源:[MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode)。

**大家都说简历没项目写，我就帮大家找了一个项目，还附赠【搭建教程】。**

## 3. font-variant-numeric

`font-variant-numeric` CSS属性控制数字，分数和序号标记的替代字形的使用。

它采用以下这些值之一： `normal | ordinal | slashed-zero | lining-nums | oldstyle-nums | proportional-nums | tabular-nums | diagonal-fractions | stacked-fractions`。

此属性对于设置数字样式很有用。 根据情况，你可能希望显示老式的数字或带有斜杠的零，对于这些情况，`font-feature-settings`很有用。

![img](https://cdn.nlark.com/yuque/0/2020/gif/1292672/1592023532633-d408989a-6a40-4225-89b1-80e88fa86b5f.gif)

> 请注意，`font-variant-numeric`是`font-feature-settings`组属性的一部分。 诸如`font-variant-caps`或`font-variant-ligatures`之类的属性也属于该组。 还要注意，像所有`font-feature-settings`属性一样，你的字体需要实现上述功能才能正常工作。 我使用的字体是`Fira Sans`。

资源:[MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-numeric)。

## 4. user-select

每当我们有不想让用户选择的文本，或者相反，如果发生了双击或上下文单击，希望选择所有文本时，`user-select`属性将非常有用。

此属性采用以下值之一：`none | auto | text | all`。

**none：**元素及其子元素的文本不可选中。 请注意这个`Selection` 对象可以包含这些元素。 从Firefox 21开始， `none` 表现的像 `-moz-none`，因此可以使用 `-moz-user-select: text` 在子元素上重新启用选择。

**auto** `auto` 的具体取值取决于一系列条件，具体如下：

- 在 `::before` 和 `::after` 伪元素上，采用的属性值是 `none`
- 如果元素是可编辑元素，则采用的属性值是 `contain`
- 否则，如果此元素的父元素的 `user-select` 采用的属性值为 `all`，则该元素采用的属性值也为 `all`
- 否则，如果此元素的父元素的 `user-select` 采用的属性值为`none`，则该元素采用的属性值也为 `none`
- 否则，采用的属性值为`text`

**text：**用户可以选择文本。 **all：**在一个HTML编辑器中，当双击子元素或者上下文时，那么包含该子元素的最顶层元素也会被选中。

![img](https://cdn.nlark.com/yuque/0/2020/gif/1292672/1592023532586-5d7736b0-b17c-4b96-abb9-9a59ce25900c.gif)

资源:[MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/user-select)。

**大家都说简历没项目写，我就帮大家找了一个项目，还附赠【搭建教程】。**

## 5. clip-path

`clip-path` CSS 属性可以创建一个只有元素的部分区域可以显示的剪切区域。区域内的部分显示，区域外的隐藏。剪切区域是被引用内嵌的URL定义的路径或者外部svg的路径，或者作为一个形状例如`circle()`。`clip-path`属性代替了现在已经弃用的剪切 `clip`属性。

此属性采用以下值之一:`circle() | ellipse() | polygon() | path() | url()`。

由于这是对该属性的介绍，因此，这里不会深入研究每个值。

我使用最多的两个值是`circle`和`polygon`。`circle(radius at pair)`值有两个参数，第一个参数是圆的半径，第二个参数是表示圆心的点。`polygon(pair, pair, pair ...)`值取3个或更多的点，表示一个三角形、一个矩形等等。

![img](https://cdn.nlark.com/yuque/0/2020/webp/1292672/1592023532643-cab00cd4-66b5-41b3-bbad-c4fbdebcecef.webp)

## 6. shape-outside

`shape-outside`的CSS 属性定义了一个可以是非矩形的形状，相邻的内联内容应围绕该形状进行包装。 默认情况下，内联内容包围其边距框; `shape-outside`提供了一种自定义此包装的方法，可以将文本包装在复杂对象周围而不是简单的框中。它采用与`clip-path`相同的值。

`clip-path`定义用户如何查看元素，`shape-outside`定义其他HTML元素如何查看元素。

![img](https://cdn.nlark.com/yuque/0/2020/webp/1292672/1592023532611-b2c7f11e-c429-4b99-808d-b77059b308a9.webp)

资源:[MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/shape-outside)。



## 7. background-clip

最后，`backgroundclip` CSS属性设置元素的背景是否扩展到其`border` 、`padding` 或`content` 框之下。

此属性采用以下值之一：`border-box (default) | padding-box | content-box | text`

![img](https://cdn.nlark.com/yuque/0/2020/gif/1292672/1592023559522-8ef19e52-af13-4cb2-966d-4b38a410d014.gif)

资源:[MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/background-clip)。

## 总结

下图是结合上面 7 个属性实现的布局，让大家加深一下印象。

![img](https://cdn.nlark.com/yuque/0/2020/webp/1292672/1592023559478-550963d4-6c4d-4791-830c-56218781f18c.webp)

如果你还知道一些新奇的属性，欢迎留言。

------

**代码部署后可能存在的BUG没法实时知道，事后为了解决这些BUG，花了大量的时间进行log 调试，这边顺便给大家推荐一个好用的BUG监控工具 Fundebug。**

原文：[dev.to/mustapha/7-…](https://dev.to/mustapha/7-amazing-css-properties-you-may-not-know-yet-eej)



作者：前端小智

链接：<https://juejin.im/post/5ea8c37fe51d454dc55c8de7>

来源：掘金

著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。