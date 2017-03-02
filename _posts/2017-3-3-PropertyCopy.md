---
layout: post
title: インスタンスのフィールドをコピー
tags: [Java]
---

org.apache.commons.beanutils.BeanUtilsの
copyPropertiesメソッドを知らずに自作してしまった。
<br>
ライブラリを入れたくない場合もあるかもしれないので公開
（引数がnullの場合は例外を投げてもよいかもしれない）
<br>
<br>


PropertyCopy.java

{% highlight Java  %}
import java.beans.IntrospectionException;
import java.beans.Introspector;
import java.beans.PropertyDescriptor;

public class PropertyCopy {
	public static void copyProperties(Object dest, Object orig) {
		// nullの場合なにもしない
		if (dest == null || orig == null) {
			return;
		}
		
		try {
			// コピー元オブジェクトのプロパティを全て取得
			PropertyDescriptor[] propertiesOrig = Introspector.getBeanInfo(orig.getClass()).getPropertyDescriptors();
			for (PropertyDescriptor propertyOrig : propertiesOrig) {
				try{
				// コピー先オブジェクトの同名プロパティを取得
					PropertyDescriptor propertyDest	= new PropertyDescriptor(propertyOrig.getName(), dest.getClass());
					// 値がコピーできる場合はコピー
					if (propertyOrig.getReadMethod() != null && propertyDest.getWriteMethod() != null) {
						Object value = propertyOrig.getReadMethod().invoke(orig);
						propertyDest.getWriteMethod().invoke(dest, value);
					}
				}catch(IntrospectionException ex){
					// 同名プロパティの取得失敗時はとばす
				}
			}
		} 
		catch(Exception ex){
			// 例外は無視
		}
	}
	
	/**
	 * テスト用
	 */
	public static void main(String[] args) {
		Test orig = new Test("string", 2017);
		Test dest = new Test();
		copyProperties(dest, orig);
		System.out.println(dest);
	}
}
/**
 * テスト用データクラス
 */
class Test{
	private String str;
	private int num;
	
	public Test(){}
	public Test(String str, int num){
		this.str = str;
		this.num = num;
	}
	
	public String getStr(){return str;}
	public void setStr(String str){this.str = str;}
	
	public int getNum(){return num;}
	public void setNum(int num){this.num = num;}
	
	@Override
	public String toString(){
		return str + num;
	}
	
}


{% endhighlight %} 

