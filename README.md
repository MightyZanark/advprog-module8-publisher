# Publisher App

## Reflection
> How many data will the publisher program send to the message broker in one run?

Program *publisher* ini akan mengirimkan 5 buah data ke *message broker* dalam satu kali jalan. Hal ini dapat dilihat dari pemanggilan fungsi `publish_event` yang dipanggil sebanyak 5 kali di fungsi `main` pada `main.rs`. 

> The url of "amqp://guest:guest@localhost:5672" is the same as the one in the subscriber program. What does it mean?

Uri yang digunakan pada program *publisher* sama dengan uri yang digunakan dengan program *subscriber* mengartikan bahwa *publisher* akan mem-*publish* *message* nya ke sesi `amqp` yang sama dengan *subscriber*. Hal ini berarti *subscriber* akan dapat melihat *message* yang di-*publish* oleh *publisher*. Jika uri nya tidak sama, *subscriber* tidak akan menerima message dari *publisher* karena *subscriber* meng-*observe* sesi yang berbeda dengan sesi dimana *publisher* mem-*publish* *message-message* nya.

## Images
Gambar yang memperlihatkan `rabbitmq` berjalan di mesin saya
![Gambar servis rabbitmq di localhost:15672 mesin saya](./rabbitmq_run.png)


Gambar yang memperlihatkan setelah program `publisher` di jalankan, program `subcsriber` mendapatkan pesan yang dikirim. Pada gambar ini, program `publisher` dijalankan 2 kali, sehingga program `subscriber` menerima total 10 *event*.
![Gambar publisher mengirimkan event dan subscriber menerimanya](./publisher_send_event.png)


Gambar yang memperlihatkan *chart* pada `rabbitmq` yang memiliki beberapa *spike* berbanding lurus dengan waktu dimana saya menjalankan program `publisher` beberapa kali di terminal. Ini berarti *spike* yang terdapat merupakan hasil mem-*publish* *event* dari `publisher`.
![Gambar spike pada chart yang sejalan dengan waktu dijalankan program publisher](./publisher_chart_spike.png)
