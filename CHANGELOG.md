# 変更履歴

## 2025-07-01

* process.mac: `PRCPTR_*`を追加。
  * `BG_*`は将来削除予定。


## 4.2.0 (2025-04-23)

* graphicmask.mac: 新規作成。Graphic Maskのgm_internal.macと互換性がある。


## 4.1.0 (2025-01-20)

* macro.mac: `STRLEN_CLOB`マクロを追加。アドレスレジスタを破壊するが速い。


## 4.0.2 (2024-11-05)

* macro.mac: `STREND`、`STRLEN`マクロの`offset`引数に負数を指定するとアセンブルエラー
  になる不具合を修正。


## 4.0.1 (2024-10-12)

* macro.mac: マクロの引数に式を指定すると正しく展開されない不具合を修正。
  * `STRCPY`、`STRCAT`マクロの`rewind`引数
  * `STREND`、`STRLEN`マクロの`offset`引数


## 4.0.0 (2024-10-06)

* dosdef.mac, filesys.mac: 削除予定の機能はシンボル`__RUKA_ENABLE_OBSOLETE_MACRO__`を
  定義したときのみ有効となるようにした。
* fdef.mac: 新規作成。X-BASIC外部関数の定義。
* macro.mac: `STRLEN`マクロに第三引数`offset`(長さの補正、-7～+9)を追加。


## 3.3.0 (2024-07-31)

* devdrv.mac: `REQHEAD_ReadData`、`DPBv1_*`、`CURDIR_*`、`MEDIABYTE_*`、`DIRENT_*`を追加。
* dosdef.mac: `MB_*`は将来削除する可能性あり。
* filesys.mac: `FILES_EX_*`を追加。
  * `FILES_Path`は将来削除する可能性あり。


## 3.2.2 (2024-02-08)

* doscall.mac: `_SUSPEND`ではなく`_SUSPEND_PR`が正式なシンボル名と解釈し、これを先頭に戻した。


## 3.2.1 (2024-02-07)

* doscall.mac: 複数の名称を定義している下記DOSコールについて、XCの名称を先頭に移動。  
  機能に変更はないが、disで使用する場合はソースコードに出力されるDOSコール名が変更される。
  * `_PSPSET` `(_V2)_SETPDB` `(_V2)_GETPDB` `(_V2)_GET_FCB_ADR` `_SUSPEND`


## 3.2.0 (2023-12-04)

* filesys.mac: `ASSIGNMD_*`を追加。
* dosdef.mac: `EXECFILETYPE_*`、`EXECMODE_*`を追加。
  * `EXEC_*`は将来削除する可能性あり。


## 3.1.0 (2023-11-26)

* `#`コメントを`;`に変更。
* filesys.mac: `sizeof_NAMESTS_*`、`sizeof_NAMECK_*`を追加。


## 3.0.0 (2023-09-20)

新機能
* filesys.mac: 新規作成。ドライブ、ファイル関係の定義。
* process.mac: 新規作成。メモリブロック、プロセス関係の定義。
* macro.mac: `STREND`マクロに第二引数`offset`(NUL文字からの相対位置=-7～+9)を追加。
  ```
    STREND a0,-1  ;NULの前のアドレスを指す。
    STREND a0,0   ;NULを指す。offset省略時と同じ。
    STREND a0,+1  ;NULの次のアドレスを指す。offsetを指定する場合の主な用途。
  ```
* sram.mac: `SRAM_16KB_END`、`SRAM_32KB_END`、`SRAM_64KB_END`を追加。

不具合の修正
* iocsdef.mac, scsicall.mac, scsidef.mac: マクロファイルの内容がリストファイルに
  出力されてしまう(`.list`状態になる)不具合を修正。

その他
* 各ファイルにバージョン番号ではなく最終更新日を書くようにした。
* dosdef.mac 内のドライブ、ファイル関係の定義は将来削除するかも。

