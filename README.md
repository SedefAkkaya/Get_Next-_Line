# get_next_line


AMAÇ
~~~
Dosyanın içindekileri, satır sartır argüman olarak başka bir dosyaya yazdırmak.
~~~
******

static char                 --> bu değeri alan değişken, fonksiyon a değeri ile bitip tekrar başladığı zaman; ilk değerinden değil,
                            2. değerinden yani a değerinden devam eder.


BUFFER_SIZE                 --> Satırları kaçarlı kaçarlı okuyacağını belirliyorsun.


read(fd, buff, BUFFER_SIZE) --> read; fd'nin içindeki BUFFER_SIZZE kadar karakteri, buff'a okur.
read, aslında her defasında fd'yi en baştan okumaya başlar. Ama mesela ilk BUFFER_SIZE kadar okuduğu yeri,
bir sonraki okuyuşunda saymaz. Sonrakinde, bir sonraki BUFFER_SIZE'ı alır.


Bilgi: 
~~~
fd --> file description 
* fd < 0 ise dosya okunmadığı anlamına geliyor.
* fd = 0 ise standart giriş -> kalvye girişi.
* fd = 0 ise standart çıktı -> metni yazdırdığı anlamına geliyor.
* fd = 2 ise standart hata  -> hata çıkma durumu.
~~~

*****************
INT MAIN

open("txt", O_RDONLY) --> txt dosyasını açıp O_RDONLY komutu ile okur.
                          open int değer döndürür. Yani file descriptionlardan bir değer döndürür.

~~~~~~~~~~~~~~~~~~~~~~
O_RDONLY --> read only

O_WRONLY --> write only

O_RDWR   --> read and write
~~~~~~~~~~~~~~~~~~~~~~

Bunları kütüphanede makrolar olarak ekliyebilirsin:
~~~
#define O_READONLY  00

#define O_WRONLY    01

#define O_RDWR      02
~~~


***
Olayı da açıklamak isterdim fakat 42 mantığına aykırı.

Arkadaşlarınıza sorabilirsiniz ^^
***
