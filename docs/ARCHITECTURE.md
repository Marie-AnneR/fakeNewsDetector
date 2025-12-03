# ARCHITECTURE.md — Architecture du Détecteur de Fake News

## 🧱 1. Vue d'ensemble

L’architecture repose sur un pipeline NLP complet permettant d’analyser un texte ou une URL, d’identifier des revendications factuelles, de rechercher des preuves, d’évaluer leur crédibilité puis de fournir une explication lisible.

```
Entrée → Prétraitement → Détection de claims → Extraction entités → Retrieval (ES + FAISS)
→ Vérification (NLI) → Agrégation → Score + Explication → UI
```

---

## 🗂️ 2. Composants principaux

### 🔹 2.1 Frontend (React + TypeScript)

* Dashboard utilisateur
* Formulaire analyse (Texte / URL)
* Affichage du score
* Visualisation des segments suspects (highlights)
* Liste des preuves utilisées
* Système de feedback utilisateur

### 🔹 2.2 API Backend (FastAPI)

* Endpoint /verify
* Endpoint /feedback
* Orchestration du pipeline
* Monitoring et logs anonymisés
* Gestion des modèles

### 🔹 2.3 Pipeline IA (Python + PyTorch)

* Prétraitement (normalisation, segmentation)
* Claim Detection (CamemBERT/T5 finetuné)
* Entity Linking (spaCy + Wikidata)
* Retrieval BM25 (Elasticsearch)
* Retrieval dense (FAISS + SentenceTransformers)
* Modèle NLI (RoBERTa/T5)
* Agrégation (XGBoost / régression logistique)
* Explicabilité (SHAP + extraction textuelle)

### 🔹 2.4 Bases de données

* PostgreSQL : feedback utilisateur + logs anonymisés
* Elasticsearch : index BM25 pour retrieval
* FAISS : index dense vectoriel
* MinIO/S3 : stockage snapshots Wikipedia + modèles IA

---

## 🧩 3. Schéma détaillé (ASCII)

```
┌──────────────────────────┐
│        FRONTEND          │
│  React / TypeScript      │
│  - Formulaire analyse    │
│  - Résultats + preuves   │
└───────────────┬──────────┘
                │ /verify
                ▼
┌───────────────────────────────────────────┐
│               BACKEND API                 │
│               FastAPI                      │
│  - Orchestrateur du pipeline              │
│  - Logging / Sécurité                     │
└───────────────┬───────────────────────────┘
                │
                ▼
┌────────────────────────────────────────────┐
│              PIPELINE IA                   │
│ 1. Prétraitement                           │
│ 2. Claim Detection                         │
│ 3. Entity Linking                          │
│ 4. Retrieval BM25 → Elasticsearch          │
│ 5. Retrieval Dense → FAISS                 │
│ 6. NLI (Support / Contradict / Neutral)    │
│ 7. Agrégation                              │
│ 8. Explicabilité                           │
└───────────────┬────────────────────────────┘
                │
                ▼
┌────────────────────────────────────────────┐
│                  RÉSULTAT                  │
│ Score + preuves + explication              │
└────────────────────────────────────────────┘
```

---

## 🌐 4. Flux de données

1. L’utilisateur envoie un texte ou URL.
2. Le backend extrait le texte.
3. Le pipeline détecte les claims.
4. Chaque claim est associé à des entités connues.
5. Le système interroge Elasticsearch et FAISS.
6. Le modèle NLI compare claim ↔ preuve.
7. Le moteur d’agrégation combine les signaux.
8. Le frontend affiche score + explications.

---

## 🔒 5. Sécurité & RGPD

* Aucun stockage de PII
* Logs anonymisés
* Chiffrement SSL
* Mécanisme d’opt-out
* Versioning des modèles pour auditabilité

---

## 🚀 6. Technologies utilisées

* Python, FastAPI, PyTorch, HuggingFace
* Elasticsearch, FAISS, PostgreSQL
* React, TypeScript, Tailwind
* Docker, GitHub Actions, MinIO/S3

---

## ✔️ 7. Points forts

* Architecture scalable
* Composants découplés
* IA explicable
* Système hybride BM25 + embeddings
* Basé sur des sources fiables et traçables
