# 重新获取 Onsen UI 搜索输入组件

> 原文:[https://www . geeksforgeeks . org/reactjs-onsen-ui-search input-component/](https://www.geeksforgeeks.org/reactjs-onsen-ui-searchinput-component/)

ReactJS Onsen-UI 是一个受欢迎的前端库，具有一组 React 组件，旨在美丽高效地开发 HTML5 混合和移动网络应用程序。搜索输入组件允许用户提供搜索输入文本字段。我们可以在 ReactJS 中使用以下方法来使用 Onsen-UI 搜索输入组件。

**搜索输入道具:**

*   **修饰词:**用于输入的外观。
*   **禁用:**用于指示输入是否禁用。
*   **onChange** 是输入发生变化时触发的回调函数。
*   **值:**用于表示输入的当前值。
*   **输入:**用于指定内部<输入>元素的“Id”属性。

**预设修改器:**

*   **材质:**用于显示材质设计搜索输入。

**创建反应应用程序并安装模块:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```
npx create-react-app foldername
```

**步骤 2:** 创建项目文件夹(即文件夹名**)后，使用以下命令移动到该文件夹中:**

```
cd foldername
```

**步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装所需的****模块:****

```
**npm install onsenui react-onsenui** 
```

******项目结构:**如下图。****

****![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构**** 

******示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。****

## ****java 描述语言****

```
**import React from 'react';
import 'onsenui/css/onsen-css-components.css';
import { SearchInput } from 'react-onsenui';

export default function App() {

  return (
    <div style={{
      display: 'block', width: 500, paddingLeft: 30
    }}>
      <h6>ReactJS Onsen-UI SearchInput Component</h6>
      <SearchInput
        modifier='material'
        onChange={(e) => { console.log(e) }}
      />
    </div>
  );
}**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/cacd9dd160149e64f64596d31a825a84.png)****

******参考:**T2】https://onsen.io/v2/api/react/SearchInput.html****