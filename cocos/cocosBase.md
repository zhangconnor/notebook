# 基本概念

游戏引擎是一种特殊的软件，它提供游戏开发所需的常见功能，用使用引擎提供的组件可以缩短开发时间，让游戏开发变得更简单。

游戏引擎通常会包含渲染器，2D/3D图形元素，碰撞检测，物理引擎，声音，控制器支持，动画等部分。

## 组件简介

菜单(Menu)，精灵(Sprite)，标签(Label)。

## 导演(Director)

Cocos2d-X 使用导演的概念，在开发过程中，你可以认为自己是制片人，告诉导演该怎么办，一个常见的 Director 任务是控制场景替换和转换， Director 是一个共享的单例对象，可以在代码中的任何地方调用

你是你的游戏的导演，你决定着发生什么，何时发生，如何发生。

## 场景(Scence)

在游戏开发过程中，你可能需要一个主菜单，几个关卡和一个结束场景。如何组织所有这些分开的部分？使用 场景(Scene) ！当你想到喜欢的电影时，你能观察到它是被分解为不同场景或不同故事线。现在我们对游戏开发应用这个相同的思维过程，你应该很容易就能想出几个场景。

场景是被 渲染器(renderer) 画出来的。渲染器负责渲染精灵和其它的对象进入屏幕。

### 场景图(Sence Graph)

场景图(Sence Graph)是一种安排场景内对象的数据结构，它把场景内所有的节点都包含在一个树(tree)上。(场景图虽然叫做“图”，但实际使用一个树结构来表示)。

Cocos2d-X 使用中序遍历 ，遍历场景图的时候，先遍历左子树，然后根节点，然后右子树。

另一点要考虑的是，z-order为负的元素，z-order为负的节点会呗放置在左子树，非负的节点会被放在右子树。实际开发过程中，你可以按照任意顺序添加对象，他们会按照你指定的z-order自动排序。

在Cocos2d-X中，通过 Sence 的 addChild() 方法来构建场景图。

```
// Adds a child with the z-order of -2, that means
// it goes to the "left" side of the tree (because it is negative)
scene->addChild(title_node, -2);

// When you don't specify the z-order, it will use 0
scene->addChild(label_node);

// Adds a child with the z-order of 1, that means
// it goes to the "right" side of the tree (because it is positive)
scene->addChild(sprite_node, 1);
```

渲染时， z-order 值大的节点对象会后绘制，值小的节点对象会先绘制，如果两个节点对象的绘制范围有重叠，z-order 值大的可能会覆盖 z-order 值小的

## 精灵(Sprite)

所有的游戏中都有精灵(Sprite)对象，精灵是您在屏幕上移动的对象，它能被控制。

一个图形对象，如果你能控制它，它才是一个精灵(Sprite)，如果无法控制，那就只是一个节点(Node)。

Sprite 很容易被创建，它有一些可以被配置的属性，如：位置，旋转角度，缩放比例，透明度，颜色等等。

```
// This is how to create a sprite
auto mySprite = Sprite::create("mysprite.png");

// this is how to change the properties of the sprite
mySprite->setPosition(Vec2(500, 0));

//设置旋转角度
mySprite->setRotation(40);

//设置缩放比例
mySprite->setScale(2.0);

//设置精灵锚点位置
mySprite->setAnchorPoint(Vec2(0, 0));
```

锚点(anchor point)， 所有的节点(Node)对象都有锚点值， sprite 是 node 的子类，自然也具有锚点。锚点是节点对象在计算坐标位置时的一个基准点。

锚点对于确定节点对象的位置是非常有用的，你可以在你的游戏中动态的调整锚点值以实现你想要的效果。

## 动作(Action)

动作(Action)解决的问题就是让 Sprite 动起来，它可以让 Sprite 在场景中移动，如从一个点移动到另外一个点，你还可以创建一个动作 序列(Sequence), 让精灵安扎这个序列做连续的动作， 在动作过程中你可以改变 sprite 的位置，旋转角度，缩放比例等等。

## 序列(Sequence)

顾名思义，序列就是多个动作按照特定顺序的一个排列，当然反向执行这个序列也是可以的.

 