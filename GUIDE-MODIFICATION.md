# 📖 Guide de modification — Site IJ Genesys

Ce guide te permet de **modifier ton site toi-même** sans coder à partir de zéro. Tout est dans **un seul fichier** : `index.html`.

---

## 🎯 Comment éditer le site

### Option A — Éditeur en ligne (le plus simple)
1. Va sur https://github.com/[ton-compte]/ijgenesys
2. Clique sur `index.html`
3. Clique sur l'icône **crayon** (✏️) en haut à droite
4. Modifie ce que tu veux
5. Descends et clique sur **"Commit changes"**
6. Ton site se met à jour automatiquement en 2-3 minutes ✨

### Option B — En local (plus avancé)
1. Télécharge le ZIP depuis ton GitHub
2. Décompresse-le
3. Ouvre `index.html` dans **Notepad++ / VS Code / Sublime Text** (pas Word !)
4. Modifie, sauvegarde
5. Re-upload sur GitHub

---

## 🎨 1. Changer les COULEURS

**Cherche ces lignes au début du fichier** (autour de la ligne 110-120) :

```css
:root {
  --bleu-nuit: #1A2B4A;     ← Change ici pour ta couleur principale
  --corail: #FF6B5B;        ← Change ici pour ta couleur d'accent
  --creme: #FBF6EF;         ← Fond du site
  --gris-fonce: #2A2A3E;    ← Couleur du texte
}
```

**💡 Astuce** : Utilise https://coolors.co pour trouver des palettes harmonieuses.

---

## 💰 2. Changer les PRIX

**Cherche `1490€` dans le fichier** (Ctrl+F) — il y en a 3 occurrences principales :

```html
<!-- Formule Essentielle -->
<span class="price-amount">1490</span>€

<!-- Formule Signature -->
<span class="price-amount">2490</span>€

<!-- Formule Excellence -->
<span class="price-amount">3990</span>€
```

→ Change juste les **chiffres**, pas le HTML autour.

---

## ✏️ 3. Changer les TEXTES (titres, descriptions)

Cherche le texte exact à modifier avec **Ctrl+F**, puis remplace-le.

**Exemples :**
- Titre principal : *"Des sites web qui révèlent vos talents"*
- Tagline : *"Studio digital parisien"*
- Email : *"ijgenesys@gmail.com"* (apparaît plusieurs fois — **change PARTOUT**)
- Téléphone : *"06 47 73 84 03"*

⚠️ **Attention** : ne modifie pas les balises `<` et `>`, seulement le texte entre elles.

✅ Bon :
```html
<h1>Mon nouveau titre génial</h1>
```

❌ Mauvais :
```html
Mon nouveau titre génial    ← Sans balises
```

---

## 🎯 4. Modifier les DÉMOS affichées

Sur la page tarifs, tu as 3 liens "Voir un exemple →". Ils pointent vers :

```html
<a href="demo-essentielle.html">Voir un exemple →</a>
<a href="demo-signature.html">Voir un exemple →</a>
<a href="demo-excellence.html">Voir un exemple →</a>
```

**Pour pointer vers une autre démo** (ex : En Vogue), change le `href` :

```html
<a href="demo-envogue-signature.html">Voir un exemple →</a>
```

---

## 📞 5. Changer les COORDONNÉES

**Recherche ces éléments** (Ctrl+F) :

| Élément | À modifier |
|---|---|
| Téléphone | `06 47 73 84 03` → ton numéro |
| Email | `ijgenesys@gmail.com` → ton email |
| Adresse | `Paris, France` (ligne ~1700) |
| SIRET | À ajouter dans mentions-legales.html |

⚠️ **Modifie partout** où tu trouves l'ancien email/tél — ils apparaissent dans :
- Le site principal (index.html)
- Les 4 pages légales (cgv, mentions, confidentialité, cookies)
- Le footer

---

## 🌟 6. Changer le LOGO

Le logo Étoile Genèse est utilisé à **3 endroits** :

### 6.1 Favicon (icône onglet navigateur)
Cherche dans `index.html` : `<link rel="icon"`
C'est un SVG inline en base64. **Pour le changer** : crée ton nouveau SVG, encode-le ici → https://yoksel.github.io/url-encoder/

### 6.2 Logo navigation
Cherche : `nav-logo-icon`
C'est le SVG dans la barre du haut.

### 6.3 Logo footer
Cherche : `footer-brand-logo-icon`
C'est le SVG dans le pied de page.

⚠️ **Pour modifier** : il faut connaître le SVG. Si tu veux changer le logo, **demande-moi** — je te ferai les 3 versions en cohérence.

---

## 📄 7. Ajouter / Modifier une SECTION

### Structure du site (ordre des sections)
```
1. Hero (haut)
2. Services
3. Tarifs (3 formules)
4. Démos
5. Processus
6. Témoignages (à ajouter)
7. FAQ
8. Contact
9. Footer
```

**Pour ajouter une nouvelle section**, copie-colle une section existante en l'adaptant. Ex pour ajouter une section témoignages :

```html
<section class="section" id="temoignages">
  <div class="container">
    <h2 class="section-title">Ils nous ont fait confiance</h2>
    <!-- Ton contenu -->
  </div>
</section>
```

---

## 🔒 8. NE PAS TOUCHER (sauf si tu sais)

Ces parties sont **critiques** pour la sécurité/RGPD. Ne les modifie pas :

❌ Ne pas modifier :
- `<meta http-equiv="Content-Security-Policy"` (sécurité)
- Les `<script>` de gestion des cookies
- Les `application/ld+json` (SEO)
- Les balises `<meta>` du début

---

## 🚀 9. METTRE EN LIGNE (héberger officiellement)

Tu as **3 options** pour héberger ton site :

### Option A — GitHub Pages (GRATUIT)
✅ Déjà en place : `https://ijgenesys.github.io/ijgenesys/`
- Avantages : Gratuit, HTTPS auto, déploiement auto
- Inconvénients : URL longue, pas de domaine perso

### Option B — Acheter un domaine + GitHub Pages (~10€/an)
1. Achète `ijgenesys.com` sur **OVH** ou **Gandi** (~10€/an)
2. Dans GitHub → Settings → Pages → ajoute ton domaine
3. Configure les DNS chez OVH (CNAME vers `ijgenesys.github.io`)
4. ✨ Ton site sera accessible sur `ijgenesys.com`

### Option C — Hébergement classique (~30€/an)
**OVH Pack Web** : 27€/an, domaine + hébergement
1. Achète l'offre
2. Upload tes fichiers via FTP (FileZilla)
3. Configure le DNS

**💡 Mon conseil** : **Option B** (domaine + GitHub Pages) — le meilleur rapport qualité/prix.

---

## 📊 10. AJOUTER GOOGLE ANALYTICS (optionnel)

⚠️ Si tu actives Analytics, tu dois **modifier le bandeau cookies** (ce n'est plus du tracking minimal).

1. Crée un compte sur https://analytics.google.com
2. Récupère ton code de mesure `G-XXXXXXXXXX`
3. Ajoute juste avant `</head>` dans index.html :

```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  if (localStorage.getItem('ij_cookies_choice') === 'accept') {
    gtag('js', new Date());
    gtag('config', 'G-XXXXXXXXXX');
  }
</script>
```

→ Analytics ne s'active **que si** le visiteur a accepté les cookies. ✅ RGPD-compliant.

---

## 🆘 EN CAS DE PROBLÈME

### Le site casse après modification
1. Va dans GitHub → onglet "Commits"
2. Trouve ton dernier commit
3. Clique "Revert"
4. Tout revient comme avant ✨

### Une fonction ne marche plus
- Cherche dans le code une balise `<script>` que tu aurais peut-être cassée
- Re-télécharge le ZIP propre depuis ton historique GitHub

### Tu veux faire un grand changement
- **Demande-moi** ! Je peux te générer une nouvelle version propre.

---

## 📋 CHECKLIST AVANT MISE EN LIGNE

- [ ] Tous les `06 47 73 84 03` remplacés par TON numéro
- [ ] Tous les `ijgenesys@gmail.com` remplacés par TON email
- [ ] SIRET ajouté dans mentions-legales.html
- [ ] Adresse mise à jour partout
- [ ] Prix actuels (1490/2490/3990) ou les tiens
- [ ] Site testé sur mobile (responsive)
- [ ] Bandeau cookies fonctionne
- [ ] Pages légales accessibles
- [ ] Favicon visible dans l'onglet

---

## 🎯 CE QUE LE SITE FAIT POUR TOI

Ton site est **prêt à scaler**. Quand un prospect te répond :
1. Il clique sur le lien de démo dans ton email
2. Il navigue, voit ton site officiel via le footer
3. Il voit ton logo, ton numéro, ton email partout
4. Il appelle ou écrit
5. 💰 Tu signes

**Bonne chance avec ta prospection !** 🚀

---

*Document généré le 13 mai 2026 — IJ Genesys*
