# 📦 LOCAL-AI-PACKAGED – Stack Technique

Ce dépôt contient toute l'infrastructure nécessaire pour faire tourner un **SaaS IA local, sécurisé et modulaire**, combinant :
- des agents IA no/low-code
- un backend self-hosted
- un frontend moderne multi-tenant (custom domains)
- des automatisations via n8n
- une interface de recherche privée

---

## 📁 Structure du projet

### `/backend/`
Contient tous les services **métier et IA** :

- `/flowise/` → Agents IA construits en no-code avec Flowise (RAG, prompts dynamiques, etc.)
- `/n8n/` → Nœud principal n8n (automatisations IA, emailing, scraping, etc.)
- `/n8n-tool-workflows/` → Librairie de workflows n8n prêts à l'emploi
- `/saas/` → App Wasp (admin, utilisateurs, facturation, API sécurisée)
- `/searxng/` → Moteur de recherche open-source et privé (utilisé pour enrichir les agents)

---

### `/frontend/`
App Next.js basée sur le **Platforms Starter Kit de Vercel**, enrichie avec `shadcn/ui` pour une UX moderne.
Fonctionnalités :
- multi-tenant : sous-domaines ou domaines personnalisés
- pages statiques/ISR ultra rapides
- éditeur markdown avec IA (Novel)
- interface client intuitive pour interagir avec les agents IA

---

### Fichiers racine

- `.env` → Variables d'environnement pour tous les services (backend & frontend)
- `docker-compose.yml` → Démarre l'intégralité de la stack (prod ready)
- `docker-compose.override.yml` → Override pour le dev local léger
- `start_services.py` → Script Python pour lancer les services automatiquement
- `Caddyfile` → Configuration de Caddy pour le HTTPS automatique (via Let's Encrypt)
- `README.md` → Intro générale
- `LICENSE` → Licence du projet (open-source)

---

## 🚀 Démarrage rapide

```bash
# 1. Copier les variables d'environnement
cp .env.example .env

# 2. Lancer tous les services
docker-compose up --build
