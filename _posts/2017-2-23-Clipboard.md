---
layout: post
title: クリップボード
tags:
- java
---



ClipboardController.java

{% highlight Java  %}
import java.util.Calendar;

import java.awt.datatransfer.Clipboard;
import java.awt.datatransfer.StringSelection;
import java.awt.Toolkit;

public class ClipboardController {
	/**
	 * システムクリップボード
	 */
	private static final Clipboard clipboard = Toolkit.getDefaultToolkit().getSystemClipboard();

	
	/**
	 * コピーする文字列
	 */
	private String str = "";
	
	/**
	 * 内部の文字列を取得
	 * @return
	 */
	public String getStr(){
		return str;
	}


	/**
	 * @param str コピーする文字列
	 */
	public void copyStr(String str) {
		this.str = str;

		// クリップボードの内容を作成
		StringSelection content = new StringSelection(str);
		
		// クリップボードにコピー
		clipboard.setContents(content, content);
		//lostOwnerShipを実装すべき？
	}



	/**
	 * テスト用
	 * 現在時刻をクリップボードへコピーする
	 * @param args
	 */
	public static void main(String[] args) {
		String time = Calendar.getInstance().getTime().toString();
		new ClipboardController().copyStr(time);
		System.out.println(time);
	}

}

{% endhighlight %} 

