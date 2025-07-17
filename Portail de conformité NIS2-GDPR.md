
---

## 🧾 **Portail de Conformité NIS2 / GDPR**  
### 📊 *"Plateforme pour simuler, visualiser et automatiser l’évaluation de conformité cyber selon les nouvelles réglementations européennes."*

---

## 🧠 **Résumé du projet**
La directive **NIS2** (UE) et le **RGPD** imposent aux entreprises, même PME, de démontrer leur conformité en matière de sécurité et de gestion des données.  
Ce projet vise à créer un **dashboard web interactif** où une entreprise fictive :
- évalue son **niveau de conformité** (questionnaire, analyse de risques),
- reçoit des **recommandations automatiques**,
- télécharge des **rapports PDF légaux ou techniques**.

---

## 🎯 **Objectifs pédagogiques**
- Comprendre les grandes obligations de la directive NIS2 et du RGPD.
- Simuler un **audit automatique** de conformité.
- Visualiser les résultats dans un tableau de bord UX-friendly.
- Générer des **rapports exploitables (PDF, CSV)**.
- (Bonus) Ajouter un système de suivi d'incidents de sécurité (Journal SOC).

---

## 🧰 **Stack technique recommandée**

| Composant              | Rôle                                                                 |
|------------------------|----------------------------------------------------------------------|
| **Backend**             | Laravel, Flask ou Django pour logique + API                          |
| **Base de données**     | SQLite (léger), MySQL ou PostgreSQL                                  |
| **Frontend**            | HTML/CSS + Bootstrap ou React + Tailwind                             |
| **Charting**            | Chart.js, ApexCharts, D3.js pour jauges de conformité                |
| **Export**              | WeasyPrint / ReportLab (Python) ou DomPDF (Laravel)                  |
| **Auth** (optionnel)    | Auth simple par e-mail ou clé API                                    |

---

## 📂 **Livrables attendus**
- 🖥️ Un **portail web fonctionnel** avec formulaire de diagnostic
- 📊 Un **tableau de bord dynamique**
- 📄 Générateur de **rapports PDF/CSV**
- 🛡️ Liste des recommandations de sécurité + plan d’action
- 📚 Documentation technique + vidéo de démo (optionnel)

---

## 🔍 **Fonctionnalités proposées**

### 🟢 1. **Audit simplifié de conformité**
- Questionnaire : 20–40 questions (sécurité réseau, incident, backup, formation…)
- Chaque question associée à :
  - un **article NIS2/RGPD**
  - un **niveau de criticité**
  - un **score**

---

### 🔵 2. **Tableau de bord interactif**
- Jauge de conformité globale (%)
- Graphiques par domaine : sécurité, vie privée, gestion des risques…
- Statut : conforme / partiellement / non conforme

---

### 🔴 3. **Rapports générés automatiquement**
- Format : PDF ou JSON/CSV
- Contenu : score global, résumé des faiblesses, plan d’action proposé
- Signature ou timestamp (optionnel)

---

### 🟠 4. **Recommandations automatiques**
- Exemple : “Pas de politique de backup ? → implémenter backup 3-2-1”
- Mapping vers des frameworks (ISO 27001, ANSSI SecNumCloud…)

---

### 🟣 5. **Journal de conformité (bonus)**
- Historique des changements : amélioration ou régression
- Système d’alertes : “depuis 30j, aucun test de phishing réalisé”

---

## 🗺️ **Architecture technique simplifiée**

```
[🌐 Interface Web]
      │
      ▼
[📋 Questionnaire dynamique] ─▶ [📊 Dashboard + 🧠 Score Engine]
      │                                    │
      ▼                                    ▼
 [📝 Recommandations]            [📄 Rapport PDF + Export CSV]
```

---

## 🧠 **Exemples de questions NIS2/GDPR**

| Domaine             | Exemple de question                                                | Score si manquant |
|---------------------|--------------------------------------------------------------------|--------------------|
| Incidents           | Avez-vous une procédure formelle de réponse aux incidents ?        | -20                |
| Données personnelles| Collectez-vous uniquement les données strictement nécessaires ?    | -15                |
| Journalisation      | Conservez-vous les logs pendant 12 mois minimum ?                  | -10                |
| Formation           | Vos employés reçoivent-ils une formation annuelle en cybersécurité ?| -20               |

---

## 📆 **Plan de travail (8 semaines)**

| Semaine | Tâches principales                                         |
|--------|-------------------------------------------------------------|
| 1      | Étude NIS2 + RGPD (exigences clés)                         |
| 2      | Maquettage frontend (formulaires, dashboard)               |
| 3      | Backend + base de données                                   |
| 4      | Intégration scoring automatisé                              |
| 5      | Recommandations automatiques                                |
| 6      | Génération PDF / CSV                                        |
| 7      | Ajout d’un journal ou système d’alertes                     |
| 8      | Finalisation, rapport, test utilisateur fictif              |

---

## 🛡️ **Difficultés possibles & solutions**

| Problème                             | Solution proposée                                                       |
|-------------------------------------|--------------------------------------------------------------------------|
| Interprétation des textes NIS2/GDPR | Utilise les **résumés officiels simplifiés + guides ANSSI**              |
| Génération PDF                      | Utilise **WeasyPrint** ou **DomPDF** (rapide et bien documenté)          |
| Évaluation UX                       | S’inspirer de sites comme **Dribbble**, **Canva Admin**, ou **Notion**   |

---

## ✅ **Faisabilité sur PC **
**Oui, à 100 %**
- Laravel/Flask/Django tournent très bien localement.
- Base de données légère (SQLite)
- Pas besoin de VM ni de services cloud
- Tu peux héberger la démo localement avec `php artisan serve` ou `python app.py`

---

## 🚀 **Extensions possibles**
- Ajouter **authentification Admin + Employé**
- Connecter à un **SIEM (Wazuh)** pour journaliser des incidents réels
- Déployer sur un Raspberry Pi ou hébergement gratuit (ex : Vercel/Netlify + backend Render)
- Version entreprise multi-utilisateurs (bonus)

---

## 📌 **Résumé rapide**

| Élément              | Détail                            |
|----------------------|------------------------------------|
| Originalité          | Moyenne (mais très professionnel) |
| Intérêt métier       | Très élevé (compliance = 🔥)       |
| Complexité           | Moyenne                           |
| Faisable localement  | ✅ 100 %                           |
| Orientation carrière | GRC, cybersécurité légale, audit  |

---