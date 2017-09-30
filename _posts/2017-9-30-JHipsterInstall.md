---
layout: post
title: JHipsterの環境構築
tags: []
---

環境：windows10<br>
<a href="http://www.jhipster.tech/installation/">Installing JHipster</a>を参考にした
### Java8をインストール
<a href="http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html">JDK 8</a>
からAccept License Agreementにチェックをいれて、
OSに適したものをダウンロード・インストール

![Java ダウンロード]({{site.baseurl}}/images/JavaDownload.png)


### Node.jsをインストール
<a href="https://nodejs.org/en/">Node.js</a>からダウンロード・インストール<br>
コマンドプロンプトで以下を実行
<p>
npm install -g npm
</p>

### Yeomanをインストール
コマンドプロンプトで以下を実行
<p>
npm install -g yo
</p>


### Angularをインストール
コマンドプロンプトで以下を実行
<p>
npm install -g @angular/cli
</p>


### JHipsterをインストール
コマンドプロンプトで以下を実行
<p>
npm install -g generator-jhipster
</p>


![コマンドプロンプト]({{site.baseurl}}/images/JHipsterInstall.png)

(環境構築終了)
### JHipsterで新規プロジェクト作成
<a href="http://www.jhipster.tech/">JHipster</a>のQuick Startを参考
コマンドプロンプトで以下を実行
<p>
mkdir myApp<br>
cd myApp<br>
jhipster
</p>
あとは色々聞かれるので画面の指示に従う

### spring実行
コマンドプロンプトで以下を実行
<p>
.\mvnw
</p>

<div style="padding: 10px; margin-bottom: 10px; border: 1px dotted #333333;">
<p>
	<font color="grey">
		<u>JAVA_HOME not foundが出た場合</u><br><br>
		環境変数にJAVA_HOMEを追加する
		<ul>
		<li>Windowsキー+pause</li>
		<li>システムの詳細設定</li>
		<li>環境変数</li>
		<li>システム環境変数の新規</li>
		<li>変数名にJAVA_HOME</li>
		<li>変数値にjavaをインストールしたディレクトリを指定
			<br>（例）C:\Program Files\Java\jdk1.8.0_144</li>
		<li>再起動</li>
		</ul>
		</font>
</p>
</div>


### Angular実行
springとは別のウィンドウのコマンドプロンプトで以下を実行
<p>
 npm start
</p>

<a href="http://localhost:9000">localhost:9000</a>にアクセスし、以下のようなページが開けば成功


![実行画面（英語）]({{site.baseurl}}/images/JHipsterStartpage.png)

日本語には標準では対応してない（おそらく翻訳ファイルを用意すればよいが、未調査）
![実行画面（日本語）]({{site.baseurl}}/images/JHipsterStartpageJP.png)

### 実行終了
終了したい場合は実行しているコマンドプロンプトで以下を実行
<p>
ctrl+c<br>
y
</p>

