# 角通用

介绍

> 原文:[https://www . geesforgeks . org/introduction-to-angular-universal/](https://www.geeksforgeeks.org/introduction-to-angular-universal/)

在过去的几年里，Angular 成为开发单页应用程序最著名的前端框架之一。

大多数人认为 Angular 只在客户端工作，但这部分是正确的，因为 Angular 中有一个概念，它解释了应用程序在下载到浏览器之前要在服务器端呈现的一些部分。这个概念叫做**角通用**。

让我们详细谈谈它以及如何在您的应用程序中实现它。在转到角度通用之前，让我们简单谈谈角度应用程序在中的表现，以及为什么需要角度通用。

一般来说，当我们尝试运行 Angular 应用程序时，首先将 JavaScript 下载到浏览器中，然后在浏览器中呈现，并向用户显示网页。通常由于高连通性，我们通常不会注意到所有这些步骤。但是当连接缓慢时，问题就出现了，下载所需的 JavaScript 文件并呈现它们需要时间，直到所有这些都完成，用户会看到一个空白页面，这对于任何用户来说都是令人沮丧的。

因此，为了解决这个问题，在《角形》中引入了角形通用的概念。

Angular universal 允许用户在服务器上预渲染一些 Angular 应用程序。它不像服务器端的 JavaScript。因此，您将无法在 angular 应用程序中编写服务器端代码。

最初的请求在服务器中预先呈现，随后的 js 请求将整个 angular 应用程序加载到浏览器中，使其更快、更具反应性。第一个负载在服务器上处理，如果连接速度慢，服务器会为用户解决用户界面问题。因此，用户能够看到应用程序的第一个网页，该网页可以是身份验证页面或任何其他页面，即使 JavaScript 由于连接速度慢而被部分下载或呈现。

这是角宇宙背后的基本思想。现在，让我们看看如何实现它。要使您的应用程序 Angular Universal，只需在终端中运行以下命令。

***ng add @ nguniversal/express-engine–client project project name***

**注意:**项目名称可以在项目下的 angular.json 文件中找到，然后识别器-name。

这将添加在服务器上呈现应用程序的选项，并获得预呈现内容。

**注意:**如果您使用的是 Angular 8 或以下，则需要检查以下内容。

应该在导入部分下的 app.server.module.ts 中导入 ModuleMapLoader。如果找不到 app.server.module.ts 文件，请运行以下命令。

***npm 安装–保存@ nguniversal/module-map-ngfactory-loader***

对于 Angular 9 和更高版本，不需要执行上述步骤。上述模块有助于实现角度通用的惰性加载。

现在，您的应用程序已经准备好在服务器上预渲染一些角度内容。第一页将在服务器上呈现，只有在第一页呈现并返回给用户之后，整个应用程序才会像往常一样在浏览器中运行。

这种方法有一个主要的含义。如果您现在在服务器端呈现的第一个请求包含一些基于浏览器的方法，这些方法不能在像 localStorage 这样的服务器上运行，那么您的应用程序将无法构建。要解决这个问题，我们有两种方法。如果可能的话，我们可以用其他方法替换它，或者我们确保只有当平台是浏览器而不是服务器时才调度这样的请求。为了检查平台是浏览器还是服务器，angular 提供了一个名为 Platform Browser 的方法，可以从@angular/common 导入。

现在，使用以下命令构建应用程序–

***npm 运行构建:ssr***

**注意:**由于现在您的 angular 应用程序部分呈现在服务器端，因此您需要一个节点 js 服务器来运行应用程序，因为静态主机不足以运行您的应用程序。

确保安装了节点 js 服务器或通过部署的服务器上传了应用程序之后。运行以下命令来运行应用程序。

***npm 跑发球:ssr***

这样，现在您的 angular 应用程序将充分利用服务器，您可以使用它来预渲染 angular 应用程序的一些内容。