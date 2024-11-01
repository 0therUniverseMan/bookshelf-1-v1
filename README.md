# API Buku

API Buku adalah sebuah RESTful API yang memungkinkan pengguna untuk mengelola koleksi buku. Pengguna dapat menambahkan, menampilkan, memperbarui, dan menghapus buku dari koleksi.

## Fitur

- Menambahkan buku baru
- Menampilkan seluruh buku
- Menampilkan detail buku berdasarkan ID
- Memperbarui data buku berdasarkan ID
- Menghapus buku berdasarkan ID

## Teknologi yang Digunakan

- Node.js
- Express.js
- nanoid (untuk menghasilkan ID unik)

## Prerequisites

Sebelum memulai, pastikan Anda telah menginstal [Node.js](https://nodejs.org/) di sistem Anda.

## Instalasi

1. Clone repositori ini:

   ```bash
   git clone https://github.com/username/repo-name.git
   ```

   Masuk ke direktori proyek:

Masuk ke direktori proyek
Instal dependensi
Jalankan server

```
cd repo-name
npm install
npm start
```

Server akan berjalan di http://localhost:9000.

## Endpoint API

1. Menambahkan Buku
   Method: POST

URL: /books

Body Request:

```
{
    "name": "string",
    "year": number,
    "author": "string",
    "summary": "string",
    "publisher": "string",
    "pageCount": number,
    "readPage": number,
    "reading": boolean
}
```

Response:

Status Code: 201
Body:

```
{
    "status": "success",
    "message": "Buku berhasil ditambahkan",
    "data": {
        "bookId": "string"
    }
}
```

## Menampilkan Seluruh Buku

Method: GET

URL: /books

Response:

Status Code: 200
Body:

```
{
    "status": "success",
    "data": {
        "books": [
            {
                "id": "string",
                "name": "string",
                "publisher": "string"
            }
        ]
    }
}
```

## 3. Menampilkan Detail Buku

Method: GET

URL: /books/{bookId}

Response:

Status Code: 200
Body:

```
{
    "status": "success",
    "data": {
        "book": {
            "id": "string",
            "name": "string",
            "year": number,
            "author": "string",
            "summary": "string",
            "publisher": "string",
            "pageCount": number,
            "readPage": number,
            "finished": boolean,
            "reading": boolean,
            "insertedAt": "string",
            "updatedAt": "string"
        }
    }
}
```

Status Code: 404 (jika buku tidak ditemukan)

### Body:

```
{
    "status": "fail",
    "message": "Buku tidak ditemukan"
}
```

## 4. Memperbarui Buku

Method: PUT

URL: /books/{bookId}

### Body Request:

```
{
    "name": "string",
    "year": number,
    "author": "string",
    "summary": "string",
    "publisher": "string",
    "pageCount": number,
    "readPage": number,
    "reading": boolean
}
```

### Response:

Status Code: 200

### Body:

```
{
    "status": "success",
    "message": "Buku berhasil diperbarui"
}
```

### Response:

Status Code: 404 (jika ID tidak ditemukan)

### Body:

```
{
    "status": "fail",
    "message": "Gagal memperbarui buku. Id tidak ditemukan"
}
```

## 5. Menghapus Buku

Method: DELETE

URL: /books/{bookId}

### Response:

Status Code: 200

### Body:

```
{
    "status": "fail",
    "message": "Buku gagal dihapus. Id tidak ditemukan"
}

```

## Kontribusi

Jika Anda ingin berkontribusi pada proyek ini, silakan buat pull request ke repositori ini.

## Lisensi

Proyek ini dilisensikan di bawah MIT License.
