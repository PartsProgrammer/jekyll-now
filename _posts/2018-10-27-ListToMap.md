---
layout: post
title: ListからMapに変換するメソッド
tags: [Java]
---
ListからMapに変換するメソッドです。

{% highlight Java  %}
/**
 * リストをマップに変換
 * 
 * @param <K>
 *            キーの型
 * @param <V>
 *            値の型
 * @param list
 *            値のリスト
 * @param keyMapper
 *            値からキーを取り出す方法
 * @return マップ（引数がnullの場合は空）
 */
public static <K, V> Map<K, V> toMap(List<V> list, Function<V, K> keyMapper) {
	Map<K, V> map = new HashMap<>();
	// 引数が不正の場合は空のマップを返す
	if (list == null || keyMapper == null) {
		return map;
	}

	// nullは例外ではなく無視したいので使わない
	// return list.stream().collect(Collectors.toMap(keyMapper, e -> e));

	list.forEach(value -> {
		// nullは無視
		if (value == null) {
			return;
		}
		K key = keyMapper.apply(value);
		if (key == null) {
			return;
		}
		map.put(key, value);
	});
	return map;
}

{% endhighlight %}



使用例は以下のような感じ。Userは適当なクラスです。
最近ようやくラムダ式が使えるようになりました。


{% highlight Java  %}
List<User> userList = new ArrayList<>();

// データを入れる部分は省略

Map<Integer, User> userMap = toMap(userList, user -> user.getId());
{% endhighlight %}

