# TUS-ME_thesis_template

東京理科大学創域理工学部機械航空宇宙工学科および大学院創域理工学研究科機械航空宇宙工学専攻の【非公式】学位論文テンプレートです．
塚原研究室は熱流体系の研究室ですが，同学科・同専攻であれば所属研究室によらずこのテンプレートを使用可能です．
パブリックリポジトリなので，他研究室所属の方もご自身の PC に入れることができます．
使用する際に塚原研究室の許可を取る必要はありませんが，このテンプレートを使用したことで生じた問題に関して大学・学科・塚原研究室および研究室に所属する個人は一切の責任を負いませんのでご了承ください．

## 学位論文 ToDO リスト（使いやすいように書き換えてください）

- [ ] 第 m 章完成目標（xx 月 xx 日）
- [ ] 第 n 章完成目標（xx 月 xx 日）
- [ ] 〇〇さんのチェック（xx 月 xx 日）
- [ ] 〇〇先生のチェック（xx 月 xx 日）
- [ ] 提出（xx 月 xx 日）

## リポジトリ内のファイル構成

- `abstract/`: 卒論・修論要旨のテンプレート
- `chapter/`: 分割した `tex` ファイルを格納
- `figure/`: 論文で使用する図を格納
- `template-manual/`: 学位論文テンプレートの説明書を格納
- `.gitignore`: Git で管理しないファイル一覧
- `README.md`: このファイル
- `jsme.bst`: 日本機械学会対応の BibTeX スタイルファイル
- `latexmkrc`: LaTeX のコンパイル設定
- `main.pdf`: `main.tex` の実行結果
- `main.tex`: メインの文書ファイル（これをコンパイルすればよい）
- `mybib_en.bib`: 英語の参考文献リストファイル
- `mybib_jp.bib`: 日本語の参考文献リストファイル
- `settings.sty`: `main.tex` で読み込むスタイルファイル

## 卒論・修論用リポジトリの作成

ここでは学位論文用リポジトリの作成方法を説明します．

1. Organization ではなく個人の GitHub アカウントに空のリポジトリを作成．ここでは仮に `master_thesis` というリポジトリ名にする．**リポジトリ作成時に `README.md` や `.gitignore` は作成しない．**
2. Private になっていることを確認したら Create repository を押す．
3. このテンプレートのリポジトリをローカルにクローンする．

例えば塚原先生（`tsukapom`）が修士論文を執筆する場合：

```bash
# ローカルにテンプレートをクローン
git clone https://github.com/tsukahara-lab/TUS-ME_thesis_template master_thesis
cd master_thesis

# リモート URL を自身のものに変更
git remote set-url origin https://github.com/tsukapom/master_thesis

# URL の変更が反映されているか確認
git remote -v

# 自身のリモートリポジトリにテンプレートの中身を反映
git push origin HEAD
```

これでテンプレートの中身が自身の学位論文リポジトリに反映されたので自由に編集して大丈夫です．

## テンプレートへの修正の反映

この学位論文テンプレートが更新された場合は，以下のコマンドを実行して自身のリポジトリに反映してください．

```bash
# この学位論文テンプレートのリポジトリを登録
git remote add upstream https://github.com/tsukahara-lab/TUS-ME_thesis_template.git

# テンプレートの最新状態を取得
git fetch upstream

# 自分が main ブランチにいることを確認し，テンプレートの最新状態をマージ
git switch main && git merge upstream/main

# 自身のリモートリポジトリを更新
git push origin HEAD
```

## 添削時の注意点

### `latexdiff` を用いた差分管理

```bash
latexdiff -e utf8 -t CFONT --flatten old.tex new.tex > diff.tex
latexmk diff.tex
```

### `latexdiff-vc` を用いた差分管理

```bash
latexdiff-vc -e utf8 -t CFONT --flatten --git --force -r HEAD^ main.tex
latexmk diff.tex
```

### `latexdiff-vc` を使用する際の注意事項（Windows ユーザー向け）

`latexdiff-vc` を Windows で使用する際に実行できない不具合を確認しています．
これに関してはデバッグしたファイルを [`latexdiff-vc_windows`](https://github.com/Yuki-MATSUKAWA/latexdiff-vc_windows) で公開しているので，Windows ユーザーは `latexdiff-vc` を使用する前に [README](https://github.com/Yuki-MATSUKAWA/latexdiff-vc_windows?tab=readme-ov-file#readme) をよく読んで，`latexdiff-vc.pl` を TeX Live 標準のものから置き換えてください．

## 卒業論文執筆における注意事項

以下の内容は東京理科大学創域理工学部機械航空宇宙工学科の卒業論文執筆要領（2023 年度版）を基に作成しています．
このリポジトリ内のテンプレート通りに使用すれば問題ありません．
修士論文では本論執筆の注意事項は特に明記されていません（修士論文要旨に関しては注意事項あり）が，卒業論文と同様のフォーマットを使用するのが理想的だと思います．
ただし，博士論文の場合は異なるフォーマットが要求され，このテンプレートをそのまま使用することはできないので注意が必要です．

1. 用紙，マージン等
    - 用紙サイズは A4，1 ページ 40 字 × 40 行程度とする．
    - 上 20 mm，下 15 mm，左 25 mm，右 10 mm のマージンをとる．
    - 本文フォント
        - 和文：明朝体，12 pt
        - 欧文：Times，12 pt
    - 章題目フォント
        - ゴシック体，12--16 pt
2. 本論文には，表紙をつける．
    - 上 25 mm，下 15 mm，左 25 mm，右 10 mm のマージンをとる（表紙のみ上のマージンが異なるので注意）．
    - 表紙の文字は全て明朝体 12 pt（題名のみ 18 pt）で中央寄せとする．
    - 2019 年度卒業論文より，和暦（平成，令和）から西暦に統一．
    - 表紙では年度と学籍番号を「全角数字で」書くこと．
    - 上から 8 行空けて「＊＊＊＊年度卒業論文」（修士論文の場合は「＊＊＊＊年度修士論文」）と書く．
    - 2 行空けて題名を書く．
    - 9 行空けて「＊＊＊＊年＊月」．
    - 2 行空けて「東京理科大学創域理工学部機械航空宇宙工学科」．
    - 1 行空けて「〇〇研究室」．
    - 3 行空けて「７５＊＊＊＊＊　　姓姓　名名」と書く．学籍番号と姓の間は全角スペースを二つ分挿入，姓と名の間は全角スペースを一つ分挿入すること．連名の場合は下の行に続ける．
3. 図と表も A4 サイズの中におさまるようにする．
4. 用語・数字・英字等の記述方法は「[日本機械学会論文集 ---投稿論文作成について---](https://www.jsme.or.jp/publish/Japanese-conference-Template-mihon.pdf)」に準ずる．ただし，上記機械学会の様式では参考文献を，「文献」「References」と二重に記載しているが，「文献」部分を参考にして作成し，重複させなくてよい．
5. その他不明な点は，教務幹事に聞くこと．
6. 論文構成後半部：結論 → 謝辞 → 参考文献 →（付録）の順序で統一する．
7. 図は説明文がある章の中に入れる．
8. 目次の各項目の右端にページ番号を入れる．緒言からページ番号をつける．
9. 序論（緒論）--結論，緒言--結言，はじめに--おわりに（まとめ）と対になって使われるので，混ぜて使わない．

