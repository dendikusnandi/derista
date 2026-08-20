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
rm -rf derista && curl -fsSL https://raw.githubusercontent.com/dendikusnandi/derista/main/derista -o /usr/bin/derista && chmod +x /usr/bin/derista && derista install 
```

> ✅ **Satu perintah** — download, install, cleanup otomatis.
> ✅ **Otomatis install** Node.js, tmux, jq, git, Claude Code, dll.
> ✅ **Skip** kalau sudah terinstall.

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
| **Tool `derista`** | dipasang ke `/usr/bin/derista` (TUI multi-akun) |

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

```bash
rm /usr/bin/derista
npm rm -g @anthropic-ai/claude-code
```

---

## Keamanan

- Repo ini **nggak nyimpen API key / token apa pun**. Array `API_KEYS` kosong.
- Token yang lo tambah lewat menu `a` disimpan **lokal** di `/usr/bin/derista`.

---

<div align="center">

## 🔥 Made with ❤️ by

### **DENDI KUSNANDI**

![GitHub](https://img.shields.io/badge/GitHub-dendikusnandi-181717?style=for-the-badge&logo=github)

**⚡ AI Infrastructure Builder ⚡**

</div>
