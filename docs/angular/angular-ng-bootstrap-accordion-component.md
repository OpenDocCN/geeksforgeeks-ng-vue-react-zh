# 角度引导手风琴组件

> 原文:[https://www . geesforgeks . org/angular-ng-bootstrap-accordion-component/](https://www.geeksforgeeks.org/angular-ng-bootstrap-accordion-component/)

Angular ng bootstrap 是一个 bootstrap 框架，与 Angular 一起使用来创建具有很好风格的组件，这个框架非常容易使用，用于制作响应性网站。

在本文中，我们将了解如何在 angular ng bootstrap 中使用手风琴。**手风琴**用于显示在有限空间内呈现信息的可折叠内容。

**安装语法:**

```
ng add @ng-bootstrap/ng-bootstrap
```

**进场:**

*   首先，使用上述命令安装 angular ng 引导程序。
*   Import ng bootstrap module in module.ts

    ```
    import { NgbModule } from '@ng-bootstrap/ng-bootstrap';

    imports: [
      NgbModule
    ]

    ```

    *   在 app.component.html 制作手风琴组件。
    *   使用 ng serve 为应用提供服务。

    **示例:**

    ## pp.component.html

    ```
    <ngb-accordion #acc="ngbAccordion"
                   activeIds="ngb-panel-0">
      <ngb-panel title="GeeksforGeeks">
        <ng-template ngbPanelContent>
          Content1
        </ng-template>
      </ngb-panel>
      <ngb-panel>
        <ng-template ngbPanelTitle>
          <span>Angular 10</span>
        </ng-template>
        <ng-template ngbPanelContent>
          Content2
        </ng-template>
      </ngb-panel>
      <ngb-panel title="Ng bootstrap"
                 [disabled]="true">
        <ng-template ngbPanelContent>
          Content3
        </ng-template>
      </ngb-panel>4
    </ngb-accordion>
    ```

    ## app.module.ts

    ```
    import { NgModule } from '@angular/core';

    // Importing forms module
    import { FormsModule, ReactiveFormsModule  }
    from '@angular/forms';
    import { BrowserModule }
    from '@angular/platform-browser';
    import { BrowserAnimationsModule }
    from '@angular/platform-browser/animations';

    import { AppComponent }   from './app.component';
    import { NgbModule } 
    from '@ng-bootstrap/ng-bootstrap';

    @NgModule({
      bootstrap: [
        AppComponent
      ],
      declarations: [
        AppComponent
      ],
      imports: [
        FormsModule,
        BrowserModule,
        BrowserAnimationsModule,
        ReactiveFormsModule,
        NgbModule
      ]
    })
    export class AppModule { }
    ```

    **输出:**

    ![](img/bb9c5bdba5fea6a7be7618f39677e8b5.png)

    **参考:**[https://ng-bootstrap . github . io/#/components/accordion/examples](https://ng-bootstrap.github.io/#/components/accordion/examples)