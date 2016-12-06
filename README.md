# GitHubLessons
Lessons on working on GitHub.

GitHubを使う練習のためのリポジトリ。
ISMR11, IS12クラスで利用するために作成した。
20161205 by yt.


## pull-req( プルリク )とmerge( マージ )

pull-reqしてmergeされた結果を知る。
チーム開発でGitHubを用いる際のイメージ。

1. repo: GitHubLessons を clone する.

	```bash
	cd documents
	cd github
	git clone http://github.com/yoshinotaichi/GitHubLessons.git

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