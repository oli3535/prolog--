
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">

</head>
<body>
<div id="wmd-preview" class="wmd-preview"><div class="md-section-divider"></div><div class="md-section-divider"></div><h1 data-anchor-id="n5ka" id="prolog-萌新入门">prolog-萌新入门</h1><p data-anchor-id="s9u1"><code>萌新入门</code> <code>小白</code></p><hr><p data-anchor-id="75dq">小白的prolog入门记录，大佬们求轻喷qaq</p><p data-anchor-id="mv1n">prolog是是种逻辑式的编程语言，可以用于<input type="text" placeholder="要显示的文字">人工智障的开发（划掉）， 如专家系统等</p><p data-anchor-id="seut">😶课上遇到了这门语言所以开个坑记录下学习进程</p><p data-anchor-id="o5q4">首先是prolog 的环境，我用的windows系统下的SWI-Prolog Editor</p><p data-anchor-id="9n5r">SWI-Prolog Editor分成两个界面，一个用来编辑关系和规则，一个用来输入和问询。</p><div class="md-section-divider"></div><h2 data-anchor-id="ybdi" id="1关系和规则">1.关系和规则</h2><p data-anchor-id="yt1p">在编辑界面中写：</p><pre data-anchor-id="epwj"><code>             friend(mike, el).
             friend(mike, john).
</code></pre><p data-anchor-id="23na">这两句被称为关系，记录了括号里两个对象的friend关系。 <br>
mike和el是朋友，然后mike和john也是朋友。</p><p data-anchor-id="ut2j">那么el和john是不是朋友呢？ <br>
在问询中写</p><pre data-anchor-id="98wz"><code>             ?- friend(mike, el).
</code></pre><p data-anchor-id="90wc">按回车，回复是true.即mike和el是朋友。</p><pre data-anchor-id="ubm3"><code>             ?- friend(john, el).
</code></pre><p data-anchor-id="bfv4">按回车，回复是false.也就是说，el和john不是朋友（ -0- 毕竟条件中没有写el和john是朋友）。 <br>
那么如果我们这样问:</p><pre data-anchor-id="kie0"><code>             ?- friend(el, mike).
</code></pre><p data-anchor-id="tvw8">回复会是false。mike和el其实是朋友啊？之所以得到错误的答案，是因为电脑不会把这个关系friend(mike, el)自动翻译成friend(el,mike)。我们可以用下面的语句：</p><pre data-anchor-id="4mub"><code>             friend(X, Y) :- friend(Y,X). //规则1
</code></pre><p data-anchor-id="y9kh">这是一个规则。电脑会从已有的关系，根据此规则，推理出更多的关系。X和Y都是大写字母，代表变量。 <br>
这个问题中，friend(mike, el)就会通过规则1自动推理一个friend(el,mike)。 <br>
再输入就会是true啦。</p></div>
</body>
</html>
