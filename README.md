# prolog-萌新入门
小白的prolog入门记录，大佬们求轻喷qaq

prolog是是种逻辑式的编程语言，可以用于人工智障的开发（划掉）， 如专家系统等

😶课上遇到了这门语言所以开个坑记录下学习进程

首先是prolog 的环境，我用的windows系统下的SWI-Prolog Editor
SWI-Prolog Editor分成两个界面，分别是


然后在编辑界面中写：
    friend(mike, el).
    friend(mike, john).
mike和el是朋友，然后mike和john也是朋友。
那么el和john是不是朋友呢？
在问询中写
    ?-  friend(mike, el).
按回车，回复是true.即mike和el是朋友。
    ?-  friend(john, el).
按回车，回复是false.也就是说，el和john不是朋友（ -0- 毕竟条件中没有写el和john是朋友）。
那么如果我们这样问:
    ?-  friend(el, mike).
回复会是false。mike和el其实是朋友啊？之所以得到错误的答案，是因为电脑不会把这个关系friend(mike, el)自动翻译成friend(el,mike)。我们可以用下面的语句：
    friend(X, Y) :- friend(Y,X).    //规则1
这是一个规则。电脑会从已有的条件，根据此规则，推理出更多的规则。X和Y都是大写字母，代表变量。
这个问题中，friend(mike, el)就会通过规则1自动推理一个friend(el,mike)。
再输入就会是true啦。
