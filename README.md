# RUKA assembler macro for X680x0/Human68k

HAS060 用各種マクロファイルです。
ファイルによっては自分があまり使わないため、バグがあるかも知れません。


## Build
PC やネット上で扱いやすくするために、ソースファイルは UTF-8 で記述されています。
X68000 上で使用する際には、UTF-8 から Shift_JIS への変換が必要です。

### u8tosj を使用する方法

あらかじめ、[u8tosj](https://github.com/kg68k/u8tosj) をビルドしてインストールしておいてください。

トップディレクトリで make を実行してください。以下の処理が行われます。
1. build ディレクトリの作成。
2. src/ 内の各ファイルを Shift_JIS に変換して build/ へ保存。

build/ 内の各ファイルを、インクルードファイル用のディレクトリにコピーしてください。


### u8tosj を使用しない方法

ファイルを適当なツールで Shift_JIS に変換してください。


## License

all-permissive license

Copying and distribution of this file, with or without modification,
are permitted in any medium without royalty provided the copyright
notice and this notice are preserved.  This file is offered as-is,
without any warranty.


## Author
TcbnErik / https://github.com/kg68k/ruka-macro
