
---

## ⚛️ **Kit de Migration Post-Quantum Cryptography (PQC)**

### 🔐 *"Détecter les algorithmes cryptographiques vulnérables et recommander leur migration vers des alternatives post-quantiques."*

---

## 🧠 **Résumé du projet**

Les ordinateurs quantiques menacent les algorithmes cryptographiques classiques comme **RSA**, **DSA**, **ECDSA**, etc.
Ce projet vise à :

* Scanner les systèmes ou logiciels pour identifier ces algorithmes vulnérables.
* Recommander automatiquement des alternatives **post-quantiques** (Kyber, Dilithium, etc.).
* Générer un **plan de migration cryptographique** clair pour l’entreprise ou l’utilisateur.

---

## 🎯 **Objectifs pédagogiques**

* Appliquer des connaissances en **cryptographie appliquée**.
* Comprendre les enjeux de la **transition post-quantique**.
* Développer un outil semi-automatique de **diagnostic + recommandation**.
* Simuler ou prototyper une **intégration TLS/SSH hybride** (ex. Kyber + AES).

---

## 🧰 **Stack technique recommandée**

| Technologie            | Usage                                                            |
| ---------------------- | ---------------------------------------------------------------- |
| **Python 3.10+**       | Langage principal (analyse, parsing, automatisation)             |
| **OpenSSL**            | Pour scanner les certificats X.509, TLS, SSH                     |
| **Wireshark**          | Pour analyser les sessions réseau et détecter les ciphers        |
| **liboqs**             | Librairie open-source de crypto PQC (Kyber, Dilithium, etc.)     |
| **CLI / GUI**          | Streamlit, Tkinter, ou ligne de commande Python                  |
| **JSON/YAML**          | Pour les templates de recommandations ou rapports                |
| **Docker (optionnel)** | Pour créer des environnements hybrides avec TLS PQC expérimental |

---

## 📂 **Livrables attendus**

* Un **outil de diagnostic CLI ou GUI** (ex: `python scan_crypto.py`)
* Un **rapport automatique** (niveau de risque, vulnérabilités, recommandations)
* Un simulateur ou démo de **migration TLS ou SSH**
* Documentation claire + vidéo de démo (optionnel)

---

## 🔍 **Fonctionnalités principales**

### 1. **Détection cryptographique**

* Scanner les fichiers `.crt`, `.pem`, `.key`
* Scanner les ports 443, 22… via **OpenSSL + sockets**
* Lire le type de certificat ou d’algorithme : RSA, ECDSA, SHA1, etc.

### 2. **Évaluation du risque (score)**

* Attribuer une **note de sécurité** : fort / modéré / vulnérable
* Définir un **indice de priorité de migration** basé sur :

  * Longueur des clés
  * Algorithme (ex: RSA-2048 = modéré, ECC-P256 = risqué)
  * Type de service (VPN, Web, SSH)

### 3. **Recommandation PQC**

* Exemple :
  RSA → Kyber
  ECDSA → Dilithium
  ECC → Falcon
* Proposer une version hybride : RSA + Kyber pour transition douce

### 4. **Plan de migration**

* Générer un fichier `.md` ou `.pdf` contenant :

  * Liste des actifs vulnérables
  * Algorithmes alternatifs
  * Actions à entreprendre
  * Outils nécessaires (liboqs, OpenSSL patched…)

---

## 🗺️ **Architecture simplifiée**

```
[Fichiers .crt / .key / TLS / SSH] ──▶ [🧠 Scanner Python]
                                           │
                                           ▼
                             [📋 Rapport JSON + Reco PQC]
                                           │
                                           ▼
                            [📊 Interface Streamlit ou Rapport PDF]
```

---

## 🛠️ **Exemple de modules Python**

* `crypto_scanner.py` → identifie RSA, ECC, etc.
* `pqc_recommender.py` → suggère un remplacement
* `report_generator.py` → compile le plan de migration
* `tls_checker.py` → scanne un domaine en TLS et affiche les ciphers

---

## 🛡️ **Exemple d’algorithmes à recommander**

| Algo classique | Menace quantique | Algo PQC recommandé |
| -------------- | ---------------- | ------------------- |
| RSA 2048       | ❌ cassable       | Kyber512            |
| ECC P-256      | ❌ cassable       | Dilithium2          |
| DSA            | ❌ cassable       | Falcon              |
| SHA-1          | ❌ collision      | SHA-3, BLAKE2       |

---

## 📊 **Interface utilisateur possible**

Avec **Streamlit** :

* Bouton pour “Scanner un fichier”
* Affichage en couleur du **niveau de vulnérabilité**
* Graphique radar ou histogramme des risques
* Bouton “Générer rapport PDF”
* Option : affichage d’un log de migration

---

## 📆 **Plan de travail (8 semaines)**

| Semaine | Tâches principales                                  |
| ------- | --------------------------------------------------- |
| 1       | Étude PQC + installation outils + crypto classique  |
| 2       | Création scanner Python (OpenSSL, fichier clé/cert) |
| 3       | Ajout analyse réseau avec Wireshark / TLS checker   |
| 4       | Génération scoring + mapping PQC                    |
| 5       | Générateur de plan de migration (.md / .pdf)        |
| 6       | Streamlit dashboard (facultatif)                    |
| 7       | Tests + cas réels (avec de vrais certificats)       |
| 8       | Rendu final + rapport + soutenance                  |

---

## 🧠 **Difficultés possibles**

| Risque                           | Solution                                                              |
| -------------------------------- | --------------------------------------------------------------------- |
| Manque de certificats à analyser | Utilise ton propre `localhost`, ou des sites en ligne (`ssllabs.com`) |
| Conflits de versions OpenSSL     | Créer environnement virtuel Python ou container Docker                |
| Difficulté à comprendre PQC      | Utiliser les ressources NIST + vidéos explicatives                    |

---

## 🚀 **Extensions possibles**

* Intégrer avec Shodan pour scanner des IP externes
* Ajouter un module d’**auto-migration TLS Apache ou Nginx**
* Créer un **plugin pour VS Code** ou une webapp déployable

---

## ✅ **Faisabilité sur PC **

**Oui à 100% !** Aucun composant lourd :

* OpenSSL, Python, Wireshark = légers
* Tu peux simuler tout sans machine virtuelle
* Option Docker pour faire tourner une version TLS avec Kyber (facultatif)

---

## 🧩 En résumé :

| Élément              | Statut                                            |
| -------------------- | ------------------------------------------------- |
| Faisable localement  | ✅                                                 |
| Originalité          | ✅✅✅                                               |
| Niveau technique     | Moyen/avancé                                      |
| Impact réel          | 🔥🔥🔥                                            |
| Opportunité carrière | Très forte (crypto, quantique, audit, compliance) |

---

