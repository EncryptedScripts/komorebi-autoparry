# Encrypted's Private Script — Komorebi Prison

Script combat all-in-one buat **[UPDATE!] Komorebi Prison**: auto parry yang ngikutin aturan parry asli game, lock target, visual HP/stamina musuh, dash & movement custom, plus sistem config — dengan menu bergaya RPG (sidebar tab, switch, slider).

## Cara pakai

Paste ke executor lu (Potassium / executor lain yang support `getgenv`, `VirtualInputManager`, `writefile`):

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/EncryptedScripts/komorebi-autoparry/main/KomorebiAutoparry.lua"))()
```

## Keybind default

| Tombol | Fungsi |
|---|---|
| `RightControl` | Auto parry on / off |
| `Insert` | Munculin / sembunyiin menu |
| `Z` | Lock ke musuh terdekat / unlock |

Semua keybind bisa diganti dari menu. Keybind aksi game (block, dash, M1, heavy, dll) juga bisa di-remap ke tombol **joystick / gamepad** atau tombol keyboard lain lewat tab **Keybind**.

## Fitur

**Combat**
- **Auto Parry** — timing dihitung per penyerang (tinggi badan, fighting style, ability aktif), termasuk heavy (Super). Cuma nekan block buat serangan yang beneran bakal kena, biar window parry gak kebuang.
- **Parry Chance, Rotation Cone, Max Range** — atur lewat slider.
- **Predict Combo** — lawan yang nge-lag (sinyal serangannya telat nyampe) pukulan combo berikutnya ditebak & di-parry duluan.
- **Auto Face** — kamera & badan otomatis ngadep penyerang, ada slider **Face Smoothing**. OFF = gak muter sama sekali.
- **Auto Stance** — otomatis masuk combat stance (block cuma jalan di stance).
- **Input Guard + buffer** — klik / heavy yang lu pencet pas parry jalan disimpen, terus dikirim otomatis abis parry (pas musuh kena parry-stun).
- **Lock Target** — pilih pemain dari dropdown atau lock ke yang terdekat; kamera & badan selalu ngadep target.
- **Smart Stomp** — pencet stomp (B / X) pas ada musuh knock: drag otomatis dilepas, badan ngadep korban, baru stomp. Lock & auto face gak ganggu selama finisher.
- **Auto Stomp** — musuh knock di jangkauan otomatis di-stomp (default OFF).

**Movement**
- **No Dash Cooldown** — pas dash game lagi cooldown, dash diganti dash custom (kurva kecepatan sama).
- **Dash Power** — slider kecepatan dash (default = nilai asli game) + tombol reset.
- **Infinite Stamina** — tetep sprint pas stamina abis.
- **No Slowdown / No Stun** — gak dipelanin pas nyerang / block / HP rendah, dan tetep bisa gerak pas stun.
- Pas ragdoll / knock / jatuh, script gak nyentuh badan sama sekali (lock & auto face diem, gak keliatan pake script).

**Visual**
- Nameplate musuh (nama, HP + ghost bar, stamina, cooldown heavy) & HUD sendiri gaya RPG (slot skill heavy) — semua bisa on/off.
- **Visual Parry** — indikator PARRY / BLOCK / KENA di bawah crosshair + highlight penyerang.
- **Visual Hitbox** — area kena serangan musuh di tanah (merah = bakal kena lu).

**Shader**
- Preset lighting: Cinematic, Vibrant, Golden Hour, Neon Night, Tropical, Sakura, Moonlight, Crisp Day, Noir — plus **Custom** (brightness, contrast, saturation, tint, bloom, sun rays, exposure, ambient, mood).
- Ringan: cuma 1 color correction + ngatur efek bawaan game, gak nambah pass render. Lighting asli balik pas dimatiin.
- **Hemat FPS** — matiin depth of field & bayangan global game.

**Keybind (joystick & keyboard)**
- Remap semua aksi game + aksi script ke tombol stik (default: B = block/parry, L2 = dash, R2 = M1, R1 = heavy, dst) atau tombol keyboard alternatif. Controller Remap & Keyboard Remap default OFF.
- Item di stik (piso, garpu, barbel, taser, dll): aksi item dicoba duluan, kalau item-nya gak punya aksi itu tombolnya balik ke fungsi remap (L2 tetep lari pas megang piso). Ambil item slot 1–3, ganti item, simpen item — tombol HP: tap = HP / simpen item, tahan = ambil piso.
- Aksi otomatis (parry, stance, buffer serangan) manggil handler game langsung, gak ada tombol keyboard palsu — pemain stik gak ke-switch ke skema keyboard.

**Animation Changer** (tab **Anim**)
- Ganti animasi M1–M4, heavy (R), idle combat, jalan combat, dan dash pake animasi style lain di game ini — **keliatan pemain lain**.
- Pilih per gerakan (tombol ▶ buat preview) atau pakai 15 preset: Speedster, Muay Thai, Iron Fist, Blood Rush, Street Brawler, Jaw Breaker, Mob Boss, The World, Aikido Flow, Heavyweight, Hybrid Striker, Thai Combo, Chaos Mix, Cinematic, Prison Classic.
- Cuma visual: timing kena, jangkauan, dan damage tetep ikut style asli lu. Heavy custom tetep bisa dipake. Kepasang lagi otomatis abis respawn / ganti style, ikut ke-save di config.

**Farm** (tab **Farm**)
- **Auto ambil garpu**: karakter jalan sendiri ke garpu terdekat yang masih ada di meja, terus diambil.
- **Auto ngasah jadi pisau**: pegang garpu, ngadep tembok, tiap cek dijawab tepat di tengah zona emas (target PRECISE 10/10). Server cuma mau mulai ngasah di tempat tertentu (di kafetaria ditolak), jadi pindah ke sel kalau muncul pesan ditolak.
- **Auto gym (Strength)**: jalan ke Bench Press / Lat Pulldown yang kosong, mulai set, tiap not ditekan pas waktunya, terus ngulang set.
- Selama farm jalan, jangan gerakin karakter. Matiin toggle = langsung berhenti.

**Anti AFK**
- Cegah kick idle 20 menit Roblox biar Activity Reward jalan (Yen tiap 30 menit, +3 Reroll tiap 120 menit di server yang sama). Default ON, bisa dimatiin di tab Settings.

**Config**
- Save pakai nama, pilih dari dropdown, load, delete, dan **autoload** config pilihan tiap script dijalanin.
- Disimpen di folder executor: `EncryptedPrivateScript/configs/`.

## Catatan

- Serangan & block selama stun, cooldown dash asli, dan stamina tetep dicek server — fitur movement cuma ngebebasin gerak di sisi client.
- Pakai dengan risiko sendiri.
