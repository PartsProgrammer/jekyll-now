---
layout: post
title: ListからMapに変換するメソッド
tags: [Java]
---






使用例は以下のような感じ。Userは適当なクラスです。
最近ようやくラムダ式が使えるようになりました。


{% highlight Java  %}
List<User> userList = new ArrayList<>();

// データを入れる部分は省略

Map<Integer, User> userMap = toMap(userList, user -> user.getId());
{% endhighlight %}

