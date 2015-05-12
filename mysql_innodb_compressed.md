# サーバーの利用の効率を上げましょう。
- 大容量で困っている -> テーブルを圧縮する。(MySQL InnoDB ) -> すでに圧縮されている。
- もっと圧縮する。KEY_BLOCK_SIZE=8 -> KEY_BLOCK_SIZE=4
- それでも動作に問題ないのか(SELECT)
```
CREATE TABLE `xxxxxu_data_20150322_backup` (
  `xxxxx` int(11) NOT NULL DEFAULT '0',
  `xxxxx` varchar(30) NOT NULL,
  `xxxxx_url` text,
  `xxxxx_name` varchar(250) DEFAULT NULL,
  `xxxxx_code` varchar(250) NOT NULL DEFAULT '',
  `xxxxx_price` int(10) unsigned DEFAULT NULL,
  `xxxxx_type` varchar(250) NOT NULL DEFAULT '',
  `xxxxxt_flg` smallint(2) unsigned NOT NULL DEFAULT '0',
  `xxxxx_flg` smallint(2) unsigned NOT NULL DEFAULT '0',
  `xxxxx_flg` smallint(2) unsigned NOT NULL DEFAULT '0',
  `xxxxx_flg` smallint(2) DEFAULT NULL,
  `xxxxx_point` smallint(2) unsigned NOT NULL DEFAULT '0',
  `xxxxx_cnt` smallint(2) unsigned NOT NULL DEFAULT '0',
  `xxxxx` smallint(3) unsigned NOT NULL DEFAULT '0',
  `xxxxx_start` date NOT NULL,
  `xxxxx_end` date NOT NULL,
  `xxxxx_kikan` smallint(3) unsigned NOT NULL,
  `xxxxx_date` datetime NOT NULL DEFAULT '0000-00-00 00:00:00',
  `xxxxx_date` datetime DEFAULT NULL,
  `xxxxx` date NOT NULL DEFAULT '0000-00-00',
  `xxxxx` varchar(3) DEFAULT NULL,
  PRIMARY KEY (`xxxxx_seq`,`xxxxxDate`,`xxxxx_code`,`xxxxxt_cnt`,`xxxxx_type`,`xxxxx_date`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 ROW_FORMAT=COMPRESSED KEY_BLOCK_SIZE=4
```



## KEY_BLOCK_SIZE=8
```
MariaDB [compare_prices]> SELECT  concat(table_schema,'.',table_name),    concat(round(table_rows/1000000,2),'M') rows,    concat(round(data_length/(1024*1024*1024),2),'G') DATA,    concat(round(index_length/(1024*1024*1024),2),'G') idx,    concat(round((data_length+index_length)/(1024*1024*1024),2),'G') total_size,    round(index_length/data_length,2) idxfrac     FROM information_schema.TABLES   where table_name = 'xxxxxxx.xxxxxxxxxxxxxxxxxxxxx_data_20150322';
+---------------------------------------------+-------+-------+-------+------------+---------+
| concat(table_schema,'.',table_name)         | rows  | DATA  | idx   | total_size | idxfrac |
+---------------------------------------------+-------+-------+-------+------------+---------+
| xxxxxxx.xxxxxxxxxxxxxxxxxxxxx_data_20150322 | 8.93M | 1.63G | 0.00G | 1.63G      |    0.00 |
+---------------------------------------------+-------+-------+-------+------------+---------+
```


## KEY_BLOCK_SIZE=4
```
MariaDB [compare_prices]> SELECT 
    -> concat(table_schema,'.',table_name),   
    -> concat(round(table_rows/1000000,2),'M') rows,   
    -> concat(round(data_length/(1024*1024*1024),2),'G') DATA,   
    -> concat(round(index_length/(1024*1024*1024),2),'G') idx,   
    -> concat(round((data_length+index_length)/(1024*1024*1024),2),'G') total_size,   
    -> round(index_length/data_length,2) idxfrac    
    -> FROM information_schema.TABLES  
    -> where table_name = 'xxxxxxx.xxxxxxxxxxxxxxxxxxxxx_data_20150322_backup' ;
+----------------------------------------------------+-------+-------+-------+------------+---------+
| concat(table_schema,'.',table_name)                | rows  | DATA  | idx   | total_size | idxfrac |
+----------------------------------------------------+-------+-------+-------+------------+---------+
| xxxxxxx.xxxxxxxxxxxxxxxxxxxxx_data_20150322_backup | 8.20M | 0.81G | 0.00G | 0.81G      |    0.00 |
+----------------------------------------------------+-------+-------+-------+------------+---------+
```

## リンク
[InnoDBの制限とファイルフォーマットAntelopeとBarracudaの違い](http://blog.kamipo.net/entry/2014/12/05/235641)
