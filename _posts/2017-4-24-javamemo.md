---
layout: post
title: Javaメモ
tags: [Java]
---

<br>
{% raw %}
〇boolean<br>
×bool<br>
〇 b = a += 5;<br>
×byte a = 0b1000000;（2の補数で代入は不可）<br>
×float a = 1.0; (実数のデフォルトはdouble)<br>
short 2B  -32768 ～ 32767<br>
++num + num * num * 10000 = 1210011(インクリメントが先に処理)<br>
&&ショートサーキット、&必ず右も評価<br>
equals(Object obj){return this == obj;}参照の比較<br>
	オーバーライド、型注意<br>
else \n if -> else { if }<br>
switch 〇String  ×long<br>
〇new int[0]<br>
〇int [][]array; int []array[];<br>
×int [2]array;参照をいれるしかできない<br>
×int [][2]array;<br>
×new int[];（要素数を指定する必要がある）<br>
×new int[2]{2,3};<br>
〇int[] array = {};<br>
〇int[][] array ={};<br>
〇Object ob = インターフェース型の変数;<br>
〇System.arraycopy(Object?src, int?srcPos, Object?dest, int?destPos, int?length)<br>
srcPosからsrcPos+length-1要素を、destPosからdestPos+length-1までの位置にコピー<br>
〇int[][] a = new int[2][];<br>
×int[][] b = new int[][2];<br>
new Item[3]() nullが3つ入った配列が生成（インスタンスはまだできない）<br>
do while の中は{}なしなら1文のみ<br>
×for(int i = 0, long j = 0 初期化は同じ型のみ<br>
〇for(;;)無限ループ<br>
for(Object a : array) →　Object a = array[i]; コピーされる、配列の参照先の変更は不可<br>
ラベルを使うことで、breakやcontinueの先を指定できる<br>
sample: <br>
        <br>
for(;;){<br>
<br>
	break sample;<br>
        <br>
}<br>
// ここに移動（先にラベルが定義されてないとエラー）<br>
ラベルはブロック、文、式（文じゃない要素）にはれる<br>
〇void multi(int... num){}可変長は最後のみ許される<br>
×return;System.out.println();到達不可能なコード<br>
アクセス修飾子なし→同じパッケージ<br>
あいまいなメソッド呼び出しはコンパイルエラーambiguous(1,1); (float, int) (int, float)<br>
コンストラクタに戻り値→メソッド（コンパイルは通る）<br>
public class Initiate{<br>
	{<br>
		// 初期化ブロック（コンストラクタの前）<br>
	}<br>
}<br>
<br>
protected 同じパッケージでもOK<br>
違うパッケージのサブクラスからのアクセスのみ、protectedとなしは違う<br>
継承してもコンストラクタ、privateなフィールドやメソッドは引き継がない<br>
オーバーライドしたメソッドは厳しいアクセス制御に変更できない<br>
同名フィールドはインスタンスが保存された変数の型に従う<br>
変数はコンパイル時に決定、インスタンスは不明<br>
キャストの失敗は例外、×コンパイルエラー<br>
スコープで変数の隠蔽は行われない<br>
int num;<br>
{<br>
	int num; // コンパイルエラー<br>
	int value;<br>
}<br>
int value; // ok<br>
フィールドと同じ名前のローカル変数はok (thisをおもいだす)<br>
継承してもフィールドは別々（同名フィールドはクラスの型で区別）<br>
catch(スーパー)<br>
catch(サブ)//到達不可能でコンパイルエラー<br>
×try finally catch<br>
return は専用の変数があると思え（値コピー、finallyで元の変数を変えても無意味）<br>
try finally は1つのみ<br>
エラー：プログラムからは対処しようがない、非検査Errorとサブ、実行環境に例外が発生したとき（メモリ不足、権限、接続）<br>
例外：プログラムが対処できる<br>
  検査例外  ：コンパイラが処理の記述を検査Exceptionとサブ（Runtimeを除く）<br>
  非検査例外：コンパイラが処理の記述を検査しない(RuntimeExceptionとサブ)<br>
起動パラメータなし→argsは長さ0の配列<br>
〇List<String> list = new ArrayList<>();<br>
static{} クラスを利用するときに一度だけ呼ばれる（例外発生時はExceptionInInitializerErrorに変換される）、static変数の初期化に使われる<br>
実行対象のクラスファイルを発見できない→NoClassDefFoundError<br>
{% endraw %}








<br>


