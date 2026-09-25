# MEMOu Deluxe — Midnight Kitty

Template Deluxe yang mengikuti struktur repository/controller MEMOu.

## Struktur repository

```text
assets/
├── audio/
│   └── bgm.mp3
└── images/
    ├── cover.jpg
    ├── mem_1.jpg
    ├── mem_2.jpg
    ├── ...
    └── mem_14.jpg
README.md
index.html
script.js
style.css
```

Tidak memakai file schema/config tambahan di root. Controller membaca `script.js`.

## Data editable Controller

Objek `DELUXE_CONFIG` berada di bagian paling atas `script.js`.

Field utama:
- `girlfriendName`
- `nickname`
- `boyfriendName`
- `birthdayDate`
- `heroSubtitle`
- `ticker`
- `loveLetter`
- `finalMessage`
- `music`
- `theme`
- `castDialogues`

`loveLetter` sengaja berupa **string**, supaya sesuai field textarea Controller.

## Foto Deluxe — 15 slot

Deklarasi slot foto di `script.js`:

```js
const PHOTOS = ["cover.jpg", ...Array.from({length:14}, (_, i) => `mem_${i+1}.jpg`)];
```

Mapping:
- `cover.jpg` = Foto utama / hero
- `mem_1.jpg` = Memory 1
- ...
- `mem_14.jpg` = Memory 14

Total = 15 foto.

Jangan mengganti pola nama file ini bila Controller Studio masih menggunakan parser yang sama dengan template Deluxe referensi.

## Audio

Background music:
`assets/audio/bgm.mp3`

Nilai sumber audio juga tersedia melalui:

```js
music: "assets/audio/bgm.mp3"
```

## Catatan

Karakter kucing adalah elemen tema SVG/DOM dari `script.js`, bukan slot foto customer.
Foto customer hanya berasal dari `assets/images/cover.jpg` dan `mem_1.jpg` sampai `mem_14.jpg`.
