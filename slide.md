---
marp: true
theme: hci-purple
paginate: true
---

<!--
class: slides
-->
# Week 2

## 開発環境とチーム開発の入口

### GitHub・Codespaces・Gitで安全に作り始める

<!--
_class: title
-->

---

<style scoped>
h1 {
    text-align: center;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
h2 {
    text-align: left;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
</style>

# 今日やること

---

## 今日は「チーム全員が同じ流れで開発できる状態」を作る

1. MVP（最小限だけど価値が伝わる形）を決める
2. GitHub（ネット上のコード置き場）を用意する
3. Codespaces（ブラウザで開く開発用PC）を起動する
4. Branch（自分専用の安全な作業部屋）を作る
5. Commit（変更のセーブポイント）を作る
6. Push（ネット上のコード置き場へ送る）する
7. Pull Request / PR（合体前の確認依頼）を出す

---

## Week 2のゴール

**「小さく作る → 確認する → 共有する」までを1回通す**

- GitHub（ネット上のコード置き場）にチームのコードを置く
- Codespaces（ブラウザで開く開発用PC）で全員同じ環境を開く
- Branch（自分専用の安全な作業部屋）で作業する
- Pull Request / PR（合体前の確認依頼）を作る

<!-- TODO: スクショ: Week2チェックリスト -->

---

<style scoped>
h1 {
    text-align: center;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
h2 {
    text-align: left;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
</style>

# まずは全体像

---

## 開発は「大元」と「自分の作業部屋」を分ける

- main（発表に使う完成版の置き場）を直接いじらない
- Branch（自分専用の安全な作業部屋）を作って作業する
- Commit（変更のセーブポイント）で作業を記録する
- Pull Request / PR（合体前の確認依頼）でmain（完成版の置き場）に入れる

<!-- TODO: 図: mainからfeatureブランチが分かれて戻る図 -->

---

## なぜmain（完成版の置き場）を直接いじらないのか

main（完成版の置き場）を全員で同時に編集すると、壊れやすいから。

- 誰かの変更を上書きしてしまう
- 動いていたアプリが急に壊れる
- どの変更が原因かわからなくなる
- 同じ場所を編集してConflict（変更の衝突）が起きる

**Branch（自分専用の安全な作業部屋）を使うと、完成版を守りながら作業できる。**

---

## Git（変更履歴を残す道具）が必要な理由

Git（変更履歴を残す道具）は、チームで安全に分担するために使う。

- 誰が、いつ、何を変えたか残る
- 前の状態に戻せる
- 担当機能ごとにBranch（自分専用の安全な作業部屋）を分けられる
- Pull Request / PR（合体前の確認依頼）で確認してからmain（完成版の置き場）に入れられる

---

## GitHub（ネット上のコード置き場）が必要な理由

GitHub（ネット上のコード置き場）は、チーム全員で同じコードを共有する場所。

- チームのコードを1か所に置ける
- Pull Request / PR（合体前の確認依頼）で差分を見られる
- Codespaces（ブラウザで開く開発用PC）を起動できる
- 家のPCでも学校PCでも同じコードにアクセスできる

---

<style scoped>
h1 {
    text-align: center;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
h2 {
    text-align: left;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
</style>

# MVPを決める

---

## MVP（最小限だけど価値が伝わる形）を1つに絞る

MVP（最小限だけど価値が伝わる形）は、発表で30秒デモできる一番小さい流れ。

- 最初から全部作らない
- 「誰の何の困りごとを解決するか」を残す
- 画面や機能を増やしすぎない
- 今週は「最初の1画面」か「最初の1機能」でよい

---

## MVP（最小限だけど価値が伝わる形）の決め方

次の4つだけを決める。

1. 使う人は誰か
2. 何に困っているか
3. 最初に見せる画面は何か
4. 最初にできる操作は何か

<!-- TODO: スクショ: MVPメモの例 -->

---

## MVP（最小限だけど価値が伝わる形）の例

例：履修相談アプリ

- 使う人：履修登録で迷っている1年生
- 困りごと：先輩の意見が見つけにくい
- 最初の画面：授業一覧
- 最初の操作：授業を選ぶとコメントが見られる

**Week 2で作るMVP（最小限だけど価値が伝わる形）：授業一覧 → 授業詳細 → コメント表示**

---

<style scoped>
h1 {
    text-align: center;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
h2 {
    text-align: left;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
</style>

# GitHubを用意する

---

## まずGitHub（ネット上のコード置き場）のアカウントを作る

GitHub（ネット上のコード置き場）を使うには、各自のアカウントが必要。

1. https://github.com にアクセス
2. Sign up（アカウント登録）を押す
3. メールアドレスなどを入力する
4. GitHubユーザー名（GitHub上の名前）をチームに共有する

<!-- TODO: スクショ: GitHub Sign up画面 -->

---

## 代表者がRepository（チームのコード箱）を作る

Repository（チームのコード箱）は、GitHub（ネット上のコード置き場）上でコードを入れる箱。

1. New repository（新しいコード箱）を押す
2. Repository name（コード箱の名前）を決める
3. Private（チームだけが見られる設定）で作る
4. README（最初の説明ファイル）ありで作る

<!-- TODO: スクショ: New repository画面 -->

---

## Collaborator（共同編集できる人）にチームメンバーを招待する

Collaborator（共同編集できる人）に入っていない人は、同じRepository（チームのコード箱）で作業できない。

1. Settings（設定）を開く
2. Collaborators（共同編集できる人）を開く
3. Add people（人を追加）を押す
4. GitHubユーザー名（GitHub上の名前）で招待する
5. 招待された人は承認する

<!-- TODO: スクショ: Collaborators画面 -->

---

<style scoped>
h1 {
    text-align: center;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
h2 {
    text-align: left;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
</style>

# Codespacesを開く

---

## Codespaces（ブラウザで開く開発用PC）を使う

Codespaces（ブラウザで開く開発用PC）は、GitHub（ネット上のコード置き場）が貸してくれる開発環境。

- 学校PCでも家のPCでも同じ環境になる
- MacでもWindowsでも差が出にくい
- Node.js（JavaScriptを動かす道具）などを自分で入れなくてよい
- 「自分のPCでは動くのに、相手のPCでは動かない」を減らせる

---

## Codespaces（ブラウザで開く開発用PC）を起動する

1. GitHub（ネット上のコード置き場）でRepository（チームのコード箱）を開く
2. 緑色のCode（コード操作メニュー）を押す
3. Codespaces（ブラウザで開く開発用PC）タブを開く
4. Create codespace on main（完成版の置き場から開発用PCを作る）を押す
5. ブラウザ上でVS Code（コードを書く画面）が開く

<!-- TODO: スクショ: Code → Codespaces → Create codespace on main -->

---

## Codespaces（ブラウザで開く開発用PC）は止め忘れに注意

Codespaces（ブラウザで開く開発用PC）は、開いたままだと利用時間を消費することがある。

- 作業が終わったらStop（停止）する
- 次回は同じCodespaces（ブラウザで開く開発用PC）を再開できる
- 消してもGitHub（ネット上のコード置き場）にPush（ネット上のコード置き場へ送る）済みなら安全

<!-- TODO: スクショ: CodespacesのStopボタン -->

---

<style scoped>
h1 {
    text-align: center;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
h2 {
    text-align: left;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
</style>

# 自分の作業部屋を作る

---

## Branch（自分専用の安全な作業部屋）を作る

Branch（自分専用の安全な作業部屋）は、main（完成版の置き場）から分かれた自分用の作業場所。

- main（完成版の置き場）を直接壊さない
- 自分の担当だけ集中して作れる
- 失敗してもmain（完成版の置き場）には影響しない
- 完成したらPull Request / PR（合体前の確認依頼）で合体をお願いする

---

## VS Code（コードを書く画面）からBranch（自分専用の安全な作業部屋）を作る

1. 左下のmain（完成版の置き場）をクリック
2. Create new branch（新しい作業部屋を作る）を選ぶ
3. 作業内容がわかる名前をつける
4. 左下の表示がmain（完成版の置き場）から新しい名前に変わったらOK

例：`feature/top-page`

<!-- TODO: スクショ: VS Code左下のmain → Create new branch -->

---

## Branch（自分専用の安全な作業部屋）の名前は内容がわかるようにする

よい名前：

- `feature/top-page`
- `feature/course-list`
- `fix/header-layout`

よくない名前：

- `aaa`
- `test`
- `my-branch`

**Branch（自分専用の安全な作業部屋）は「何をする場所か」が名前でわかるようにする。**

---

<style scoped>
h1 {
    text-align: center;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
h2 {
    text-align: left;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
</style>

# 少しだけ変更して記録する

---

## Commit（変更のセーブポイント）を作る

Commit（変更のセーブポイント）は、「ここまでの変更」をメモ付きで記録すること。

- ただファイル保存するだけではGit（変更履歴を残す道具）には記録されない
- 何を変えたかメモを残す
- 後から見たときに作業内容がわかる
- 戻したいときの目印になる

---

## テストとしてREADME（最初の説明ファイル）を少し変える

1. 左のファイル一覧からREADME.md（最初の説明ファイル）を開く
2. 文字を少し足す
3. Source Control（変更を記録する画面）を開く
4. README.md（最初の説明ファイル）が変更一覧に出ていることを確認する

<!-- TODO: スクショ: README.mdを開いて編集する画面 -->

---

## Commit（変更のセーブポイント）にはメッセージを書く

1. Source Control（変更を記録する画面）を開く
2. Message（変更メモ）に何をしたか書く
3. Commit（変更のセーブポイントを作る）を押す

よいメッセージ：

```text
テストでREADMEに文字を追加
```

<!-- TODO: スクショ: Source ControlのMessage欄とCommitボタン -->

---

## Commit（変更のセーブポイント）のメッセージは具体的にする

よい例：

- トップページを作成
- 授業一覧の仮データを追加
- READMEにセットアップ手順を追加

よくない例：

- 修正
- いろいろ
- test

---

<style scoped>
h1 {
    text-align: center;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
h2 {
    text-align: left;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
</style>

# ネット上のコード置き場へ送る

---

## Push（ネット上のコード置き場へ送る）をする

Commit（変更のセーブポイント）は、まだ今開いているCodespaces（ブラウザで開く開発用PC）の中だけにある。

- GitHub（ネット上のコード置き場）へ送る必要がある
- これをPush（ネット上のコード置き場へ送る）と呼ぶ
- Push（ネット上のコード置き場へ送る）すると、チームメンバーも変更を見られる

---

## VS Code（コードを書く画面）からPush（ネット上のコード置き場へ送る）する

1. Source Control（変更を記録する画面）を開く
2. Sync Changes（送る・受け取るをまとめて行う）を押す
3. GitHub（ネット上のコード置き場）にBranch（自分専用の安全な作業部屋）が作られる
4. GitHub（ネット上のコード置き場）で変更が見えるようになる

<!-- TODO: スクショ: Sync Changesボタン -->

---

## コマンドでやる場合はこの4つ

```bash
git switch -c feature/top-page
git add .
git commit -m "トップページを作成"
git push -u origin feature/top-page
```

- `git switch -c`：Branch（自分専用の安全な作業部屋）を作って移動
- `git add .`：Commit（変更のセーブポイント）に入れる変更を選ぶ
- `git commit`：Commit（変更のセーブポイント）を作る
- `git push`：Push（ネット上のコード置き場へ送る）する

---

<style scoped>
h1 {
    text-align: center;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
h2 {
    text-align: left;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
</style>

# 合体の確認依頼を出す

---

## Pull Request / PR（合体前の確認依頼）を作る

Pull Request / PR（合体前の確認依頼）は、

**「自分の作業をmain（完成版の置き場）に入れていいですか？」というお願い。**

- チームメンバーに変更を見てもらう
- main（完成版の置き場）に入れる前に確認する
- 変な変更が混ざっていないか見る
- 問題なければMerge（完成版の置き場に合体）する

---

## GitHub（ネット上のコード置き場）でPull Request / PR（合体前の確認依頼）を作る

1. GitHub（ネット上のコード置き場）でRepository（チームのコード箱）を開く
2. Compare & pull request（比べて確認依頼を作る）を押す
3. タイトルを書く
4. 変更内容を書く
5. Create pull request（確認依頼を作る）を押す

<!-- TODO: スクショ: Compare & pull request画面 -->

---

## Pull Request / PR（合体前の確認依頼）には3つを書く

```md
## 目的
トップページを作成する

## 変更内容
- トップページ用の表示を追加
- 仮の見出しと説明文を追加

## 確認方法
- 画面表示を確認
- build（完成品として作れるか確認）が成功
```

---

## Files changed（変更差分の確認画面）を見る

Files changed（変更差分の確認画面）では、何が変わったかを確認できる。

- 意図しないファイルを変えていないか
- 消してはいけないコードを消していないか
- main（完成版の置き場）に入れてよい内容か
- Conflict（変更の衝突）が起きていないか

<!-- TODO: スクショ: Files changed画面 -->

---

## Merge（完成版の置き場に合体）は確認してから押す

Merge（完成版の置き場に合体）は、Pull Request / PR（合体前の確認依頼）の内容をmain（完成版の置き場）へ入れる操作。

- 変更内容をチームで見る
- build（完成品として作れるか確認）が通っているか見る
- 問題がなければMerge（完成版の置き場に合体）する

**main（完成版の置き場）は発表に使う大事な場所。慎重に守る。**

---

<style scoped>
h1 {
    text-align: center;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
h2 {
    text-align: left;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
</style>

# Vue.jsで最初の画面を作る

---

## 技術スタック（使う道具の組み合わせ）を決める

技術スタック（使う道具の組み合わせ）は、アプリを作るために使う道具セット。

- Vue.js（画面を作る道具）
- TypeScript（ミスに気づきやすいJavaScript）
- Firebase（ログインやデータ保存を助けるサービス）
- Vercel（Webアプリを公開するサービス）

迷ったら、まずはこの組み合わせでよい。

---

## Vue.js（画面を作る道具）のプロジェクトを作る

Codespaces（ブラウザで開く開発用PC）のTerminal（文字で操作する場所）で実行する。

```bash
mkdir frontend
cd frontend
npm create vue@latest .
npm install
npm run dev
```

- npm（JavaScriptの道具箱を管理するコマンド）を使う
- `npm run dev` は開発用の画面を起動するコマンド

<!-- TODO: スクショ: Terminalでコマンドを実行する画面 -->

---

## 最初は見る場所を絞る

Vue.js（画面を作る道具）のファイルは多いので、最初はここだけ見る。

- `src/views`：ページ全体を置く場所
- `src/components`：画面の部品を置く場所
- `App.vue`：アプリ全体の土台
- `main.ts`：アプリを起動する場所

<!-- TODO: スクショ: VS Codeのファイルツリー -->

---

## build（完成品として作れるか確認）を通す

build（完成品として作れるか確認）は、発表や公開に向けてアプリが正しく作れるか確認する操作。

```bash
npm run build
```

- エラーが出たら、まずエラー文を読む
- AI（相談役の自動補助ツール）に聞くときはエラー文も貼る
- build（完成品として作れるか確認）が通ってからPull Request / PR（合体前の確認依頼）を出す

<!-- TODO: スクショ: build成功画面 -->

---

<style scoped>
h1 {
    text-align: center;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
h2 {
    text-align: left;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
</style>

# AIに手伝ってもらう

---

## AI（相談役の自動補助ツール）には、いきなり全部作らせない

AI（相談役の自動補助ツール）には、まず計画を出してもらう。

- MVP（最小限だけど価値が伝わる形）を伝える
- 変更するファイルを提案してもらう
- 先に手順を説明してもらう
- build（完成品として作れるか確認）が通るように依頼する

---

## AI（相談役の自動補助ツール）への依頼文には目的・制約・確認方法を書く

```text
Week2で作るMVP（最小限だけど価値が伝わる形）は
「授業一覧 → 授業詳細 → コメント表示」です。

お願い：
1. まず既存ファイル構成を確認してください。
2. すぐ実装せず、変更するファイルと手順を提案してください。
3. 初心者にもわかる説明でお願いします。
4. 最後に npm run build が通るようにしてください。
```

<!-- TODO: スクショ: AIへの依頼画面 -->

---

## AI（相談役の自動補助ツール）が作った変更も人間が確認する

- Files changed（変更差分の確認画面）を見る
- 変なファイルが増えていないか確認する
- 目的と違う実装をしていないか確認する
- build（完成品として作れるか確認）を実行する

AI（相談役の自動補助ツール）は便利だが、最後に判断するのは人間。

---

<style scoped>
h1 {
    text-align: center;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
h2 {
    text-align: left;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
</style>

# よくある詰まりポイント

---

## 詰まったら情報をそろえて相談する

相談するときは、次の3つを出す。

1. 何をしようとしたか
2. どんなエラーが出たか
3. 画面のスクショ

- Codespaces（ブラウザで開く開発用PC）の画面
- Terminal（文字で操作する場所）のエラー文
- GitHub（ネット上のコード置き場）のPull Request / PR（合体前の確認依頼）画面

---

## Conflict（変更の衝突）は失敗ではない

Conflict（変更の衝突）は、同じ場所を複数人が変えたため、Git（変更履歴を残す道具）が自動で決められない状態。

- 「どちらを残すか」を人間が選ぶ
- 早めにチームへ共有する
- 大きすぎるPull Request / PR（合体前の確認依頼）を避けると起きにくい

---

## 1回のPull Request / PR（合体前の確認依頼）は小さくする

大きすぎるPull Request / PR（合体前の確認依頼）は確認しづらい。

- 1画面だけ
- 1機能だけ
- 1つの修正だけ

**「何を変えたか説明できる大きさ」にする。**

---

<style scoped>
h1 {
    text-align: center;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
h2 {
    text-align: left;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
</style>

# 最後の確認

---

## Week 2チェックリスト

- GitHub（ネット上のコード置き場）のアカウントを作った
- Repository（チームのコード箱）を作った
- Collaborator（共同編集できる人）に全員を招待した
- Codespaces（ブラウザで開く開発用PC）を開けた
- MVP（最小限だけど価値が伝わる形）を1つに絞った
- Branch（自分専用の安全な作業部屋）を作った
- Commit（変更のセーブポイント）を作った
- Push（ネット上のコード置き場へ送る）した
- Pull Request / PR（合体前の確認依頼）を作った

---

## Week 3へつなげる

Week 3では、Pull Request / PR（合体前の確認依頼）を起点にMVP（最小限だけど価値が伝わる形）を育てる。

- バグを直す
- 画面を増やす
- データをつなぐ
- 発表で見せる流れを作る

**完成度よりも、チームで安全に開発する流れを身につける。**

---

<style scoped>
h1 {
    text-align: center;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
h2 {
    text-align: left;
    margin-inline-start: 0;
    margin-top: 16.6rem
}
</style>

# 補足

---

## devcontainer（開発用PCの初期設定を自動化する仕組み）は任意

devcontainer（開発用PCの初期設定を自動化する仕組み）は、Codespaces（ブラウザで開く開発用PC）を作るときの準備を自動化する設定。

- 毎回npm install（必要な道具を入れる操作）を手動でやらなくてよくなる
- VS Code（コードを書く画面）の拡張機能も自動で入れられる
- 最初は知らなくても開発できる
- 余裕があるチームだけ使えばよい

<!-- TODO: スクショ: .devcontainer/devcontainer.jsonの例 -->

---

## 用語と言い換え一覧

| 用語              | 言い換え                     |
| ----------------- | ---------------------------- |
| Git               | 変更履歴を残す道具           |
| GitHub            | ネット上のコード置き場       |
| Repository        | チームのコード箱             |
| Codespaces        | ブラウザで開く開発用PC       |
| main              | 完成版の置き場               |
| Branch            | 自分専用の安全な作業部屋     |
| Commit            | 変更のセーブポイント         |
| Push              | ネット上のコード置き場へ送る |
| Pull Request / PR | 合体前の確認依頼             |
| Merge             | 完成版の置き場に合体         |
| Conflict          | 変更の衝突                   |
| build             | 完成品として作れるか確認     |

---

## 今日のまとめ

- Git（変更履歴を残す道具）は、チームで安全に分担するために使う
- GitHub（ネット上のコード置き場）は、チームのコードを共有する場所
- Codespaces（ブラウザで開く開発用PC）は、全員の環境をそろえる場所
- Branch（自分専用の安全な作業部屋）で作業し、Pull Request / PR（合体前の確認依頼）でmain（完成版の置き場）に入れる

**小さく作って、確認して、共有する。**
