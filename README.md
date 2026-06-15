# Music Player - DIMMI PERCHÉ

🎵 Player privato per la canzone "DIMMI PERCHÉ" con **Git LFS per tracciare i file media su GitHub**.

---

## ⚡ Quick Start (con Git LFS)

### 1️⃣ Prerequisiti
- Git installato ([https://git-scm.com](https://git-scm.com))
- **Git LFS** installato ([https://git-lfs.github.com](https://git-lfs.github.com))
  - macOS: `brew install git-lfs`
  - Linux: `apt-get install git-lfs`
  - Windows: Scarica dal sito ufficiale

### 2️⃣ Setup Locale

```bash
# 1. Clona il repo (o inizializza una cartella vuota)
git clone https://github.com/TUO_USERNAME/music-player-dimmi-perche.git
cd music-player-dimmi-perche

# 2. Esegui lo script di setup (oppure i comandi sotto)
bash setup.sh

# OPPURE esegui manualmente:
# a) Installa Git LFS
git lfs install

# b) Configura quali file tracciare
git add .gitattributes

# c) Installa dipendenze
npm install

# d) Avvia il server locale
npm start
# Apri http://localhost:3000
```

### 3️⃣ Cos'è Git LFS?

**Git Large File Storage** permette di:
- ✅ Tracciare file grandi (audio/video) su GitHub senza rallentamenti
- ✅ Mantenere il repo GitHub leggero (i file media sono su server separato)
- ✅ Caricare file fino a 2GB singolarmente
- ✅ Download intelligente (scarica solo quel che serve)

**Configurazione automatica** in `.gitattributes`:
```
*.m4a filter=lfs diff=lfs merge=lfs -text
*.mp4 filter=lfs diff=lfs merge=lfs -text
```

---

## 🚀 Deploy su Render (con Git LFS)

### Passaggio 1: Crea Repo GitHub

```bash
# Se non l'hai già fatto
git init
git add .
git commit -m "Initial commit: music player con Git LFS"

# Crea un nuovo repo su https://github.com/new
# Poi collega il remote:
git branch -M main
git remote add origin https://github.com/TUO_USERNAME/music-player-dimmi-perche.git
git push -u origin main
```

**Nota:** Git LFS farà upload dei file `.m4a` e `.mp4` automaticamente! 🎬

### Passaggio 2: Deploy su Render

1. Vai su [render.com](https://render.com)
2. Clicca **New +** → **Web Service**
3. Seleziona il repo GitHub che appena hai pushato
4. Configura:
   - **Name**: `music-player-dimmi-perche`
   - **Environment**: Node
   - **Build Command**: `npm install`
   - **Start Command**: `npm start`
   - **Plan**: Free (o Paid per uptime 24/7)
5. Clicca **Create Web Service**

**Render scaricherà automaticamente i file LFS!** ✨

### Passaggio 3: Verifica

Una volta deployato, il tuo link sarà:
```
https://music-player-dimmi-perche.onrender.com
```

---

## 📁 Struttura File

```
music-player-dimmi-perche/
├── server.js                           # Server Express
├── package.json                        # Dipendenze
├── .gitignore                          # File da escludere da git
├── .gitattributes                      # Configurazione Git LFS ⭐
├── setup.sh                            # Script di setup
├── public/
│   ├── index.html                      # Pagina HTML
│   └── media/
│       ├── DIMMI_PERCHÉ.m4a           # Audio (tracciato con LFS)
│       └── DIMMI_PERCHE__Lyrics_Video_.MP4  # Video (tracciato con LFS)
└── README.md                           # Questo file
```

---

## ✨ Caratteristiche

✅ **Audio + Video Player** nativi con HTML5  
✅ **Git LFS** per file media su GitHub  
✅ **Design moderno** e responsive  
✅ **Render deployment** automatico  
✅ **Nessun download** scaricato dai visitor  
✅ **Cache intelligente** per performance  

---

## 🔧 Troubleshooting

### "Git LFS not found"
```bash
# Installa Git LFS:
# macOS:
brew install git-lfs

# Linux:
sudo apt-get install git-lfs

# Poi:
git lfs install
```

### I file .m4a/.mp4 non si vedono?
```bash
# Verifica che Git LFS abbia tracciato i file:
git lfs ls-files

# Se vuoti, esegui:
git add .gitattributes
git add public/media/
git commit -m "Add media files with LFS"
git push
```

### Render non carica i file media?
1. Verifica che Git LFS sia installato sul tuo PC
2. Fai `git push` di nuovo (Git LFS farà upload)
3. Riavvia il servizio Render

---

## 📊 Dimensioni File

| File | Dimensione | Tracciato con |
|------|-----------|--------------|
| DIMMI_PERCHÉ.m4a | 5.5 MB | ✅ Git LFS |
| DIMMI_PERCHE__Lyrics_Video_.MP4 | 192 MB | ✅ Git LFS |

---

## 💾 Note Importanti

- **Spazio GitHub**: Il repo GitHub rimane piccolo (~50KB) grazie a LFS
- **Uptime Render Free**: Tira giù dopo 15 min di inattività (upgrade per 24/7)
- **Limite LFS GitHub**: 1GB di storage gratuito, poi paghi per più storage
- **Private Repo**: Puoi usare un repo privato se non vuoi che sia pubblico

---

## 🎵 Prossimi Step

1. ✅ Hai i file pronti
2. ⏳ Crea repo GitHub
3. ⏳ Esegui `git push`
4. ⏳ Deploy su Render
5. ⏳ Condividi il link!

---

Made with ❤️ by Claude
