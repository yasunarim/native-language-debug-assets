# 日本語でデバッグ for Python

Pythonコードを **日本語で理解しながらデバッグできる VSCode 拡張機能**。  
AIが生成したコードの理解とデバッグにも役立ちます。

Pythonコードを日本語に変換して表示し、  
コードの意味を自然言語で読みながらデバッグできるようにします。

---

⚠ この拡張は現在MVP（初期バージョン）です。  
不具合や改善提案があれば Issue で教えていただけると嬉しいです。

[公開用のGithubのIssue](https://github.com/yasunarim/native-language-debug-assets/issues)

---

![デバッグ実行](https://yasunarim.github.io/native-language-debug-assets/movie003.gif)

---

## 概要

AIが生成したコードや、複雑なPythonコードを読むときに、

- 「このコードは何をしているのか？」
- 「この行は何の処理なのか？」

と理解に時間がかかることがあります。

この拡張は、Pythonコードを日本語に変換して表示し、  
さらに **行ごとの説明をAIが生成**することで、コードの理解を助けます。

Pythonのデバッグ実行と連携して、  
**現在実行されている行を日本語コード側でもハイライト表示**します。

---

# 主な機能

## 1. Pythonコードを日本語で表示

Pythonコードを解析し、日本語の自然な文章に変換して表示します。

Pythonの構文は **AST解析を利用して変換**されます。 

---

## 2. 日本語コードペイン（Twin Panel）

Pythonコードの横に、日本語コードを表示する専用ペインを開きます。

![日本語表示](https://yasunarim.github.io/native-language-debug-assets/movie001.gif)

コードを編集すると、日本語コードも自動更新されます。

---

## 3. 行クリックでコードの説明を表示

日本語コードの行をクリックすると、
AIがその行の処理を日本語で説明します。

![日本語説明](https://yasunarim.github.io/native-language-debug-assets/movie002.gif)

説明は **LLMを利用して生成されます。** 

対応プロバイダ

* GitHub Copilot
* OpenAI
* Anthropic Claude

---

## 4. Pythonデバッグと連携

VSCodeのデバッグ実行と連携し、
現在実行中のコード行を日本語ペインでもハイライトします。

![デバッグ実行](https://yasunarim.github.io/native-language-debug-assets/movie003.gif)

これにより

* 実行フローの理解
* ステップ実行の追跡

が分かりやすくなります。 

---

## 5. 変数名・関数名の日本語化

コード内の識別子（変数名、関数名、クラス名）を解析し、
日本語の名前に翻訳できます。

翻訳結果は

.vscode/native-debugger-rename-map.json

に保存されます。 

---

## 6. AIモデルの選択

使用するAIモデルを選択できます。

対応プロバイダ

* GitHub Copilot
* OpenAI
* Anthropic Claude

ステータスバーのアイコンから変更できます。

---

# 使い方

## 0. モデルの設定

日本語化にはLLMを利用します。利用するサービスは以下です。

* GitHub Copilot
* OpenAI
* Anthropic Claude

コマンドパレットの

`Native Language Debug:使用モデルを選択`

または、または右下のステータスバーの虫アイコンから

`モデル／プロバイダを選択`

を選択します。

### GitHub Copilot

Github Copilot　を選択するとモデルの一覧が表示されるので、

利用するモデルを選択します。

* Github Copilot 拡張機能のインストールが必要です。
* Github Copilot のプランによって使えるモデルや回数などが異なります。

### OpenAI

OpenAIを選択して利用するには、OpenAIのAPIキーの設定が必要です。

APIキーの選択は、コマンドパレットの

`Native Language Debug: API キーを設定`

または、または右下のステータスバーの虫アイコンから

`APIキーを設定`

を選びます。設定するAPIキーは、事前にOpenAIに契約してAPIキーを取得してください。
OpenAIを選択すると利用可能なモデルのリストが表示されるので、
利用するモデルを選択します。

### Anthropic Claude

Anthropic Claudeを選択して利用するには、Anthropic ClaudeのAPIキーの設定が必要です。

APIキーの選択は、コマンドパレットの

`Native Language Debug: API キーを設定`

または、または右下のステータスバーの虫アイコンから

`APIキーを設定`

を選びます。設定するAPIキーは、事前にAntropicに契約してAPIキーを取得してください。
Claudeを選択すると利用可能なモデルのリストが表示されるので、
利用するモデルを選択します。

---

## 1. Pythonファイルを開く

`.py` ファイルを開きます。

---

## 2. 日本語ペインを開く

Pythonファイルを開くと、日本語コードが表示されます。

機能を一時的にオフにするには、コマンドパレットの

`Native Language Debug: メニュー`

または、または右下のステータスバーの虫アイコンから

`日本語でデバッグ をオフにする`

を選びます。

日本語ペインを閉じるには、日本語でデバッグタブのバツボタンをクリックします。

サイド表示するには、コマンドパレットの

`Native Language Debug: 日本語ペインを開く`

または、または右下のステータスバーの虫アイコンから

`日本語ペインを開く`

を選びます。

---

## 3. 日本語コードを確認

Pythonコードが日本語で表示されます。

コードを編集すると自動更新されます。

---

## 4. 行をクリックして説明を見る

日本語コードの行をクリックすると
AIによるコード説明が表示されます。

---

## 5. デバッグ実行

通常どおり VSCode のデバッグを実行します。

現在実行中の行が、日本語コード側でもハイライトされます。

---

# 設定

## Python 実行環境

実行にはPythonが必要です。

Pythonの実行パスは次の優先順で検出されます。

1. この拡張機能の設定 `Native Language Debug: Python Path`
2. VSCode Python拡張機能のインタープリタ
3. PATH の python3 / python

Python拡張機能をインストールしておらず、PATHにもPythonのパス指定がない場合は、

設定から`Native Language Debug: Python Path`を設定してください。

---

## APIキー

OpenAI / Claude を使用する場合は
APIキーを設定してください。

コマンド
`Native Language Debug: API キーを設定`

または、または右下のステータスバーの虫アイコンから

`APIキーを設定`

を選びます。

APIキーは **SecretStorage に安全に保存**されます。

---

# 対応言語

現在

* Python

に対応しています。

今後

* JavaScript
* TypeScript
* 他の言語

への対応も予定しています。

---

# 対象ユーザー

この拡張は特に次のような人に役立ちます。

* Python初心者
* AI生成コードを読む人
* コードレビューをする人
* プログラミング学習者

---

# ライセンス

Apache 2.0

---

## 料金について

現在、この拡張のすべての機能は無料で利用できます。

多くのユーザーに試してもらうため、当面は無料で提供しています。

※ 将来的に、一部のAI機能に使用回数制限や有料プランが導入される可能性があります。
