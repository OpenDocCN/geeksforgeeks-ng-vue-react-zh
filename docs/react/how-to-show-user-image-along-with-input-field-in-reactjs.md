# 如何在 ReactJS 中显示用户图像和输入字段？

> 原文:[https://www . geesforgeks . org/how-show-user-image-with-input-field-in-reactjs/](https://www.geeksforgeeks.org/how-to-show-user-image-along-with-input-field-in-reactjs/)

我们可以在 ReactJS 中显示用户图像和输入字段。该功能也可以在脸书登录/ Instagram 登录屏幕上看到。React 的 Material UI 有这个组件可供我们使用，非常容易集成。我们可以使用下面的方法在 ReactJS 中使用输入组件。

**创建反应应用程序并安装模块:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app foldername
```

**步骤 2:** 在创建项目文件夹(即文件夹名**)后，使用以下命令将**移动到该文件夹:

```jsx
cd foldername
```

**步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装 **material-ui** 模块:

```jsx
npm install @material-ui/core
```

**项目结构:**如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**App.js:** 现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## java 描述语言

```jsx
import React from "react";
import Input from "@material-ui/core/Input";
import InputAdornment from "@material-ui/core/InputAdornment";

const App = () => {
  return (
    <div
      style={{
        marginLeft: "30%",
      }}
    >
      <h4>
          How to show User Image along with 
          the input field in ReactJS?
      </h4>
      <Input
        id="input-with-icon-adornment"
        style={{
          padding: 20,
        }}
        startAdornment={
          <InputAdornment position="start">
            <img
              src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200716222246/Path-219.png"
              style={{
                height: 50,
                width: 50,
                borderRadius: "50%",
                border: "1px solid grey",
              }}
            />
          </InputAdornment>
        }
      />
    </div>
  );
};

export default App;
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

![](img/a004b4e96691c021f7e1200529e04e2c.png)