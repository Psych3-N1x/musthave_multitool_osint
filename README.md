
# 🕵️‍♂️ OSINT Multitool (Linux) – `multitool_musthave_osint`

[🇫🇷 Français](#français) | [🇬🇧 English](#english)

---

## 🇫🇷 Français

### 🔎 Présentation

`multitool_musthave_osint` est un **outil OSINT polyvalent** en ligne de commande, développé en **Rust**. Il permet d'extraire des informations publiques depuis plusieurs plateformes majeures, via des appels API ou du scraping léger.  
> ⚠️ L'outil est conçu **exclusivement pour les systèmes Linux** pour l'instant. Une version **Windows** est prévue très prochainement.

---

### 🛠️ Fonctionnalités disponibles

| Commande | Plateforme | Description |
|----------|------------|-------------|
| `--spotify` | Spotify | Récupère les métadonnées publiques d’un utilisateur Spotify (nom, followers, liens, etc.) via l’API officielle. |
| `--twitter` | Twitter | Récupère les métadonnées publiques d’un compte Twitter (followers, bio, etc.) via scraping HTML ou API. |
| `--tiktok` | TikTok | Récupère les métadonnées d’un compte TikTok public (bio, username, nombre de vidéos, etc.) via scraping HTML. |

---

### 🚀 Utilisation

#### ▶️ Exécution du binaire

Assurez-vous que le fichier `.env` est présent dans le même dossier que le binaire (voir ci-dessous).  
Lancez ensuite une des commandes suivantes selon la cible :

```bash
./multitool_musthave_osint --spotify --username 31dzxejfwxm76jm4vzx4iyv5ucuu
./multitool_musthave_osint --twitter --username ElonMusk
./multitool_musthave_osint --tiktok --username charlidamelio
```

---

### 🔐 Exemple de `.env` (⚠️ à créer manuellement)

```env
#  Spotify API
SPOTIFY_CLIENT_ID=your_spotify_client_id
SPOTIFY_CLIENT_SECRET=your_spotify_client_secret

#  Twitter API
TWITTER_BEARER_TOKEN=your_twitter_bearer_token

```

- Ces variables sont nécessaires, car l'outil utilise des APIs (authentification client credentials).
- Pour TikTok, aucun jeton n’est requis (scraping public).
- Je me suis obligé à utiliser l'API de Twitter parce que le scrapping ne permet pas d'avoir autant d'informations ou aussi préices.

---

### ⚙️ Détails techniques

- Écrit en Rust avec des modules séparés par plateforme (`spotify.rs`, `twitter.rs`, `tiktok.rs`).
- Architecture modulaire facilitant les futures extensions (`commands/mod.rs`).
- Utilisation de `dotenvy`, `clap`, `reqwest`, `rspotify`, et `scraper` selon les modules.
- Gestion des erreurs centralisée avec un module `error.rs`.

---

### 📦 Support & compatibilité

- ✅ Linux (x86_64)
- ⚠️ Android (via Termux) : possible, à compiler avec `cargo` sur Termux et git clone.
- ❌ Windows : pas encore supporté, **mais une version identique est prévue**.

---

### 🔄 Mise à jour

> 📢 Ce projet est **mis à jour régulièrement**.  
> De nouvelles plateformes, options de scraping et formats de sortie (JSON, CSV) sont en cours d’implémentation.

---

## 🇬🇧 English

### 🔎 Overview

`multitool_musthave_osint` is a **versatile OSINT command-line tool**, written in **Rust**, designed to extract public metadata from major platforms using lightweight scraping and official APIs.  
> ⚠️ Currently, it is designed **exclusively for Linux systems**. A **Windows version** is planned soon.

---

### 🛠️ Available Features

| Command | Platform | Description |
|--------|----------|-------------|
| `--spotify` | Spotify | Retrieves public metadata of a Spotify user (name, followers, links, etc.) via the official API. |
| `--twitter` | Twitter | Retrieves public metadata of a Twitter user (followers, bio, etc.) using HTML scraping or API. |
| `--tiktok` | TikTok | Retrieves metadata from a public TikTok profile (bio, username, number of videos, etc.) via scraping. |

---

### 🚀 Usage

#### ▶️ Binary Execution

Ensure your `.env` file is located in the same folder as the binary.  
Then run one of the following commands:

```bash
./multitool_musthave_osint --spotify --username 31dzxejfwxm76jm4vzx4iyv5ucuu
./multitool_musthave_osint --twitter --username ElonMusk
./multitool_musthave_osint --tiktok --username charlidamelio
```

---

### 🔐 Example `.env` file

```env
#  Spotify API
SPOTIFY_CLIENT_ID=your_spotify_client_id
SPOTIFY_CLIENT_SECRET=your_spotify_client_secret

#  Twitter API
TWITTER_BEARER_TOKEN=your_twitter_bearer_token

```

- requires authentication credentials.
- TikTok modules rely on public scraping.

---

### ⚙️ Technical Stack

- Written in **Rust**, modular architecture (`spotify.rs`, `twitter.rs`, `tiktok.rs`)
- Uses `dotenvy`, `clap`, `reqwest`, `rspotify`, and `scraper`.
- Centralized error handling through `error.rs`.

---

### 📦 Compatibility

- ✅ Linux (x86_64)
- ⚠️ Android (via Termux): works if compiled on-device.
- ❌ Windows: currently unsupported, **but a version is coming soon.**

---

### 🔄 Updates

> 📢 This repository is **updated regularly**.  
> New platforms, scraping techniques, and output formats (e.g. JSON/CSV) will be added soon.

---

## 📬 Contact & Contribution

> This tool is currently **binary-only** and not open to external contributions.  
If you have feedback, ideas, or want to support future platforms, feel free to open an issue (if hosted on GitHub).
