# Javascript 的构造

## 译序

物理学家在研究时强调逻辑和数学，也会强调物理直觉和物理图像带来的启发。一个经典例子：物理世界当然不存在电场图和电磁图，但我们将其理解电磁世界重要的工具。一张好图胜过千言万语。编程当然是一个强调逻辑的智力活动，但与物理学类似，我们同样可以运用直觉和图像思维，来增进我们对于代码的理解。在 **[Just JavaScript](https://justjavascript.com/)** 中，作者 Dan Abramov 给我们一个很好的示范，展示了他所构建的 Javascript 心智模型，呈现他建构的程序图像和代码直觉。本文是他对于Just Javascript 概述介绍说明。将 [原文](https://overreacted.io/what-is-javascript-made-of/)翻译如下，译者水平有限，难免多疏漏，望多多批评指正。

## 正文

在我早年使用 Javascript 的时候，感觉自己像个骗子。尽管能用框架搭建网站，还是少了一些东西。因为基础不牢，我害怕Javascript的工作面试。

几年后，我构建出一个 Javascript **心智模型**，它给我信心。这里，我分享这个模型的**超级压缩**版。像词汇表一样，每个话题都有几句话。

读这篇文章时，心里试着对每个话题的熟悉程度打个分。如果有些内容你未曾了解过，我不会介意，文章结尾有些东西或许能帮到你！


**值（Value）**: 值的概念是有点抽象的，它是一个实体。值对于 Javascript 来说，就像数学中的数，集合中的点。当你的程序运行时，这是一个充满值的世界。像 `1` 、 `2` 和 `420` 这样的数是值，还有， 像 `"Cows go moo"`  这样的句子也是值。但并非所有的东西都是值， 一个数是值，但 `if` 语句不是，我们讨论下面一些不同类型的值：

 - **值类型（Type of Value)**：值有不同的数据类型，比如 像`420` 这样的 **numbers**  数据类型，像 `"Cows go moo"` 这样的 **strings** 数据类型，还有 **objects** ... 等等一些其他的数据类型。你可以在一个值前面使用 `typeof` 来获取其类型。比如 `console.log(typeof 2)` 会输出 `number`。
 - **原始值（Primitive Values)**: 一些值类型是原始的，有 numbers 、strings ...... 原始值的一个奇特之处在于，你不能创造更多的原始值，也不能以任何方式改变原始值。例如，每次编写 `2` 时，都会得到相同的 `2` 值。你不能在你的程序中创建另一个 `2` 值，或者使 `2` 值变成 `3`。这也适用于字符串。(译者注：just javascript 模型x详细描述了这种值的"图像直觉"。每一个值都是独一无二的实体。`1` 和 `1` 是同一个实体， `1` 与 `2` 是不同的实体， `{name: 'javascipt' }` 与  `{name: 'javascipt' }` 是不同的实体。这一点在 详细阅读 just javascript， 读者可以有更深入的体会。)
 - **`null` 与 `undefined`**: 它们是两类特殊的值。之所以特别，是因为有很多事情你不能用它们来做，他们常常会导致错误。通常， `null` 代表故意缺失的值，而 `undefined` 代表无意间缺失的值。然而，何时使用他们都由程序员来决定。他们之所以存在，因为有时程序操作失败比带着一个缺失的值运行好。

**相等 (Equality)**: 和值一样，相等也是 Javascript 中的一个基础概念。我们说两个值是相等的当他们...... 事实上，我不会这么讲。如果两个值是相等的，这意味着他们是相同的值。他们并非两个不同值，而是同一个值。例如，`"Cows go moo" === "Cows go moo"` 或者 `2 === 2` 是因为2就是2 。 注意，我们在 Javascript 中使用三种等号来表示 相等性。

 - **严格相等（Strict Equality 即 ===）**：如上所述，同一个值
 - **引用相等（Referential Equality 即 = ）**：如上所述，同一个值（译者注即引用数据类型的空间地址相同）
 - **不严格相等（Loose Equality 即 =  )**:  哦，这个有些不一样。当我们使用两个等号 ` == ` 时，代表不严格相等。有过有些看起来相似的不同值（比如 `2` 和 `"2"` ), 可以被视为不严格相等。 它早期是为了方便添加到 JavaScript 中的，但此后一直引起无休止的混乱。 这个概念不是基础，而是常见的错误源头。 你可以没事的时候研究它如何工作，但是许多人都在尝试避免它。


**字面量(Literal)**: 字面量是你通过在程序中字面地写下它来引用一个值。例如，`2` 是数字字面量， `"Banana"` 是字符串字面量。

**变量（Variable）**:  一个变量能让你通过使用一个名字引用一些值。例如，`let message = "Cows go moo"` 。现在你可以写 `message` 而不必每次在代码中重复同样的句子。稍后你也可以更改 `message` 指向另一个值， 像 `message = "I am the walrus"` 。 注意，这不改变值本身，而是改变 `message` 的指向。就像一条连线一样，之前指向 `"Cows go moo"` , 现在指向 `"I am the walrus"` 。

 - **作用域(Scope作用域)**: 如果在你整个程序中只有一个 `message` 变量，这将会是一件十分糟糕的事情。相反，当你定义一个变量时，它只在你程序的局部可用，这一部分即为"作用域"。关于作用域如何工作有 很多规则，但一般来讲，你可用通过寻找定义变量位置附近的 `{ }`,  括号为其作用域。
 - **赋值(Assignment)** : 当我们写 `message = "I am the walrus"` , 我们改变 `message` 变量来指向 `"I am the walrus"`。 这被叫做赋值，也叫做定义变量。
 - **变量声明 (`let` vs `const` vs `var`)**: 通常你想使用 `let` 。如果你想禁止对该变量赋值，你可以使用 `const` 。(当只有一次赋值时，有些死板的同事会强迫你使用 `const`。) 尽可能避免使用 `var` , 因为它的作用域规则令人困惑。

**对象(Object)**: 对象是 JavaScript 中的一种特殊值。 对象最酷的地方在于，它们可以连接到其他值。 例如，`{flavor: "vanilla"}` 对象具有指向 `" vanilla"` 值的 `flavor` 属性。 将一个对象视为“您自己的”值，其中包含一些“连线”。

  - **属性(Property)**: 属性类似于粘在对象上并指向某个值的“线”。 这可能会让您想起变量: 它有一个名称(如 `flavor`)并指向一个值(如 `"vanilla"`)。 但与变量不同的是，属性“存在”于对象本身，而不是代码(作用域)中的某个位置。 一个属性被认为是对象的一部分—但它指向的值不是。
  - **对象字面量(Object Literal)**: 对象字面量是一种通过在程序中直接写入来创建对象值的方法，比如 `{}`或 `{ flavor: “"anilla"}`。 在 `{}` 中，我们可以有多个属性: 值对，用逗号分隔。 这让我们可以设置对象中属性“连线”指向的位置。
  - **对象身份(Object Identity)**: 我们前面提到 `2` 等于 `2`(换句话说，`2===2`) ，因为每当我们写2时，我们“召唤”同样的值。 但是当我们写`{ }`的时候，我们总会得到一个不同的值！ 所以`{ }`不等于另一个 `{ }`。 在控制台中尝试:` { }==={ }` (结果为 false)。 当计算机在我们的代码中遇到2时，它总是给我们相同的2值。 但是，对象字面量是不同的: 当计算机遇到`{ }`时，它创建一个新对象，该对象始终是一个新的值。 那么什么是对象身份呢？ 这是另一个表示相等或者值相同的术语。 当我们说“ `a` 和  `b`  具有相同的身份”时，我们的意思是 `a`  和 ` b ` 指向相同的值( `a === b` )。 当我们说“ `a` 和 `b` 有不同的身份”时，我们的意思是 `a`  和 `b` 指向不同的值 ( `a !== b` ).
  - **点表示法(Dot Notation）**: 当你想从一个对象读取一个属性或者给它赋值时，你可以使用点(`.`) 符号。 例如，如果一个变量 `iceCream` 指向一个属性 `flavor` 指向 `"chocolate"` 的对象，那么写 `iceCream.flavor `就会代表 `"chocolate"`.
  - **括号表示法(Bracket Notation)**: 有时候你不能预先知道你想读取的属性的名称。 例如，有时候你想读取 `iceCream.flavor` , 有时候你想读取 `iceCream.taste` 。 当属性的名称本身是一个变量时，使用括号(`[ ]`)符号可以读取该属性。 例如，如果 `let ourProperty="flavor"`。 然后，`iceCream[ourProperty ]` 会给我们 `"chocolate"`。 令人吃惊的是，我们也可以在创建对象时使用它:` {[ ourProperty ] : "vanilla"}`
  - **改变(Mutation)**: 当有人改变一个对象的属性来指向一个不同的值，我们说这个对象就发生了改变。 例如，如果我们声明`let  iceCream  = { flavor: " vanilla"}` ，我们可以稍后用 `iceCream.flavor="chocolate"`对其进行改变。 注意，即使我们使用 `const` 来声明 `iceCream` ，我们仍然可以对 `iceCream.flavor` 进行改变。 这是因为 `const `只会阻止对 `iceCream` 变量本身赋值，但是我们对对象属性 (`flavor`) 的指向进行了改变。 有些人发誓完全不使用 const，因为他们觉得这太具有误导性
  - **数组(Array)**: 数组是一个对象，表示一系列的东西。 当您编写一个数组字面值, 像`[" banana", "chocolate", "vanilla"]`时，实际上您创建了一个对象。其属性`0`指向`"banana"`字符串值，属性 `1` 指向 `"chocolate"`值，属性为`2`指向 `"vanilla"` 值。 如果写 `{0: ..., 1: ..., 2: ...}`会很烦人，这就是数组有用的原因。 还有一些内置的方法来操作数组，如 `map`、` filter` 和 `reduce`。 如果 reduce 看起来令人困惑，不要绝望——它让每个人都感到困惑。
  - **原型(Prototype)**: 如果我们读取一个不存在的属性会发生什么？ 例如，`iceCream.taste` (但我们的属性为 `flavor` )。 简单的回答是：我们将得到特殊的 `undefined` 值。 更细致的答案是：JavaScript 中的大多数对象都有一个“原型”。 您可以将原型看作是每个对象上的“隐藏”属性，它决定了“下一步要查看哪里”。 因此，如果在 `iceCream`上没有 `taste`属性，JavaScript 将在其原型上寻找 `taste` 属性，然后在该对象原型的原型上寻找 `taste` 属性...... 只有当它到达这个“原型链”的末端而没有找到 `.taste` , 才会给出 `undefined` 。  你很少直接与这个机制打交道，但它解释了为什么我们的 `iceCream` 对象有一个我们从未定义过的 `toString` 方法 —— 它来自原型。


**函数(Function)**: 函数是一个特殊的值，它只有一个用途: 它表示程序中的一些代码。 如果您不想多次编写相同的代码，那么函数很方便。像 `sayHi()` 这样 “调用”一个函数，是告诉计算机运行其中的代码，然后返回到它在程序中的位置。 在 JavaScript 中定义函数的方法有很多种，他们有一些细微的差别。

 - **参数(Argument or Parameters)**: 参数允许您从调用它的位置向函数传递一些信息，比如 ` sayHi ("Amelie")`。 在函数内部，它们的作用类似于变量。 它们被称为参数(Argument or Parameters) ，这取决于您正在做什么事(函数定义或函数调用)。 然而，这种术语上的区别是迂腐的，在实践中这两个术语可以互换使用。（译者注：英文中Argument 专用于 Actual Argument（实际参数，实参），Parameter 专用于 Formal Parameter（形式参数，形参），中文一般都将其翻译为参数）
 - **函数表达式(Function Expression)**: 之前，我们将变量设置为一个字符串值，比如 `let message = "I am the walrus"` 。 事实上，我们也可以为函数设置一个变量，比如 `let  sayHi = function(){ }`。 `=` 后的东西叫做函数表达式。 它为我们提供了一个特殊的值(一个函数)来表示我们的代码片段，如果我们愿意，我们可以稍后调用它。
 - **函数声明(Function Delaration)**: 写一个 `let sayHi = function() { }`是很累的，所以我们可以用一个更短的形式来代替: `function sayHi(){ }` ,这被称为函数声明。 我们没有在左边指定变量名，而是将其放在 function 关键字之后。 这两种风格大多是可以互换的。
 - **函数提升（Function Hoisting)**: 通常，您只能 let 或 const 声明后使用一个变量。 函数之间可能需要相互调用，这可能会令人讨厌，因为很难跟踪哪个函数使用了哪个函数，以及哪个函数需要首先定义。 作为一种方便，当（且仅） 使用函数声明语法，它们的定义顺序并不重要，因为它们会“提升”。 这是一种奇特的说法，从概念上讲，它们都自动移动到作用域的顶部。 当你调用的时候，他们都已经定义好了。
 - **`this`** :  大概是Javascript 最容易迷惑的概念。 this 对一个函数来说是一个特别的参数。你不能把它传递给你自己的函数，相反，Javascript  会根据如何调用函数自己传递它。就像当你使用 `.` 表示法 ，像 `iceCream.eat()`  ，将会从`.` 之前得到一个特殊的 `this` 值（在我们的例子中，是 `iceCream` ) 。函数内部的 `this` 值取决于函数如何被调用，而不是如何被定义。像 `.bind` 、`.call` 、 `.apply` 这些辅助可以让你更方便的控制 `this` 。
 - **箭头函数(Arrow Functions)**: 箭头函数类似于函数表达式。 你这样声明它们: `let sayHi = () => { } `。 它们很简洁，经常用于一行程序。 箭头函数比常规函数有更多的局限性——例如，它们没有 `this` 概念。 在箭头函数中编写 `this` 时，它使用上层最接近的“常规”函数中的 `this` 。 这与使用仅存在于上面的函数中的参数或变量类似。 实际上，这意味着人们使用箭头函数时，他们希望内部与外部使用同一个 `this`。
 - **函数绑定(Function Binding)**: 通常，给函数 `f` 绑定到特定的 `this` 值和 arguments 意味着创建一个新函数，该函数使用那些预定义的值调用 `f`。 Javascript 有一个内置的辅助`.bind` 来完成它,但你也可以手动实现。 绑定是使嵌套函数具有与外部函数相同的 `this` 的一种流行方法。 但是这个目的现在一般由箭头函数实现，所以绑定并不经常使用
 - **调用栈(Call Stack)**: 调用一个函数就像进入一个房间。 每次我们调用一个函数，函数内部的变量都会被重新初始化。 因此，每个函数调用就像用它的代码构造一个新的“房间” ，然后进入它。 我们函数的变量在那个房间里“存活”。 当我们从函数返回时，“房间”和它的所有变量一起消失。 你可以把这些房间想象成一个垂直的房间栈——一个调用栈。 当我们退出一个函数时，我们返回到调用栈上它下面的函数。
 - **递归(Recursion)**: 递归意味着函数从自身内部调用自身。 当您想要重复刚才在函数中所做的事情时，这是非常有用的，但是他们参数不同。 例如，如果您正在编写一个搜索引擎来爬取网页，那么 `collectLinks (url)` 函数可能首先从一个页面收集链接，然后为每个链接调用自身，直到它访问所有页面。 递归的缺陷在于，很容易编写永远不会结束的代码，因为函数会永远调用自己。 如果发生这种情况，JavaScript 将通过一个名为“堆栈溢出”的错误来停止它。 之所以这样称呼，是因为这意味着我们在调用栈中堆积了太多的函数调用，而且函数调用已经超出了调用栈的范围.
 - **高阶函数(Higher-Order Function)**: 高阶函数函数是一个处理其他函数的函数，通过将其他函数作为参数或返回它们。 这在一开始可能看起来很奇怪，但是我们应该记住函数是值，这样我们就可以像传递数字、字符串或对象一样传递它们。 这种风格可能会被过度使用，但是它在适度的情况下非常有用。
  - **回调(Callback)**: 回调不是一个真正的 JavaScript 术语。 它更像是一种模式。 当你将一个函数作为参数传递给另一个函数，期望它稍后调用你的函数。 你在等一个“回调”。 例如，`setTimeout` 接受一个回调函数，时间到了h回头调用它。 但是回调函数没有什么特别的。 它们是常规函数，当我们说“回调”时，我们只谈论我们的期望（希望回头执行）。
 - **闭包（Closure)**: 通常，当执行完退出一个函数时，函数的所有变量都会“消失”。 这是因为没有东西再需要它们了。 但是如果在函数中声明一个函数呢？ 仍然可以稍后调用这个内部函数，并读取外部函数的变量。 在实践中，这是非常有用的！ 但是为了实现这一点，外部函数的变量需要在某个地方“逗留”。 因此，在这种情况下，JavaScript 会注意“保持变量存在” ，而不是像通常那样“忘记”它们。 这就是所谓的“闭包”。 虽然闭包经常被认为是一个被误解的 JavaScript 方面，但是您可能一天使用它们很多次却没有意识到这一点。


JavasScript 正是由这些概念组成。对于 JavaScript 的知识，我曾一度感觉十分不安，直到我可以构建一个正确的心理模型。我乐意帮助下一代的开发者尽快弥补这一差距。

如果你想跟我进一步深入到上面这些话题，我有些东西给你。**[Just JavaScript](https://justjavascript.com/) 是我关于JavaScript工作原理的精炼思维模型，且还有奇人 [Maggie Appleton](https://illustrated.dev/) 所作的一些插画展示。** 

**[Just Javascript](https://justjavascript.com/)** 还处于早期阶段，目前只是一系列的电子邮件，也没有任何修饰和编辑。 如果你有兴趣，可以通过 [订阅](https://justjavascript.com/) 邮件接收这些草稿。对你的反馈，我会十分感激。再次感谢！
## 后记

Dan Abramov,  就职于Facebook(London)。关于作者经历可以看下面这篇文章：[我的十年回顾](https://overreacted.io/zh-hans/my-decade-in-review/) 。 另外我阅读学习 **[Just JavaScript](https://justjavascript.com/)** 过程中收获颇多，因为Just Javascript 基本上是周更，所以建立一个 Just JavaScript 微信交流群，感兴趣的朋友可以加我微信（ji-weiyuan)，可以一起探讨研究，追更。


## 译者

[袁继伟](https://yuanjiwei.com):  (微信：`ji-weiyuan`  微信公众号：`袁继伟` )


