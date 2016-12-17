---
title: 使用 React 开发一个自己的 DataTable 组件
date: 2016-08-22 17:24:46
tags: [React, JavaScript]
---

# 使用 React 开发一个自己的 DataTable 组件

**已完成的实例代码，传送门： [chengjianhua/react\-datatable: A simple data table implementaition by react\.js, to replace the jQuery data table with simple usages\.](https://github.com/chengjianhua/react-datatable)**

目前在实习中，由于公司项目的重构需求，原有使用 `jQuery-data-table` 来完成数据表的展示、排序、筛选和分页等功能，原本打算使用 `react-bootstrap-table` 来完成项目的重构，但是由于一些定制化的需求，不想再使用 Hack 的方式来蹩脚地完成我们想要实现的效果。也是为了以后的便利，所以打算自己造个小轮子，只要满足以上我们想要的几个小功能就可以了。不需要大而全且不符合我们定制化需求的第三方库了。别说，写个小轮子还是挺好玩的！

接下来总结下我在开发过程中对 React 一些特性的理解。

## 结构

```bash
\---DataTable
    |   Column.jsx # 数据表格列的配置组件
    |   DataTable.jsx # 数据表格的根组件
    |   index.js # 入口文件
    |   index.scss # 样式文件
    |   Pagination.jsx # 数据表的分页组件
    |
    \---utils
            Constants.js # 定义一些常量配置
            Store.js # 数据表中数据的操作与临时中间值的存储
            utils.js # 工具函数
```

文件的大概作用我都在右边的注释进行了说明。

##
