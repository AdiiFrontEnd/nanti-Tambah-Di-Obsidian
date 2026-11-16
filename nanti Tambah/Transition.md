Adalah Sebuah Properti Untuk Membuat Sebuah Perubahan Atau Pergerakan dari Elemen Secara Berangsur Angsur/Perlahan Lahan Sesuai Waktu Yang Ditentukan
# Cara Pakai Properti `transition`

## Bentuk Dasar

```css
transition: properti durasi timing-function delay;
```

Contoh:

```css
transition: background 0.5s ease 0.2s;
```

Artinya: ubah `background`, lamanya `0.5s`, gaya `ease`, mulai setelah jeda `0.2s`.

Yang wajib hanya **durasi**. Sisanya opsional.

## Dua Cara Menulis

### 1. Shorthand (singkat, paling sering dipakai)

```css
.kotak {
  transition: width 1s ease;
}
```

### 2. Dipecah per properti

```css
.kotak {
  transition-property: width;
  transition-duration: 1s;
  transition-timing-function: ease;
  transition-delay: 0s;
}
```

Hasilnya sama persis.

## Isi Tiap Bagian

**1. `transition-property`**: properti apa yang dihaluskan

```css
transition-property: width;        /* satu properti */
transition-property: width, color; /* beberapa */
transition-property: all;          /* semuanya (hindari) */
```

**2. `transition-duration`**: lama perubahan

```css
transition-duration: 0.3s;   /* detik */
transition-duration: 300ms;  /* milidetik, sama saja */
```

**3. `transition-timing-function`**: gaya geraknya

```css
transition-timing-function: ease;
transition-timing-function: linear;
transition-timing-function: ease-in;
transition-timing-function: ease-out;
transition-timing-function: ease-in-out;
```

**4. `transition-delay`**: jeda sebelum mulai

```css
transition-delay: 0.5s;
```

## Aturan Urutan Angka Waktu

Kalau ada dua angka waktu, **yang pertama = durasi, yang kedua = delay**.

```css
transition: opacity 2s 1s;
/*                  ^   ^
                durasi  delay */
```

## Beberapa Properti Sekaligus

Pisahkan dengan koma, tiap properti bisa punya durasi sendiri:

```css
transition: width 1s ease, background 0.3s linear, opacity 2s;
```

## Tempat Menaruhnya

Taruh di **elemen aslinya**, bukan di `:hover`:

```css
.kotak {
  transition: width 1s;   /* di sini */
}
.kotak:hover {
  width: 200px;
}
```

## Contoh Siap Pakai

```css
/* Ganti warna */
transition: background 0.3s ease;

/* Naik/besar/geser */
transition: transform 0.3s ease;

/* Muncul/hilang */
transition: opacity 0.4s ease;

/* Kartu (naik + bayangan) */
transition: transform 0.3s ease, box-shadow 0.3s ease;
```

## Ringkasan

| Mau apa             | Tulis                                |
| ------------------- | ------------------------------------ |
| Haluskan 1 properti | `transition: width 1s;`              |
| Haluskan beberapa   | `transition: width 1s, color 0.5s;`  |
| Tambah gaya gerak   | `transition: width 1s ease-in;`      |
| Tambah jeda         | `transition: width 1s ease-in 0.5s;` |