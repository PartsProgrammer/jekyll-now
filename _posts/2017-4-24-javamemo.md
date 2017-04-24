---
layout: post
title: メモ
tags:[java]
---

<br>
〇boolean
×bool
〇 b = a += 5;
×byte a = 0b1000000;（2の補数で代入は不可）
×float a = 1.0; (実数のデフォルトはdouble)
short 2B  -32768 ～ 32767
++num + num * num * 10000 = 1210011(インクリメントが先に処理)
&&ショートサーキット、&必ず右も評価
equals(Object obj){return this == obj;}参照の比較
	オーバーライド、型注意
else \n if -> else { if }
switch 〇String  ×long
〇new int[0]
〇int [][]array; int []array[];
×int [2]array;参照をいれるしかできない
×int [][2]array;
×new int[];（要素数を指定する必要がある）
×new int[2]{2,3};
〇int[] array = {};
〇int[][] array ={};
〇Object ob = インターフェース型の変数;
〇System.arraycopy(Object?src, int?srcPos, Object?dest, int?destPos, int?length)srcPosからsrcPos+length-1要素を、destPosからdestPos+length-1までの位置にコピー
〇int[][] a = new int[2][];
×int[][] b = new int[][2];
new Item[3]() nullが3つ入った配列が生成（インスタンスはまだできない）
do while の中は{}なしなら1文のみ
×for(int i = 0, long j = 0 初期化は同じ型のみ
〇for(;;)無限ループ
for(Object a : array) →　Object a = array[i]; コピーされる、配列の参照先の変更は不可
ラベルを使うことで、breakやcontinueの先を指定できる
sample: 
        
for(;;){

	break sample;
        
}
// ここに移動（先にラベルが定義されてないとエラー）
ラベルはブロック、文、式（文じゃない要素）にはれる
〇void multi(int... num){}可変長は最後のみ許される
×return;System.out.println();到達不可能なコード
アクセス修飾子なし→同じパッケージ
あいまいなメソッド呼び出しはコンパイルエラーambiguous(1,1); (float, int) (int, float)
コンストラクタに戻り値→メソッド（コンパイルは通る）
public class Initiate{
	{
		// 初期化ブロック（コンストラクタの前）
	}
}

protected 同じパッケージでもOK
違うパッケージのサブクラスからのアクセスのみ、protectedとなしは違う
継承してもコンストラクタ、privateなフィールドやメソッドは引き継がない
オーバーライドしたメソッドは厳しいアクセス制御に変更できない
同名フィールドはインスタンスが保存された変数の型に従う
変数はコンパイル時に決定、インスタンスは不明
キャストの失敗は例外、×コンパイルエラー
スコープで変数の隠蔽は行われない
int num;
{
	int num; // コンパイルエラー
	int value;
}
int value; // ok
フィールドと同じ名前のローカル変数はok (thisをおもいだす)
継承してもフィールドは別々（同名フィールドはクラスの型で区別）











<br>


