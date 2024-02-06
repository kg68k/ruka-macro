# 変更履歴

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

