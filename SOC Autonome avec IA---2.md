 
---

## 🧠 **Titre PFA : Optimisation d’un SOC Autonome par intégration de Nmap et d’Intelligence Artificielle dans Wazuh**

---

### 🎯 **Résumé du projet**

Ce projet vise à **développer un mini-SOC intelligent**, capable de :

* **scanner automatiquement** un réseau interne à l’aide de **Nmap**,
* **collecter et corréler les logs** via **Wazuh SIEM**,
* **analyser les vulnérabilités détectées** à l’aide de modèles d’IA (Scikit-learn, PyCaret…),
* **générer des alertes, des scores de risque**, et proposer une **réponse automatisée** (alerte mail, blocage, ticket…).

💡 **Objectif final** : démontrer qu’un **SOC local**, même simple, peut être rendu **plus intelligent, autonome et réactif** grâce à l’IA.

---

### 🧩 **Architecture technique globale**

```
[🌐 Réseau local (VMs ou IPs réelles)]
          │
          ▼
[🔍 Nmap (Scan Automatisé)]
          │
          ▼
[🧠 IA Python (Analyse + Scoring des Vulnérabilités)]
          │
          ▼
[📦 Wazuh SIEM (Indexation + Corrélation)]
          │
          ▼
[📊 Dashboard (Kibana / Wazuh UI) + Réponse auto]
```

---

### 🛠️ **Stack Technique utilisée**

| Composant             | Usage                                                          |
| --------------------- | -------------------------------------------------------------- |
| **Wazuh**             | SIEM pour collecte, détection, corrélation                     |
| **Nmap**              | Scanner réseau & vulnérabilités                                |
| **Python**            | Analyse automatique avec IA (scikit-learn, pandas, seaborn...) |
| **ELK**               | Visualisation des logs & dashboards personnalisés              |
| **PyCaret / Sklearn** | IA low-code pour scoring et détection d’anomalies              |
| **Docker**            | Déploiement modulaire (Wazuh, Nmap Runner, etc.)               |
| **Streamlit** (opt.)  | Interface secondaire pour visualiser les vulnérabilités        |

---

### ⚙️ **Modules fonctionnels à implémenter**

| Module                            | Description                                                          |
| --------------------------------- | -------------------------------------------------------------------- |
| 🔍 **Scanner réseau automatique** | Exécuter régulièrement des scans avec Nmap (CRON ou script Python)   |
| 🧠 **Analyse IA (offline)**       | Classification, regroupement, scoring des failles détectées          |
| 🧩 **Intégration Wazuh**          | Envoi des résultats enrichis dans Wazuh via les logs personnalisés   |
| 📊 **Dashboard SOC**              | Visualiser le statut des vulnérabilités par hôte, segment, criticité |
| 🛑 **Réponse automatisée**        | Exemple : si criticité élevée → alerte e-mail ou blocage temporaire  |

---

### 📊 **Exemples de fonctionnalités**

| Action déclenchée                                        | Résultat attendu                                       |
| -------------------------------------------------------- | ------------------------------------------------------ |
| Scan détecte port ouvert SSH avec vulnérabilité critique | ⚠️ Alerte + Score de risque élevé dans Wazuh           |
| Modèle IA repère comportement anormal                    | 🚨 Génération d’une alerte + envoi par e-mail          |
| Machine avec trop de vulnérabilités                      | 🔒 IP marquée comme isolée (simulation pare-feu)       |
| Score global du réseau augmente                          | 📈 Affichage sur dashboard + recommandation corrective |

---

### 🧠 **Modules IA possibles**

| Module IA               | Objectif                                                         |
| ----------------------- | ---------------------------------------------------------------- |
| Clustering (KMeans)     | Grouper les hôtes par comportement de scan                       |
| Isolation Forest        | Détection d’anomalies dans les logs d’activité réseau            |
| CVSS-based Risk Scoring | Calcul automatique du risque à partir des CVE détectées par Nmap |
| TF-IDF CVE Processing   | Résumer les descriptions des vulnérabilités                      |
| AutoML (PyCaret)        | Tester plusieurs modèles de prédiction sur un dataset de logs    |

---

### 📁 **Livrables attendus**

* ✅ Script de scan automatisé + parsing
* ✅ Système d’analyse IA avec enrichissement
* ✅ Intégration dans Wazuh / ELK
* ✅ Interface de visualisation (Wazuh Dashboard + Streamlit/HTML)
* ✅ Rapport technique structuré (architecture, modules, tests)
* ✅ Démo vidéo ou soutenance avec cas d’attaque simulée

---

### 📆 **Plan de travail (8 semaines)**

| Semaine | Tâches clés                                                             |
| ------- | ----------------------------------------------------------------------- |
| 1       | Étude Wazuh, Nmap, définition des besoins                               |
| 2       | Setup Wazuh local + ELK Stack (via Docker)                              |
| 3       | Script de scan automatique avec Nmap + parsing XML/JSON                 |
| 4       | Développement du module IA d’analyse (scoring, clustering, anomalie)    |
| 5       | Intégration des résultats dans Wazuh (logs personnalisés ou JSON input) |
| 6       | Dashboard + visualisation dans Kibana / Streamlit                       |
| 7       | Tests sur machines virtuelles + réponse automatique simulée             |
| 8       | Rapport, soutenance, extension possible (OpenVAS, honeypot, etc.)       |

---

### ✅ **Faisabilité sur ton PC**

| Ressource        | OK ?                                      |
| ---------------- | ----------------------------------------- |
| Wazuh via Docker | ✅ Oui, tourne très bien en local          |
| Python + Scikit  | ✅ Oui, très léger                         |
| Nmap             | ✅ Oui, déjà disponible sous Linux/Windows |
| RAM recommandée  | 8 Go minimum pour fluidité                |
| CPU              | Pas besoin de GPU ou de gros calculs      |
| Virtualisation   | VM ou Docker ≈ très pratique              |

---

### 🚀 **Extensions possibles (pour bonus ou version PFA++)**

* Intégration **OpenVAS** pour scanner plus riche que Nmap
* Utilisation de **MISP ou OTX** pour enrichir les alertes (threat intel)
* Simulation d’un honeypot (cowrie) pour générer des logs réels
* Génération d’un **rapport automatique PDF** chaque semaine

---

### 📌 **Résumé stratégique**

| Critère               | Évaluation                         |
| --------------------- | ---------------------------------- |
| Originalité           | 🔥 Très bonne (SOC + IA + scanner) |
| Faisabilité locale    | ✅ 100%                             |
| Pertinence académique | ✅ Conformité, sécurité, IA         |
| Matériel requis       | PC normal, Docker                  |
| Outils à maîtriser    | Python, Wazuh, Nmap, IA            |

---

 