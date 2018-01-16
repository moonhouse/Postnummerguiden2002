# Postnummerguiden2002
Genomgång av dataformat för Postens "Postnummerguiden" från 2002. Programmet installerades från filen pguide.exe (för Windows) som fanns att ladda ned från Postens webbplats under 2002. Programmet fanns även för Macintosh (pre-MacOS X) under namnet pguide.mac.bin.

## Filer som installeras

MD5-summor inom parentes.

### Huvudkatalog

 * INSTALL.LOG 
 * Pong2002.exe (f5124fb8a78fe743d4b78360d234ec56)
 * UNWISE.EXE (2b85fe26ca828485bff6a454b881a295)
 * UNWISE.INI (d0b1f44b0c716b010b80cc7edf61b4d0)
 * Working.avi (6a7ec6fcbc08d41c6c7b6e52be4beaa5)
 * help.htm (9737e4f607693d58f4668866488402ff)
 * mmdbi.dll (261e2ac739c3143907525cbc4eb2e57b)

### Datakatalog

 * pong1.dat (15de46b39ef1bdd6a399975a5422e7a2)
 * pong2.dat (11ce60310e4c6233d65698eaca680a2b)
 * pong3.dat (37b82be60a2d398a7b9f863721e6266f)
 * pong4.dat (9620091f1e3bd198b683a98ad869d87c)
 * pong5.dat (c4b97b5250fbf809be86be21bb12f82c)
 * pong6.dat (909374a3fc8cf7ccb4c8449fe9748f56)
 * pong7.dat (f21eaed3dafccb56d827a4b3f4a9c838)
 * pong8.dat (26df4d8b9e19639c84dc4bd2f0f1cd97)
 * pong9.dat (751589e36b8d1a7de7753003567ea0bd)
 * Tips.BLB (d0a83f77ad43be962e73a3dca0691d17)
 * Tips.DAT (cec3dfdd42e1cfdbb2b7046dec58ec68)
 * Tips.IDX (1496c82db7d5ab23a8cdbd8554dbc61d)

## Genomgång datafiler

pong = *Po*st*n*ummer*g*uiden. 

### pong1.dat

###  pong2.dat    

`LC_ALL=C strings pong2.dat | LC_ALL=C sort | LC_ALL=C uniq`

@AADK\
@AAORRTR]S
@AISK
@CDLS
@GNDSADR
@GUNN@RY
@L@FOR
@LFT

Inte så där jättetydligt. ABBORRTRÄS(K) på rad 2? AGUNNARY(D) på rad 6?

K@RLSH@M
K@RLSKOG
K@RLSKRON
K@RLST@
K@RUNG
K@TRINDHOL

= Karlshamn, Karlskoga, Karlskrona, Karlstad, Kar?, Katrineholm. Sista tecknet saknas genomgående. A (DEC 65) är ersatt med @ (DEC 64). E (DEC 69) är ersatt med D (DEC 68). G (DEC 72) ser ut att fortfarande vara G.

###  pong3.dat

`LC_ALL=C strings pong2.dat | LC_ALL=C sort | LC_ALL=C uniq`

10:D KOLONISTIGDN
11:D KOLONISTIGDN
1:@ GULCV]GDN
1:@ INCUSTRIG@T@N
1:@ KOLONISTIGDN
1:@ R@CHUSG@T@N
1:@ R@CHUSV]GDN
1:@ RINGV]GDN

Ser ut att vara samma märkliga teckenuppsättning som för pong2. Till skillnad mot i pong2 så ser sista tecknet i respektive sträng ut att vara intakt. 

###  pong4.dat  
###  pong5.dat
###  pong6.dat 
###  pong7.dat
###  pong8.dat

Sträng:

01200301012001010 ... 1466143614661836146603

Totalt 8190 tecken.

###  pong9.dat    

Strängar:

                        34001      34249      49001      49129      49130      49311      21001      21200      26220      26299      26000      26219      29001      29199      29301      29310      39001      39065      39101      39139      10001      10350      11001      11556      38001      38410      44001      44108      43001      43250      47001      47399          1         50         51        100        101        150        151        200        201        250        251        300        301        350        351        400        401        450        451        500        501        550        551        600        601        659        701        716        717        732        733        752        800        849        850        899       1000       1049       1050       1099      55501      55580      55601      55650      12001      12040      12041      12080      12081      12120      12121      12170      12171      12220      12221      12270      12271      12300      12301      12330      12500      12599       6001       6072       6073       6126       6127       6200       6201       6300       6306       6369       6901       6928       5851       5900       5001       5050       5051       5100       5101       5150       5151       5200       5
                   
                        ...
                        
                         16         20         17         35         30         58         31         63         67         67         76         76          1        999       1100       1159       1200       1260       1300       1363       1400       1441       1500       1559       1600       1659       1700       1779       1801       1850       1901       1950       1160       1199       1261       1299       1364       1399       1442       1499       1560       1599       1660       1699       1780       1799       1851       1899       1951       1999          2         58          1         49          2         48          1         21          2         22          2         36          1         37         11         33         35         55         69      99999         78      99998          1         51          2         54         17         45         38         42         24      99998         25      99999          7      99999         10      99998         30         40         33         45         23         31         24         28         56         60         19      99999         44      99998         47      99999         50         74         51         65         22         34         39         65         36         52         67         83          2         24          1         25          6      99998         17      99999        101        119         57         99        121        133         62         66         32         62         37         63         60         80         63         63         82        102         13         39         14         30         32         38         41         49         69         77         76         90         79         87          2          4         53         79         68         84         20         30          1         39          2         92          1         99          2         88         54         72         85      99999         81        141         86        130         41      99999         50      99998        135        185         90      99998        101      99999        132      99998        143      99999         31      99999         36      99998         42      99998         37      99999         38      99998          1          1         26         40          1         29         22        120       1000       1999      12600      12649      12650      12699      12700      12749      12770      12799      12800      12849      12850      12899         66         78         64         64          2         16         18         22         22         32         54
