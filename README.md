<div align="center">

# DENDI KUSNANDI

### 🚀 AI Infrastructure & Tool Builder

---

</div>

# derista

**Auto-installer + pusat kendali Claude Code buat VPS.**
Satu script (`derista`) buat bootstrap VPS baru dari nol: pasang Node.js, Claude Code CLI, tmux, jq, dan tool TUI `derista` buat ngelola banyak akun/token Claude sekaligus.

<div align="center">

![Profile](https://img.shields.io/badge/Developer-Dendi_Kusnandi-7C3AED?style=for-the-badge)
![GitHub](https://img.shields.io/badge/GitHub-dendikusnandi-181717?style=for-the-badge&logo=github)
![9Router](https://img.shields.io/badge/Router-9Router-10B981?style=for-the-badge)

</div>

```
╔══════════════════════════════════════════════════════════════╗
║                                                              ║
║   ███╗   ██╗███████╗██████╗ ███████╗██████╗ ██╗███████╗     ║
║   ████╗  ██║██╔════╝██╔══██╗██╔════╝██╔══██╗██║██╔════╝     ║
║   ██╔██╗ ██║█████╗  ██████╔╝███████╗██████╔╝██║███████╗     ║
║   ██║╚██╗██║██╔══╝  ██╔══██╗╚════██║██╔═══╝ ██║╚════██║     ║
║   ██║ ╚████║███████╗██║  ██║███████║██║     ██║███████║     ║
║   ╚═╝  ╚═══╝╚══════╝╚═╝  ╚═╝╚══════╝╚═╝     ╚═╝╚══════╝     ║
║                                                              ║
║   ══════════════════════════════════════════════════════     ║
║   DERISTA · Select-CRUD Kendali Claude                    ║
║   ══════════════════════════════════════════════════════     ║
║                                                              ║
║   (belum ada akun — tekan a untuk menambah)                 ║
║                                                              ║
║   ── AKSI ──────────────────────────────────────────────     ║
║    a  Tambah akun          m  Resume sesi Claude            ║
║    e  Edit akun            t  Pantau sesi tmux              ║
║    d  Hapus akun           n  Sesi tmux baru                ║
║    v  Lihat data akun      k  Matikan semua sesi tmux       ║
║    o  Kelola model         c  Hapus semua riwayat chat      ║
║    j  Kelola API key       g  Kelola memori                 ║
║    u  Kelola URL           s  Pengaturan                    ║
║    0  Keluar                                                 ║
║                                                              ║
║   nomor = jalankan akun · huruf = aksi                      ║
║                                                              ║
╚══════════════════════════════════════════════════════════════╝
```

> ✅ **Default:** URL = `routers.dendikusnandi.tech` | Model = `dendi-ai`

---

## Download & Install

```bash
curl -fsSL https://raw.githubusercontent.com/dendikusnandi/derista/main/derista -o /tmp/derista && bash /tmp/derista install
```

> ✅ **Satu perintah** — download ke `/tmp` (aman dijalankan dari folder apa pun), install, cleanup otomatis.
> ✅ **Otomatis install** Node.js, tmux, jq, Claude Code, dll — **skip** yang sudah ada.
> ✅ **Root** → `/usr/bin/derista`, paket sistem dipasang langsung.
> ✅ **Non-root + sudo** → `~/.local/bin/derista`, paket sistem via sudo, PATH ditambah otomatis ke `.bashrc`/`.zshrc`.
> ✅ **Non-root tanpa sudo** → `~/.local/bin/derista` + Claude Code ke `~/.local`. Paket sistem di-skip (pakai yang sudah ada); installer kasih **ringkasan jujur** komponen mana yang berhasil.

> ℹ️ Kenapa `-o /tmp/derista`? Biar download nggak gagal (`curl: (23)`) kalau folder saat ini nggak bisa ditulis (mis. user biasa di `/root`) atau bentrok dengan folder data `~/derista`.

---

## Yang dipasang

| Komponen | Keterangan |
|---|---|
| **Node.js LTS (≥18)** | via NodeSource kalau belum ada / masih tua |
| **Claude Code CLI** | `@anthropic-ai/claude-code` → perintah `claude` |
| **tmux** | buat session management (background & monitoring) |
| **jq** | JSON processing buat parsing transcript |
| **git + curl** | Version control & HTTP requests |
| **whois, bzip2, gzip, wget, screen, nscd** | System packages |
| **Tool `derista`** | dipasang ke `/usr/bin/derista` (root) atau `~/.local/bin/derista` (user) (TUI multi-akun) |

### Default Settings

| Setting | Value |
|---|---|
| **URL** | `https://routers.dendikusnandi.tech` |
| **Model** | `dendi-ai` |
| **Mode** | `langsung` (direct) |

---

## Cara pakai

Jalankan `derista` → muncul daftar akun. Pilih pakai nomor lalu **Enter** buat launch Claude Code.

### Menu

| Tombol | Fungsi |
|---|---|
| `a` | **tambah akun** |
| `e` | edit akun |
| `d` | hapus akun |
| `v` | lihat detail akun |
| `o` | kelola daftar model |
| `j` | kelola API key |
| `u` | kelola URL endpoint |
| `s` | setelan |
| `m` | pantau pesan Claude |
| `t` | monitor sesi tmux |
| `n` | buka tmux baru |
| `k` | kill semua sesi tmux |
| `c` | clear history chat |
| `g` | tambah memory |
| `0` | keluar |

---

## Uninstall

**Otomatis** — satu perintah, tau sendiri lokasinya:

```bash
derista uninstall
```

> ✅ **Root** → hapus `/usr/bin/derista` · **Non-root** → hapus `~/.local/bin/derista` + bersihin baris PATH di `.bashrc`/`.zshrc`.
> ✅ Alias: `derista -u` atau `derista remove`. Bisa juga lewat menu **`s` (Pengaturan) → `9`**.
> ✅ Data akun di `~/derista` **tetap aman** (nggak ikut kehapus).

Manual (kalau perlu):

```bash
# Root
rm /usr/bin/derista
npm rm -g @anthropic-ai/claude-code

# Non-root
rm ~/.local/bin/derista
npm rm -g @anthropic-ai/claude-code
# Hapus juga baris PATH ~/.local/bin di .bashrc/.zshrc kalau ada
```

---

## Keamanan

- Repo ini **nggak nyimpen API key / token apa pun**. Array `API_KEYS` kosong.
- Token yang lo tambah lewat menu `a` disimpan **lokal** di file `derista` yang terpasang — `/usr/bin/derista` (root) atau `~/.local/bin/derista` (non-root).

---

<div align="center">

## 🔥 Made with ❤️ by

### **DENDI KUSNANDI**

![GitHub](https://img.shields.io/badge/GitHub-dendikusnandi-181717?style=for-the-badge&logo=github)

**⚡ AI Infrastructure Builder ⚡**

</div>
