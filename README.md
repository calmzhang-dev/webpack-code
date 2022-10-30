# code文件夹下

## webpack源码学习
## 利用node, 通过浏览器调试代码:
eg: node --inspect-brk ./node_modules/webpack-cli/bin/cli.js
### 01 转换代码

#### 02 找出依赖文件 解决嵌套依赖 解决循环依赖
#### perject_02 和 02ts对应

#### 03 转译代码（平稳的兼容策略（解决办法）： 转译代码，将所有文件打包为一个文件）
#### 04 （打包器）将所有文件打包为一个文件（平稳的兼容策略（解决办法）： 转译代码，将所有文件打包为一个文件）
- 这里的文件将会打包为一个文件,  然后去执行他

#### 05 手写一个dist文件 （dist文件就是包含所有打包后的代码，里面的code是函数然后执行函数得到结果）
#### 07 这个文件作用是生成dist文件，加上04文件的打包器，就可以输出自动输出dist
- 那么这里发现只可以解决打包js文件，css呢？ 那么就是去将css转化为js，那么就可以加载了
- 我们建立了一个loader的文件夹，实现了css-loader，就是将css，变为js引入

#### 08 对前面的loader进行优化 loader2（单一职责原则）
- webpack 里每个loader只做一件事情 现在loader文件中做了两件事 1.转字符串 和 2.代码扔到dom中
- 目前我的loader做了两件事
- 1. 将css转化为js字符串


# code2文件 补充

## webpack源码学习补充
#### 01 了解到node.js可以使用import文件, 需要文件名是.mjs文件

#### https://astexplorer.net/ 这个网站列举了诸多语言的解析器(Parser)，及转化器(Transformer)。

#### 02 之前是手写了一个webpack(打包器) 这次看一下联系玩一下 webpack 的 api 以及看一下 输出的代码 (build.js, build2.js, )
- 和之前手写的code/05.dist.js文件一样: 这里给出一个易于理解dist文件结构的例子
```java
const __webpack_modules__ = [() => {}];
const __webpack_require__ = (id) => {
  const module = { exports: {} };
  const m = __webpack_modules__[id](module, __webpack_require__);
  return module.exports;
};

__webpack_require__(0);
```
#### 03 









