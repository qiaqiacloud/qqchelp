
# 页面组态

使用图形化组态编辑器来生成交互显示页面。


## 编辑器

**页面编辑器**用来创建交互界面，生成基于web的显示页面，在支持浏览器的任何设备上都可以运行。编辑器如下图所示：

![编辑器](../image/e1.png)

> 构成

编辑器由工作区、组件箱、控制栏、工具条、页面容器等5部分构成。

- **工作区**: 即页面的显示区域，把组件箱中的显示组件拖拽至工作区，放到合适的位置，通过属性框配置组件的尺寸、颜色、行为等属性，最终组合成目标显示页面。

- **组件箱**：页面是由若干显示组件单元构成的，组件箱提供创建页面的各种必要组件资源，并会持续更新丰富。

- **控制栏**：提供基本的操作功能，包括“保存”、“撤销”、“重做”、“发布”、“重启”。

- **工具条**：为工作区编辑提供常用的操作功能，如“复制”、“粘贴”等。

- **页面容器**：提供页面管理功能，包括页面创建、修改、删除、分组、组件列表等。

<p class="tip">显示时，页面宽度会自适应到屏幕的宽度，页面高度根据原始宽高比例自动调整</p>

## 预览

页面编辑过程中，需要快速查看实际显示效果，可以点击“工具条”右侧的“预览”按钮，如下图：

![编辑器](../image/e2.png)

打开预览页面后，鼠标移至页面最右侧，会出现“关闭”按钮和“显示调整”按钮，如下图所示，“显示调整”按钮可以切换全屏模式和实际尺寸模式。

![编辑器](../image/e3.png)

<p class="tip">预览页面不具有实时数据收发功能，只能查看显示样式效果。</p>


## 发布

> 发布是指将保存的页面数据更新到url访问地址的操作。

页面编辑过程中，点击“保存”按钮，服务器后台把当前页面数据保存到数据库中，但页面的url访问数据并没有更新，点击“发布”按钮，会产生两个操作效果：

- 将页面数据更新到url

- 将页面显示组件实例化到后面板，可参与数据联动


## 页面

> 交互界面以页面为显示单元，不同页面之间可以互相切换。

**页面容器**如下图所示：

![编辑器](../image/e4.png)

可以创建页面分组、创建页面、复制页面、编辑页面、删除页面，点击“编辑页面”按钮，出现如下图所示的操作窗体:

![编辑器](../image/e5.png)

- 页面名称：修改页面的显示名称

- 页面类型：包括“PC页面”和“手机页面”两类，电视大屏显示页面属于“PC页面”类型

- 页面尺寸：自定义页面的显示尺寸，以“像素”为单位

- 上传背景：上传当前页面的背景图片

- 二维码：其中包含页面的访问地址，可以通过手机扫码来查看页面

- 公开链接：指本页面对外的公开url地址，可以输入到浏览器中打开页面

## 组件资源

组件是页面构成的基本单元，作为显示资源，页面组态编辑器为用户提供常用的多种类型组件，并会持续的更新丰富，尽可能的满足用户大多数需求。

组件箱分为**布局**、**控件**、**软设**、**素材**、**母版**5种分类，详细使用如下。

