# JavaScript Naming Conventions

#javascript #naming-conventions #conventions

## 注意点

1. 尽量用英文
2. 注意命名格式

## 命名格式

一般来讲，有下面几种命名格式

- PascalCase：组件名、网络请求
- camelCase：变量、方法
- snake_case
- kebab-case：源代码路径、组件标签 <kebab-case>、url、路由
- ALL_UPPERCASE_WITH_SNAKE_CASE：常量

以下为示例:

```javascript
// PascalCase
import HeaderContainer from './HeaderContainer.vue'
const UpdateBook = () => { return axioa.get() }

// camelCase
const addItem = () => {}
const removeItem = () => {}

let userList = []

// kebab-case
<header-container></header-container>

// ALL_UPPERCASE_WITH_SNAKE_CASE
const DEFAULT_PAGE_SIZE = 10
```
## 组件

事件绑定的函数即通过 `@` 开头的方法，需要以 handle 前缀命名
在method 中首先排列 handle 的方法，handle 方法通过字母表顺序排列， 建议在 handleEvent 中尽量通过调用方法的形式实现功能。

```javascript
// <Button @click="handleClickCancel>
methods: {
    handleClickCancle() {
        this.closeModal()
    },
    handleClickOK() {},
    handleClickRefresh() {}
    otherFunction() {}
}

```
生命周期钩子函数，只调用方法

```javascript
// This is Bad Example
created () {
    this.loading = false
    this.booksList = ListBooks()
    this.loading = false
}
// This is Good Example
methods: {
    listBooks() {
        this.loading = false
        this.booksList = ListBooks()
        this.loading = false
    }
}
created () {
    this.listBook()
}
```

## 网络请求

参考 Google Cloud API Naming Convention。

```javascript
// src/book/service.js
export const async ListBooks = () => { 
    let {data} = await axios.request({
        method: 'GET',
        baseURL: 'http://'
    })

    return data
}

// or 
export const ListBooks = () => {
    return axios.request({
        method: 'GET',
        baseURL: 'http://'
    })
}

const Book = {
    ListBooks
}

export defaut Book
```

## 其他

`IS_DEV` 是一个脚手架变量。相关的函数通过 `DEV_mockData` 的形式命名

## References

`github/kettanito/naming-cheatsheet` ， `Google Cloud API Naming Convention`， 需要简单看一下，材料可以做进一步研究参考。


- [**Code Complete**](https://book.douban.com/subject/1432042/), Steve McConnell
- [**The Elements of Java™ Style**](http://derek.dkit.ie/java/the_elements_of_java_style/the_elements_of_java_style.pdf), Vermeulen et al. 2000
- [github/kettanito/naming-cheatsheet](https://github.com/kettanaito/naming-cheatsheet)
- [Google Cloud API Naming Convention](https://cloud.google.com/apis/design/naming_convention)