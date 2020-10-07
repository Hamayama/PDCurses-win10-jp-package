# PDCurses-win10-jp-package


## 概要
- PDCurses-win10-jp ( https://github.com/Hamayama/PDCurses-win10-jp ) の  
  MSYS2/MinGW-w64 (64bit/32bit) 用のパッケージファイルを、  
  管理するリポジトリです。

- ( PDCurses-win10-jp は、PDCurses の Windows Console 用ポート (wincon) を、  
  Windows 10 上での日本語表示が改善するように、改造したものです)


## インストール方法
- MSYS2/MinGW-w64 (64bit/32bit) 環境での、本パッケージのインストール手順を、  
  以下に示します。

1. MSYS2/MinGW-w64 (64bit) のインストール  
   事前に MSYS2/MinGW-w64 (64bit) がインストールされている必要があります。  
   以下のページを参考に、開発環境のインストールを実施ください。  
   https://gist.github.com/Hamayama/eb4b4824ada3ac71beee0c9bb5fa546d  
   (すでにインストール済みであれば本手順は不要です)

2. パッケージファイルのダウンロード  
   以下のリリースページから、環境に応じたパッケージファイルをダウンロードして、  
   適当な作業用フォルダに置いてください。  
   (作業用フォルダのパスには、空白を入れないようにしてください)  
   
   https://github.com/Hamayama/PDCurses-win10-jp-package/releases  
   
   ( i686 は 32bit 環境用で、x86_64 は 64bit 環境用になります。  
   また、win8 は Windows 8.1 以前用で、win10 は Windows 10 用になります)

3. パッケージファイルのインストール  
   ダウンロードしたパッケージファイルを、開発環境にインストールします。  
   
   ＜Windows 10 で、MSYS2/MinGW-w64 (64bit) 環境の場合＞  
   プログラムメニューから MSYS2 の MinGW 64bit Shell を起動して、以下のコマンドを実行してください。  
   ( c:\work にパッケージファイルを置いた場合)
   ```
   cd /c/work
   pacman -U mingw-w64-x86_64-pdcurses-win10-jp-3.9-2-any.pkg.tar.xz
   ```
   ＜Windows 10 で、MSYS2/MinGW-w64 (32bit) 環境の場合＞  
   プログラムメニューから MSYS2 の MinGW 32bit Shell を起動して、以下のコマンドを実行してください。  
   ( c:\work にパッケージファイルを置いた場合)
   ```
   cd /c/work
   pacman -U mingw-w64-i686-pdcurses-win10-jp-3.9-2-any.pkg.tar.xz
   ```
   ＜Windows 8.1 以前で、MSYS2/MinGW-w64 (64bit) 環境の場合＞  
   プログラムメニューから MSYS2 の MinGW 64bit Shell を起動して、以下のコマンドを実行してください。  
   ( c:\work にパッケージファイルを置いた場合)
   ```
   cd /c/work
   pacman -U mingw-w64-x86_64-pdcurses-win8-jp-3.9-2-any.pkg.tar.xz
   ```
   ＜Windows 8.1 以前で、MSYS2/MinGW-w64 (32bit) 環境の場合＞  
   プログラムメニューから MSYS2 の MinGW 32bit Shell を起動して、以下のコマンドを実行してください。  
   ( c:\work にパッケージファイルを置いた場合)
   ```
   cd /c/work
   pacman -U mingw-w64-i686-pdcurses-win8-jp-3.9-2-any.pkg.tar.xz
   ```

4. その他  
   もし、Lem エディタ ( https://github.com/cxxxr/lem ) のライブラリとして使用する場合には、  
   以下のコマンドを追加で実行してください。  
   (この名前のヘッダーファイルしか認識しないため)  
   
   ＜MSYS2/MinGW-w64 (64bit) 環境の場合＞  
   プログラムメニューから MSYS2 の MinGW 64bit Shell を起動して、以下のコマンドを実行してください。
   ```
   cp -i /mingw64/include/pdcurses.h /mingw64/include/ncurses.h
   ```
   ＜MSYS2/MinGW-w64 (32bit) 環境の場合＞  
   プログラムメニューから MSYS2 の MinGW 32bit Shell を起動して、以下のコマンドを実行してください。
   ```
   cp -i /mingw32/include/pdcurses.h /mingw32/include/ncurses.h
   ```

- 以上です。


## 保守用メモ
1. プログラムメニューから MSYS2 の MinGW 64bit Shell を起動して、  
   以下のコマンドを実行すると、パッケージファイルが生成される。
   ```
   cd /c/work/PDCurses-win10-jp-package
   makepkg-mingw
   makepkg-mingw -p PKGBUILD_win8
   ```
   その後、GitHub の Release ページでリリースを作成して、  
   パッケージファイルをアップロードする。


## 環境等
- OS
  - Windows 10 (version 1909) (64bit)
  - Windows 8.1 (64bit)
- 環境
  - MSYS2/MinGW-w64 (64bit) (gcc version 10.2.0 (Rev1, Built by MSYS2 project)) (Windows 10)
  - MSYS2/MinGW-w64 (64bit) (gcc version 9.2.0 (Rev2, Built by MSYS2 project)) (Windows 8.1)

## 履歴
- 2020-10-7  PDCurses-win10-jp v3.9-jp0002 のパッケージファイルを作成


(2020-10-7)
