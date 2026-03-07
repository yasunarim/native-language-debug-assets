# 日本語でデバッグ for Python

Pythonコードを **日本語で理解しながらデバッグできる VSCode 拡張機能**。  
AIが生成したコードの理解とデバッグにも役立ちます。

Pythonコードを日本語に変換して表示し、  
コードの意味を自然言語で読みながらデバッグできるようにします。

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
* Claude

ステータスバーのアイコンから変更できます。

---

# 使い方

## 1. Pythonファイルを開く

`.py` ファイルを開きます。

---

## 2. 日本語ペインを開く

コマンドパレットから

Native Language Debug: 日本語ペインを開く

またはステータスバーの虫アイコンから開きます。

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

Pythonの実行パスは次の優先順で検出されます。

1. 設定 `nativeLanguageDebug.pythonPath`
2. VSCode Python拡張のインタープリタ
3. PATH の python3 / python

---

## APIキー

OpenAI / Claude を使用する場合は
APIキーを設定してください。

コマンド
Native Language Debug: API キーを設定

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
