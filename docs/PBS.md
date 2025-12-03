# PBS.md — Product Breakdown Structure (Markdown)

```
1. Produit : Détecteur de Fake News
   1.1 Interface Utilisateur
        1.1.1 Dashboard Web
        1.1.2 Module d’analyse d’URL / texte
        1.1.3 Visualisation des explications
        1.1.4 Système de feedback utilisateur

   1.2 Backend API
        1.2.1 Endpoint d’analyse (/verify)
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
        1.4.3 Index passage-level (FAISS / Elasticsearch)
        1.4.4 Stockage résultats & feedback (anonymisé)

   1.5 IA & Modèles
        1.5.1 Modèle de claim detection
        1.5.2 Modèle de retrieval dense (embeddings)
        1.5.3 Modèle NLI / entailment
        1.5.4 Modèle d’agrégation (ensemble)
        1.5.5 Explicabilité (SHAP + extraction de passages)

   1.6 Infrastructure
        1.6.1 Serveurs / conteneurs (Docker / Kubernetes optionnel)
        1.6.2 Moteur de recherche (Elasticsearch + FAISS)
        1.6.3 CI/CD & tests
        1.6.4 Sécurité & RGPD

   1.7 Documentation & Conformité
        1.7.1 Documentation technique
        1.7.2 Documentation fonctionnelle
        1.7.3 Charte éthique & RGPD
        1.7.4 Manuel utilisateur
```