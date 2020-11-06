# OpenGL

## 一、简介

> 是什么

- OpenGL是一个图形操作的**规范**
-  严格规定了每个函数该如何执行，以及它们的**输出值** 
- **具体实现**由OpenGL库的开发者自行决定 

### 1.1 核心模式和立即渲染模式

> 立即渲染模式

- **固定管线**
- 容易理解和使用
- 不灵活
- 效率低

> 核心模式

- 灵活
- 高效
- 难于学习

### 1.2 状态机

- OpenGL自身是一个巨大的**状态机**
- OpenGl状态被称为**OpenGL上下文**
- 改变状态的方法
  - 设置选项
  - 操作缓冲

### 1.3 对象

> 为什么

- 定义不同的对象来保存不同的设置
- 不需要重复设置

> 是什么

- 一个**选型**的集合

> 基元类型

- 保证程序在**不同平台**上工作一致
- `GL`
  - `GLfloat`

> 工作流

```C++
// 创建对象
GLuint objectId = 0;
glGenObject(1, &objectId); //用一个id保存它的引用
// 绑定对象至上下文
glBindObject(GL_WINDOW_TARGET, objectId);
// 设置当前绑定到 GL_WINDOW_TARGET 的对象的一些选项
glSetObjectOption(GL_WINDOW_TARGET, GL_OPTION_WINDOW_WIDTH, 800);
glSetObjectOption(GL_WINDOW_TARGET, GL_OPTION_WINDOW_HEIGHT, 600);
// 将上下文对象设回默认
glBindObject(GL_WINDOW_TARGET, 0);
```

## 二、入门

### 2.1 创建窗口

> 目标

- 创建一个窗口
- 定义OpenGL上下文
- 处理用户输入

#### 2.1.1 GLFW

> 是什么

-  一个专门针对OpenGL的C语言库 
-  提供了一些渲染物体所需的最低限度的接口 
-  允许用户创建OpenGL上下文，定义窗口参数以及处理用户输入 

> 构建GLFW

