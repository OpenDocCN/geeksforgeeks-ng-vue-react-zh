# 反应钩介绍

> 原文:[https://www.geeksforgeeks.org/introduction-to-react-hooks/](https://www.geeksforgeeks.org/introduction-to-react-hooks/)

**什么是钩子？**
钩子是 React 16.8 中新增的。他们允许开发人员使用状态和其他反应特性，而不需要编写一个类

需要注意的是，类内部不使用钩子。

**为什么需要钩子？**
引入 Hooks 有多种原因，这些原因可能因开发人员开发 React 产品的经验而异。其中一些如下:

*   **使用*‘this’*关键词:**第一个原因更多的是与 javascript 有关，而不是与 React 本身有关。要使用类，你需要理解“this”关键字在 javascript 中是如何工作的，这与它在其他语言中的工作方式非常不同。更容易理解道具、状态和单向数据流的概念，但是使用“this”关键字可能会导致在实现类组件时遇到困难。还需要将事件处理程序绑定到类组件。React 开发团队还观察到，类没有有效地精简，这导致热重载不可靠，这可以使用 Hooks 解决。
*   **可重用的有状态逻辑:**这个原因触及了 React 中的高级主题，比如高阶组件(HOC)和渲染道具模式。没有特定的方法可以重用有状态组件逻辑来做出反应。虽然这个问题可以通过使用 HOC 和渲染道具模式来解决，但它会导致代码库效率低下，这变得难以理解，因为人们最终会将组件包装在几个其他组件中以共享功能。钩子让我们以更好、更干净的方式共享有状态逻辑，而不改变组件层次结构。
*   **简化复杂场景:**在为复杂场景(如数据提取和事件订阅)创建组件时，很可能所有相关代码都没有组织在一个地方，而是分散在不同的生命周期方法中。
    比如像数据、取数这样的动作，通常在`componentDidMount`或者`componentDidUpdate`完成，类似的，如果是事件监听器，则在`componentDidMount`或者`componentWillUnmount`完成。这些开发了一个场景，在这个场景中，完全不同的代码，比如数据获取和事件侦听器，最终会出现在同一个代码块中。由于有状态逻辑，这也使得不可能将组件制动到更小的组件。Hooks 解决了这些问题，它不是基于生命周期方法强制拆分，而是让您根据相关的部分将一个组件拆分成更小的功能。

**使用钩子时要记住的重要事项:**

*   挂钩适用于 React 版本 16.8 或更高版本。
*   钩子完全是选入的。将它部分地用于几个组件，或者根据您的需要将整个项目建立在它的基础上，而无需重写任何现有的代码。
*   钩子不包含任何破坏性的改变，并且是 100%向后兼容的。
*   react 团队没有从 React 中移除类的计划。
*   钩子不能在类组件中使用，但是这个应用程序绝对可以用钩子混合基于类的组件和功能组件。
*   Hooks 没有违反任何现有的 React 概念。相反，Hooks 提供了一个直接的 API 来对道具、状态、上下文、引用和生命周期等概念做出反应。