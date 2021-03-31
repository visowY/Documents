
# <center> <font color=red>Unity UI 基础</font></center>

## <center>1.RectTransform 基本概念 </center>

* RectTransform 图片

<img src="./01_RectTransfrom.png" width = "300" height = "200" alt="图片名称" align=center />

* Anchored Position :代表物体pivot相对于Anchors锚点的几何中心点的位置
* Position :   物体pivot相对与父物体的rect的几何中心点的位置 
* SizeDelta:   OffsetMax - OffsetMin 
* 安全获取UI宽高的方式： RectTransform.rect 结构体 

* 两种编辑模式
    1. Blueprint mode: 用于控制UI物体的Rect是否进行与UI物体的缩放旋转自动包含适应。

## <center>2.Canvas</center> 

* Canvas的3种渲染模式
* UI&像素的对应关系
* ConstantPixelSize 模式下的UI适配、、
* 常用UI适配方式

* 管理UI点击响应的组件
    1. Graphic Raycaster
        *   Ignore Reversed Graphics  :是否忽略翻转图形（不参与交互）
        *   Blocking Objects: 决定了什么物体会遮挡射线 null 3D 2D 所有 （注意，判断2d还是3D是根据碰撞体来区分的， collider 2D/3D ）
        *   Blocking Mask: 能够阻挡当前射线的层级

* Canvas Group 的使用：

    1. 解决问题： 对成组的UI进行统一管理
    2. 参数
        * Interactable  所有的子物体是否能进行点击响应
        * Block Raycasts 所管理的元素是否能接受图形射线检测 -- 功能& 上基本相同
        * Ignore Parent Groups 是否忽略父上的 canvas Group

## <center>3.渲染层级</center>
> 属性中的数字越大，越后渲染，UI显示在上面
    
* 决定UI渲染层级的4种因素
    1. Camera 的 depth `（针对不同的Camera）`
    2. Canvas 的 Sorting Layer  越下面的layer越后显示`（针对不同的Canvas 或者说针对不同层）`
    3. Canvas 的 Ordier In Layer `针对同1layer下的问题`
    4. UI的自然层级（面板上的排列顺序）

* Image 基础参数

* UV坐标的概念： 贴图映射到物体表面的坐标
    左下为原点， 
