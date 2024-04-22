# Publisher App

## Reflection
> How many data will the publisher program send to the message broker in one run?

Program *publisher* ini akan mengirimkan 5 buah data ke *message broker* dalam satu kali jalan. Hal ini dapat dilihat dari pemanggilan fungsi `publish_event` yang dipanggil sebanyak 5 kali di fungsi `main` pada `main.rs`. 

> The url of "amqp://guest:guest@localhost:5672" is the same as the one in the subscriber program. What does it mean?

Uri yang digunakan pada program *publisher* sama dengan uri yang digunakan dengan program *subscriber* mengartikan bahwa *publisher* akan mem-*publish* *message* nya ke sesi `amqp` yang sama dengan *subscriber*. Hal ini berarti *subscriber* akan dapat melihat *message* yang di-*publish* oleh *publisher*. Jika uri nya tidak sama, *subscriber* tidak akan menerima message dari *publisher* karena *subscriber* meng-*observe* sesi yang berbeda dengan sesi dimana *publisher* mem-*publish* *message-message* nya.
