# GitHubLessons
Lessons on working on GitHub.

GitHubを使う練習のためのリポジトリ。
ISMR11, IS12クラスで利用するために作成した。
20161205, 20161214 by yt.


## "ひとりで開発"する場合に必要なこと

自分のリポジトリ( repository; 160999 )を確認して、ブランチ( branch )をつくる。コード( code )を書いてマージ( merge )し、pushする。

0. 自分のリポジトリを確認する.
	
	webサイト側( https://github.com/ )に,元となるリポジトリ( 160999, etc. )があるか確認する.

	- ログインして所有するリポジトリを確認する
		- GitHub IDが必要
		- GitHub パスワードが必要
	- リポジトリのwebページにアクセスする
	- Collaboratorの設定を確認する
		- ユーザ: yoshinotaichi が登録されているか
		- ↑なければ登録する

	同じリポジトリがPCにもある( cloneしてある )か確認する.なければ clone する.

	```bash
	cd
	cd documents
	cd github
	ls
	```

	↑この時点で "160999" などのdirが表示されるはず.なければ clone してダウンロードする.

	```bash
	git clone https://github.com/yoshinotaichi/160999.git
	ls
	```

	dirがあるか確認する.あればOK.



1. 自分のリポジトリを確認する

	Commitしていないファイルがあるか, 確認する.

	```bash
	cd
	cd documents
	cd github
	cd 160999
	git status
	```

	もし, Commitしていないファイルがあれば, Commitする.

	```bash
	git add .
	git commit -m "コメントを書く"
	git status
	```


2. 今日のブランチ( branch; 20161214 など )をつくる.

	160999リポジトリ( repository )のdirにアクセスする.

		```bash
		cd
		cd documents
		cd github
		cd 160999
		pwd
		ls
		```

	今日のブランチ( branch )をつくる.名前を日付( 20161214 など )にする.

		```bash	
		git branch
		git checkout -b 20161214
		git branch
		```

3. コード( code )を書く & コンパイル & 実行する & Commitする

	Javaのdirがあればアクセスする.なければつくる.

	```bash
	ls
	mkdir Java
	cd Java
	pwd
	```

	Javaの code を書く.
	- file: Aloha160999.java

	```java:Aloha160999.java
	public class Aloha160999 {
	  public static void main(String[] args) {
	    System.out.println("ALOHA!");
	  }
	}
	```

	保存して, コンパイル & 実行する.

	```bash
	javac -encoding utf8 Aloha160999.java
	java Aloha160999
	```

	Commitする.
	
	```bash
	git status
	git add .
	git commit -m "Aloha160999.java done."
	```

4. mergeする

	今日のブランチ( branch )を, masterブランチ( branch )にマージmergeする.

	リポジトリ( repository )のdirに移動する.

	```bash
	cd
	cd documents
	cd github
	cd 160999
	```

	masterブランチにきりかえる.

	```bash
	git branch
	git checkout master
	git branch
	```

	今日のブランチをマージ( merge )する.

	```bash
	git merge 20161214
	```

5. pushする

	リポジトリをpushする( github.com にアップロードする ).

	```bash
	git push origin master
	```

	Google Chromeで github.com の自分のリポジトリ( repository )にアクセスして, アップロードされているか確認する.

	


## グループで開発するときに必要なこと. pull-req( プルリク )とmerge( マージ )

pull-reqしてmergeされた結果を知る。
チーム開発でGitHubを用いる際のイメージ。

1. repo: GitHubLessons を clone する.

	```bash
	cd documents
	cd github
	git clone http://github.com/yse2016/GitHubLessons.git

	ls
	cd GitHubLessons
	```

2. local repoで branch を作る.
	- branch: 160999( 学籍番号 )

	```bash
	git status
	git branch
	git checkout -b 160999
	git branch
	```

3. 自分の branch でHTMLページを作る.
	- 160999.html( 学籍番号.html )

	```bash
	vi 160999.html
	```

	```html
	<!DOCTYPE html>
	<html>
	<head>
		<meta charset="utf-8">
		<title>GitHubLessons: 160999</title>
	</head>
	<body>
		<h1>160999</h1>
		GitHub練習中	
	</body>
	</html>
	```

4. add, commit, push する

	```bash
	git status
	git add .
	git status
	git commit -m "160999.html added."
	git status
	git push origin 160999
	```

5. webブラウザで、remote にも branch: 160999 があるのを確かめる.

6. webブラウザで、pull-req を作る.

7. 誰かに merge してもらう.
	- reviewer( レビュアー )役は、local に branch を作り、内容を確認してから merge する.
		- reviewer は、codeを読む
		- reviewer は、htmlファイルをwebブラウザで表示させて妥当であるか確かめる.
		- reviewer は、↑が妥当でない時は、merge せずに comment のみ送り、修正を促す.

	```bash
	git checkout -b 160999 origin/160999
	```

8. webブラウザで、remoto の master ( origin/master )に、"160999.html" があるのを確かめる.



end.
