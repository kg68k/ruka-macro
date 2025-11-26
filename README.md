# RUKA assembler macro for X680x0/Human68k

HAS060.X用マクロファイル集です。  

* 無保証です。
* ファイルによっては自分があまり使わないため、不具合があるかも知れません。
* しばしば仕様の変更が行われます。


## ファイル内容

* console.mac ... 制御文字
* devdrv.mac ... デバイスドライバ
* doscall.mac ... DOSコールマクロとDOSコール番号
* dosdef.mac ... DOSコールの各種定義
* fdef.mac ... X-BASICの外部関数
* fefunc.mac ... FLOAT\*.X (FPACKマクロとFEFUNCコール番号)
* filesys.mac ... ファイル操作DOSコールの各種定義
* graphicmask.mac ... Graphic Mask
* iocscall.mac ... IOCSコールマクロとIOCSコール番号
* iocsdef.mac ... IOCSコールの各種定義
* iocswork.mac ... IOCSワーク
* iomap.mac ... メモリマップトI/O
* keycode.mac ... IOCSのキースキャンコード
* macro.mac ... 各種マクロ
* opmdrv.mac ... OPMDRV\*.X (OPMマクロとOPMコール番号)
* opmdrvdef.mac ... OPMコールの各種定義
* process.mac ... プロセス操作DOSコールの各種定義
* rsdrv.mac ... RSDRV.SYS (ERSマクロとERSコール番号)
* scsicall.mac ... SCSI IOCSコール (SCSIマクロとSCSIコール番号)
* scsidef.mac ... SCSI IOCSコールの各種定義
* sram.mac ... SRAMメモリスイッチ
* sxcall.mac ... SX-Window (SXマクロとSXコール番号)
* vector.mac ... 例外ベクタ番号


## Build

PCやネット上での取り扱いを用意にするために、src/内のファイルはUTF-8で記述されています。
X68000上で使用する際には、UTF-8からShift_JISへの変換が必要です。

### src2buildを使用する場合

必要ツール: [src2build](https://github.com/kg68k/src2build)

srcディレクトリのある場所で以下のコマンドを実行します。
```
src2build src
```

### u8tosj を使用する方法

必要ツール: [u8tosj](https://github.com/kg68k/u8tosj)

srcディレクトリのある場所で以下のコマンドを実行します。
```
make
```

build/内の各ファイルを、インクルードファイル用のディレクトリにコピーしてください。

### その他の方法

src/内のファイルを適当なツールで適宜Shift_JISに変換してください。


## License

all-permissive license

Copying and distribution of this file, with or without modification,
are permitted in any medium without royalty provided the copyright
notice and this notice are preserved.  This file is offered as-is,
without any warranty.


## Author

TcbnErik / https://github.com/kg68k/ruka-macro
