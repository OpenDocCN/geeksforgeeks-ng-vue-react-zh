# angular 10 getlocalecurrency symbol()函数

> 原文:[https://www . geeksforgeeks . org/angular 10-getlocalecurrency symbol-function/](https://www.geeksforgeeks.org/angular10-getlocalecurrencysymbol-function/)

在本文中，我们将看到 Angular 10 中的 **getLocaleCurrencySymbol** 是什么以及如何使用。

getLocaleCurrencySymbol 是 用来获取给定地区的货币符号。

**语法:**

```ts
getLocaleCurrencySymbol(locale: string): string | null
```

**模块:**getlocalecurrency symbol 使用的模块为:

*   **公共模块**

**进场:**

*   创建要使用的角度应用程序
*   在 app.module.ts 中导入 LOCALE_ID，因为我们需要使用 getLocaleCurrencySymbol 导入区域设置。

```ts
import { LOCALE_ID, NgModule } from '@angular/core';
```

*   在 app.component.ts 中，导入 getLocaleCurrencySymbol 和 LOCALE_ID
*   将 LOCALE_ID 作为公共变量注入。
*   在 app.component.html，使用字符串插值显示局部变量
*   使用 ng serve 为 angular app 服务，以查看输出。

**参数:**

*   **区域设置:**包含带有规则的区域设置代码的字符串。

**返回值:**

*   **字符串:**包含货币符号的字符串。

**例 1:**

## app.module.ts

```ts
import { LOCALE_ID, NgModule } 
        from '@angular/core';
import { BrowserModule } 
        from '@angular/platform-browser';

import { AppRoutingModule } 
        from './app-routing.module';
import { AppComponent } 
        from './app.component';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule
  ],
  providers: [
      { provide: LOCALE_ID, useValue: 'en-GB' },
  ],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

## app.component.ts

```ts
import {FormStyle,
        getLocaleCurrencySymbol, 
        TranslationWidth } 
        from '@angular/common';

import {Component, 
        Inject,
        OnInit, 
        LOCALE_ID } 
        from '@angular/core';

@Component({
    selector: 'app-root',
    templateUrl: './app.component.html'
})
export class AppComponent {
    sym = getLocaleCurrencySymbol(this.locale);
    constructor(
        @Inject(LOCALE_ID) public locale: string,){}
      }
```

## app.component.html

```ts
<h1>
   GeeksforGeeks
</h1>

<p>Locale Currency symbol is : {{sym}}</p>
```

**输出:**

![](img/2c5a7fdb401fd7cd546fc9f4d332966d.png)

**例 2:**

## app.module.ts

```ts
import { LOCALE_ID, NgModule } 
       from '@angular/core';
import { BrowserModule } 
       from '@angular/platform-browser';

import { AppRoutingModule } 
from './app-routing.module';
import { AppComponent } 
from './app.component';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule
  ],
  providers: [
      { provide: LOCALE_ID, useValue: 'en-GB' },
  ],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

## app.component.ts

```ts
import {FormStyle,
  getLocaleCurrencySymbol, 
  TranslationWidth } 
  from '@angular/common';

import { Component, 
  Inject,
  OnInit, 
  LOCALE_ID } 
  from '@angular/core';

@Component({
    selector: 'app-root',
    templateUrl: './app.component.html'
})
export class AppComponent {
    sym = getLocaleCurrencySymbol(this.locale);
    constructor(
        @Inject(LOCALE_ID) public locale: string,){}
      }
```

## app.component.html

```ts
<h1>
   GeeksforGeeks
</h1>
 <p>Currency symbol is : {{sym}}</p>
 <p>
    {{sym}}100
    {{sym}}200 
    {{sym}}300
    {{sym}}400
    {{sym}}500
 </p>
```

**输出:**

![](img/7f71c0610b6772f1a10e31856b0924bb.png)

**参考:**[](https://angular.io/api/common/getLocaleCurrencyName)**[https://angular.io/api/common/getLocaleCurrencySymbol](https://angular.io/api/common/getLocaleCurrencySymbol)**