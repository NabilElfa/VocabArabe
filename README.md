# عربي — Application de vocabulaire arabe (PWA)

## Déploiement sur Vercel (5 minutes)

### Étape 1 — Compte GitHub
1. Crée un compte sur [github.com](https://github.com) si tu n'en as pas
2. Crée un **nouveau dépôt** (bouton vert "New") → nom : `arabic-vocab` → Public → Create

### Étape 2 — Mettre les fichiers sur GitHub
Deux options :

**Option A — Interface web (plus simple)**
1. Dans ton dépôt GitHub, clique "uploading an existing file"
2. Glisse-dépose **tous les fichiers** de ce dossier (en respectant la structure)
3. Commit changes

**Option B — Terminal (si tu as Git)**
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/TON-PSEUDO/arabic-vocab.git
git push -u origin main
```

### Étape 3 — Déployer sur Vercel
1. Va sur [vercel.com](https://vercel.com) → "Sign up with GitHub"
2. Clique **"New Project"** → importe ton dépôt `arabic-vocab`
3. Laisse tout par défaut → **Deploy**
4. En 30 secondes, tu as une URL publique genre `arabic-vocab.vercel.app`

### Étape 4 — Installer sur ton téléphone
- **iPhone** : ouvre l'URL dans Safari → partage → "Sur l'écran d'accueil"
- **Android** : ouvre dans Chrome → menu ⋮ → "Ajouter à l'écran d'accueil"

---

## Ajouter tes prochaines leçons

Dans `public/index.html`, trouve le tableau `const VOCAB = [...]` et ajoute tes mots :

### Nom / Adjectif
```javascript
{fr:"Le livre", sg:"كِتَابٌ", pl:"كُتُبٌ", l:5, type:"nom"},
{fr:"Grand",    sg:"كَبِيرٌ", pl:"كِبَارٌ", l:5, type:"adj"},
// Sans pluriel :
{fr:"Toujours", sg:"دَائِماً", pl:null,      l:5, type:"adv"},
```

### Verbe (passé / présent / مصدر)
```javascript
{fr:"Écrire", type:"verbe", passe:"كَتَبَ", present:"يَكْتُبُ", masdar:"كِتَابَةٌ", l:5},
{fr:"Lire",   type:"verbe", passe:"قَرَأَ", present:"يَقْرَأُ", masdar:"قِرَاءَةٌ", l:5},
```

### Expression / Particule
```javascript
{fr:"Peut-être", sg:"رُبَّمَا", pl:null, l:5, type:"expr"},
```

---

## Structure des fichiers
```
arabic-pwa/
├── public/
│   ├── index.html      ← Application complète
│   ├── manifest.json   ← Config PWA
│   ├── sw.js           ← Service worker (mode hors-ligne)
│   └── icons/
│       ├── icon-192.png
│       └── icon-512.png
└── vercel.json         ← Config Vercel
```
