# マシンの環境構築

前提：

* OS: macOS Big Sur (11.2.3)：2021-03-09 時点最新
* シェルの種類：zsh
* VS Code はインストール済み

## 0. 参考

* [YouTube KBOYのFlutter大学](https://www.youtube.com/watch?v=kpvVENfDCRc)

## 1. インストールするツール

* Xcode
* VS Code

## 2. Python の環境構築

あとで書く。

## 3. Flutter の環境構築

## 3.1 概要

* Flutter のインストール
* Flutter のパスを通す
* Android Studio のインストール
* Andorid エミュレータのインストール
* Xcode のインストール
* iOS シミュレータのインストール
* VS Code の Flutter の拡張機能をインストール
* `flutter doctor -v` で確認する

### 3.2 Flutter のインストール

[flutter.dev の macOS 用インストールページ](https://flutter.dev/docs/get-started/install/macos)へアクセスし、Flutter SDK の zip ファイル（2021-03-09 時点：`flutter_macos_2.0.1-stable.zip`）をダウンロードする。

マシンの所望のディレクトリ（`~/dev` とする）で展開する。

```sh
cd ~/dev
unzip ~/Downloads/flutter_macos_2.0.1-stable.zip
```

### 3.3 パスを通す

Flutter のパスを通すために、`dev` ディレクトリで下記のコマンドを実行する（または、`~/.zshrc` に記載して、`resource ~/.zshrc` コマンドを実行する）。

```sh
export PATH="$PATH:`pwd`/flutter/bin"
```

下記コマンドで Flutter の場所が帰ってくれば OK。

```sh
which flutter
```

この時点で

```sh
which dart
```

で、flutter ディレクトリとセットで dart も使用可能になっていることがわかる。

### 3.4 Android Studio のインストール

[developer.android.com のインストールページ](https://developer.android.com/studio)へアクセスし、Android Studio をダウンロードする（2021-03-09 時点：`4.1.2 for Mac`）する。

その後、`Applications` ディレクトリに移動させ、Android Studio を起動し、ガイドに沿ってインストールの操作を進める。一連の操作の後、Android Studio を再起動し、"Configure > Preferences" から Flutter のプラグイン（と Dart のプラグイン）をインストールする。

ターミナルで

```sh
flutter doctor --android-licenses
```

を実行し、アンドロイドライセンスに同意する。

### 3.6 Xcode のインストール

AppStore から Xcode を開き、ライセンスに同意する。

ターミナルで下記コマンドを実行し、CocoaPods をインストールする。

```sh
sudo gem install cocoapods
```

### 3.7 iOS シミュレータのインストール

あとで書く。

### 3.8 VS Code の Flutter の拡張機能をインストールする

VS Code の Flutter の拡張機能をインストールする。一緒に Dart の拡張機能もインストールされていることを確認する。

ついでに `command + ,` の設定画面から "format" で検索し、"Editor: Format On Save" にチェックを付けておく。

### 3.9 `flutter doctor -v` で確認する

最後に

```sh
flutter doctor -v
```

で確認する。
