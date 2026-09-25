# ⚠️ [OBSOLÈTE / DÉPRÉCIÉ] App Hermès Core

> **IMPORTANT** : Ce dossier est un **reliquat du prototype initial d'août/septembre 2026**.
> Il est officiellement **remplacé par le module UI Client souverain `apps/ui-client`** situé dans le dépôt `orso-core`.
> Toute la production s'appuie désormais sur `https://app.orso-agents.fr` orchestrée via Docker Ingress et Supabase IAM. Ne plus utiliser ce prototype.

---

# App Hermès Core — Espace Client Multi-Agents (Archive)

---

## 🚀 Fonctionnalités Clés

1. **Un canal de chat dédié par agent :**
   - **🔵 Hermès Recouvrement (Jérôme)** : Assistant ADV & Credit Manager (analyse balance âgée, relances de factures L.441-10, négociations d'échéanciers).
   - **🟣 Hermès Commercial (Lucas)** : Qualification de leads et CRM.
   - **🟢 Hermès Support Client (Clara)** : Support 24/7 et escalade de tickets.
   - **🟡 Hermès Appel d'Offre (Victor)** : Analyse de DCE et mémoires techniques.

2. **Cartes d'Action Interactives & Streaming Temps Réel :**
   - Validation en un clic des relances de factures impayées (*Approuver et envoyer*, *Reporter 48h*).
   - Visualisation immédiate de l'encours et des retards critiques.
   - Streaming fluide mot à mot et affichage du processus de réflexion de l'agent.

3. **Supervision Transverse par Olympe :**
   - Réception en direct des consignes transverses diffusées par Olympe (mises à jour réglementaires, alertes de conformité).
   - Suivi de la santé de la flotte de conteneurs.

4. **Multi-plateforme & PWA :**
   - Fonctionne sur navigateur desktop et mobile.
   - Installable en PWA (Progressive Web App) sur iOS et Android.
   - Charte graphique alignée sur `Site_Hermes-core` (Dark UI, accents or et bleu, *Plus Jakarta Sans*).

---

## 🛠️ Démarrage Rapide

### Option 1 : Lancement Local Immédiat
Vous pouvez ouvrir directement `index.html` dans n'importe quel navigateur, ou lancer un serveur local :
```bash
# Dans le dossier App_Hermes Core :
python3 -m http.server 9300
```
Puis accédez à : `http://localhost:9300`

### Option 2 : Déploiement Conteneurisé avec Docker Compose
```bash
docker compose up -d --build
```
L'application sera accessible sur le port `9300`.

---

## 🔌 Architecture des Flux

```
[Navigateur / Mobile PWA (Port 9300)]
         │
         ├─── (WebSocket / REST) ──► [hermes_recouvrement_agent : Port 9229]
         ├─── (Directives) ────────► [olympe_supervisor : Port 9230]
         └─── (Portail Vitrine) ───► [Site_Hermes-core]
```
