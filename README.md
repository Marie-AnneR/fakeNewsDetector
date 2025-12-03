# 📰 Détecteur de Fake News 

## 📌 Description

Le projet vise à développer un système automatisé capable d'analyser un texte ou une URL, détecter les revendications factuelles, rechercher des preuves dans des sources fiables, puis estimer la crédibilité de l'information. Le système fournit un score final, des explications transparentes pour l'utilisateur.

---

## 🎯 Objectifs du projet

* Aider à la vérification d'informations de manière automatique.
* Fournir une analyse explicable et transparente.
* Proposer un outil francophone fiable et accessible.
* Construire un pipeline IA techniquement solide : NLP, retrieval, NLI, explicabilité.
* Développer un projet complet mobilisant IA, backend, frontend, DevOps et data engineering.

---

# 📦 PBS — Product Breakdown Structure

```
1. Produit : Détecteur de Fake News
   1.1 Interface Utilisateur
        1.1.1 Dashboard Web
        1.1.2 Module d’analyse d’URL / texte
        1.1.3 Visualisation des explications
        1.1.4 Système de feedback utilisateur

   1.2 Backend API
        1.2.1 Endpoint d’analyse
        1.2.2 Endpoint de feedback
        1.2.3 Logs & Monitoring
        1.2.4 Gestion des modèles IA (versioning)

   1.3 Pipeline de Traitement
        1.3.1 Prétraitement du texte
        1.3.2 Détection des revendications (Claim Detector)
        1.3.3 Extraction d’entités (NER + Linking)
        1.3.4 Recherche de preuves (Retrieval Engine)
        1.3.5 Vérification des faits (NLI / Entailment)
        1.3.6 Estimation de fiabilité de la source
        1.3.7 Agrégation & scoring final

   1.4 Bases de Données
        1.4.1 Base Wikipedia localisée (snapshot)
        1.4.2 Base fact-checking
        1.4.3 Index passage-level (FAISS / ES)
        1.4.4 Stockage résultats & feedback (anonymisé)

   1.5 IA & Modèles
        1.5.1 Modèle de claim detection
        1.5.2 Modèle de retrieval dense (embeddings)
        1.5.3 Modèle NLI / entailment
        1.5.4 Modèle d’agrégation (ensemble)
        1.5.5 Explicabilité (SHAP + extraction de passages)

   1.6 Infrastructure
        1.6.1 Serveurs / conteneurs (Docker + Kubernetes optionnel)
        1.6.2 Moteur de recherche (Elasticsearch + FAISS)
        1.6.3 CI/CD & tests
        1.6.4 Sécurité & RGPD

   1.7 Documentation & Conformité
        1.7.1 Documentation technique
        1.7.2 Documentation fonctionnelle
        1.7.3 Charte éthique & RGPD
        1.7.4 Manuel utilisateur
```

---

# 🛠️ WBS — Work Breakdown Structure

## **Phase A — Analyse & Spécification**

```
A1. Analyse du besoin
A2. Recherche datasets & licences
A3. Spécifications fonctionnelles
A4. Architecture préliminaire
A5. Plan RGPD & éthique
A6. Finalisation PBS & WBS
```

## **Phase B — Conception & Setup**

```
B1. Maquettes UI/UX
B2. Setup environnement (Docker, CI/CD)
B3. Indexation Wikipedia
B4. Définition schéma DB
B5. Plan des tests
```

## **Phase C — Prototypage IA**

```
C1. Préparation datasets
C2. Détection de claims
C3. Retrieval BM25 + FAISS
C4. Modèle NLI
C5. Agrégation initiale
C6. Explication basique
C7. Tests IA
```

## **Phase D — Backend & API**

```
D1. API /verify
D2. Model serving
D3. Versioning modèles
D4. Logging & monitoring
D5. Sécurité API
```

## **Phase E — Frontend**

```
E1. Dashboard utilisateur
E2. Affichage des highlights
E3. Visualisation des preuves
E4. Feedback utilisateur
E5. Tests UI
```

## **Phase F — Intégration & Validation**

```
F1. Intégration pipeline complet
F2. Tests adversariaux
F3. Évaluation humaine
F4. Optimisation performances
F5. Documentation
F6. Préparation pitch
```

---

# 🧱 Architecture générale

```
Texte/URL → Prétraitement → Détection des revendications → Retrieval (ES + FAISS) → Modèle NLI
→ Agrégation → Score de crédibilité → Explications
```

---

# 🧪 Stack technique proposée

* **Backend :** Python, FastAPI, Docker
* **IA / NLP :** PyTorch, HuggingFace, CamemBERT/XLM-R, SentenceTransformers
* **Recherche de preuves :** Elasticsearch, FAISS
* **Frontend :** React + TypeScript
* **Base de données :** PostgreSQL
* **DevOps :** GitHub Actions, MinIO/S3, monitoring Prometheus/Grafana

---

# 🔒 RGPD & Éthique

* Aucun stockage de données personnelles de l'utilisateur
* Anonymisation systématique des logs
* Transparence du modèle et de ses limites
* Charte éthique intégrée au projet

---

# 🚀 Roadmap

* **S7 :** Spécifications + PBS/WBS + présentation
* **S8 :** Index Wikipedia + prototype IA (claims + retrieval)
* **S9 :** API /verify, NLI, UI v1
* **S10 :** Robustesse, test humain, optimisation, présentation finale

---

# 🧩 Équipe recherchée

* 2 IA / NLP
* 2 Backend
* 1 Frontend
* 1 DevOps
* 1 Data Engineer / QA

---

# 🏷️ Tags

`#IA #MachineLearning #FakeNews #FactChecking #NLP #DeepLearning #Cyber #ExplainableAI #OpenData #Python`

---

