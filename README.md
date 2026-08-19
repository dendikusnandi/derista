<div align="center">

# DENDI KUSNANDI

### 🚀 AI Infrastructure & Tool Builder

---

</div>

# derista

**Auto-installer + pusat kendali Claude Code buat VPS.**
Satu script (`derista.sh`) buat bootstrap VPS baru dari nol: pasang Node.js, Claude Code CLI, tmux, jq, dan tool TUI `derista` buat ngelola banyak akun/token Claude sekaligus.

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
> ⚠️ Tambahkan akun & API key lo sendiri lewat menu setelah kepasang.

---

## Install cepat (VPS baru)

```bash
curl -fsSL https://raw.githubusercontent.com/dendikusnandi/derista/main/derista.sh | bash -s install
```

> ✅ **Tidak perlu password!**
> ✅ **Otomatis install** Node.js, tmux, jq, git, Claude Code.
> ✅ **Skip** kalau sudah terinstall.

---

### 📥 Download manual

```bash
curl -fsSLO https://raw.githubusercontent.com/dendikusnandi/derista/main/derista.sh
chmod +x derista.sh
./derista.sh install
```

---

Habis install tinggal ketik:

```bash
derista
```

---

## Yang dipasang

| Komponen | Keterangan |
|---|---|
| **Node.js LTS (≥18)** | via NodeSource kalau belum ada / masih tua |
| **Claude Code CLI** | `@anthropic-ai/claude-code` → perintah `claude` |
| **tmux** | buat session management (background & monitoring) |
| **jq** | JSON processing buat parsing transcript |
| **git + curl** | Version control & HTTP requests |
| **Tool `derista`** | dipasang ke `/usr/bin/derista` (TUI multi-akun) |

### Default Settings

| Setting | Value |
|---|---|
| **URL** | `https://routers.dendikusnandi.tech` |
| **Model** | `dendi-ai` |
| **Mode** | `langsung` (direct) |

---

## Cara pakai tool `derista`

Jalankan `derista` → muncul daftar akun. Pilih pakai nomor lalu **Enter** buat launch Claude Code dengan token + URL + model akun itu.

### Menu

| Tombol | Fungsi |
|---|---|
| `a` | **tambah akun** (nama, token `sk-…`, URL API, model, mode) |
| `e` | edit akun |
| `d` | hapus akun |
| `v` | lihat detail akun |
| `o` | kelola daftar model |
| `j` | kelola API key |
| `u` | kelola URL endpoint |
| `s` | setelan (default model, cmd, mode, dll) |
| `m` | pantau pesan Claude (baca transcript `~/.claude/projects/*.jsonl`) |
| `t` | monitor sesi tmux |
| `n` | buka tmux baru |
| `k` | kill semua sesi tmux |
| `c` | clear history chat |
| `g` | tambah memory |
| `0` | keluar |

### Nambah akun pertama

Tekan `a`, isi:

- **Nama** — bebas, mis. `kerja`
- **Token** — token `sk-…` dari provider lo
- **URL API** — base URL provider (kosongin = pakai default)
- **Model** — pilih dari daftar (default `dendi-ai`)
- **Mode** — `langsung` (jalan di terminal ini) atau `tmux` (sesi background)

---

## Uninstall

```bash
rm /usr/bin/derista              # copot tool derista
npm rm -g @anthropic-ai/claude-code   # copot Claude Code (opsional)
```

---

## Keamanan

- Repo ini **nggak nyimpen API key / token apa pun**. Array `API_KEYS` kosong.
- Token yang lo tambah lewat menu `a` disimpan **lokal** di `/usr/bin/derista` di VPS lo — jangan commit file itu ke git / share sembarangan.

---

<div align="center">

## 🔥 Made with ❤️ by

### **DENDI KUSNANDI**

![GitHub](https://img.shields.io/badge/GitHub-dendikusnandi-181717?style=for-the-badge&logo=github)
![9Router](https://img.shields.io/badge/9Router-dendikusnandi.tech-10B981?style=for-the-badge)

---

**⚡ AI Infrastructure Builder ⚡**

</div>
