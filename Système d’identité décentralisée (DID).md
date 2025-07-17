
---

## 🪪 **Système d’Identité Décentralisée (DID)**

### 🔐 *"Implémenter une identité auto-souveraine avec vérification de CV ou diplôme, sans dépendre d'un fournisseur central."*

---

## 🧠 **Résumé du projet**

L’identité décentralisée (DID, ou Self-Sovereign Identity - SSI) est une nouvelle approche qui permet à un utilisateur :

* de **créer et posséder son identité numérique** (wallet),
* de **recevoir des preuves vérifiables** (diplômes, certificats, CV),
* de **les présenter à des tiers**, sans passer par Google/Facebook ou des registres centralisés.

---

## 🎯 **Objectifs pédagogiques**

* Comprendre les standards DID / Verifiable Credentials (VC) du W3C
* Implémenter un cycle : **création DID → émission VC → vérification VC**
* Simuler une plateforme de gestion d’identité (profil, preuve, validation)
* Utiliser une **blockchain légère ou un registre distribué** (Ethereum testnet, Hyperledger)

---

## 🧰 **Stack technique recommandée**

| Composant                            | Usage                                                         |
| ------------------------------------ | ------------------------------------------------------------- |
| **SpruceID** ou **Hyperledger Indy** | Librairies pour DID / VC (prêtes à l’emploi)                  |
| **React.js**                         | Frontend utilisateur (création de portefeuille, réception VC) |
| **Node.js / Express**                | Backend d’émission de crédentiels                             |
| **MetaMask**                         | Wallet décentralisé (pour signer les DIDs)                    |
| **Ganache / Hardhat**                | Blockchain locale (Ethereum, testnet, sans coût)              |
| **IPFS** (optionnel)                 | Stockage décentralisé des métadonnées (VC)                    |

---

## 📂 **Livrables attendus**

* Frontend fonctionnel pour :

  * Créer une identité décentralisée (DID)
  * Générer / recevoir un **Verifiable Credential (VC)**
  * Partager et faire vérifier ce VC par un tiers
* Backend d’émission ou vérification des crédentiels
* Rapport technique expliquant l’architecture, les composants, la sécurité

---

## 🗺️ **Cycle DID / VC expliqué**

```
[🧑 Utilisateur] ─▶ [Wallet (DID)] ──recevoir──▶ [🔐 Preuve : diplôme/expérience]

                 └──présente VC──▶ [👩‍💼 Vérificateur : recruteur/école]

                             └──valide la signature / source sur blockchain
```

---

## 🔍 **Exemple d’usage concret**

* Une école délivre un **VC "Diplôme"** signé numériquement à l’étudiant.
* L’étudiant le conserve dans son **wallet** (MetaMask, Spruce, Indy).
* Il postule chez une entreprise, qui **vérifie la preuve** sans contacter l’école.
* Aucune base de données centrale = respect de la vie privée.

---

## 🔐 **Standards à respecter**

| Standard                       | Description                                        |
| ------------------------------ | -------------------------------------------------- |
| **DID**                        | Identifiant unique (ex : `did:ethr:0xABC...`)      |
| **Verifiable Credential (VC)** | JSON signé contenant une preuve (ex : diplôme)     |
| **DID Document**               | Document JSON décrivant le DID et ses clés         |
| **DID Resolver**               | Outil pour récupérer un DID Document depuis un DID |

---

## 🛠️ **Modules du projet**

| Module                      | Fonction                                                    |
| --------------------------- | ----------------------------------------------------------- |
| `wallet.js`                 | Gérer les DIDs dans le navigateur (création, signature)     |
| `issuer.js`                 | API d’émission de VC (backend signé)                        |
| `verifier.js`               | API ou outil pour vérifier un VC reçu                       |
| `blockchain.js` (optionnel) | Interagir avec Ganache pour stocker un hash de la preuve    |
| `ui.jsx`                    | Interface React : voir ses preuves, en générer, en partager |

---

## 📊 **Maquette UI (exemple Streamlit ou React)**

* 👤 Page “Mon identité” : voir ton DID, clés, infos
* 📄 Page “Mes preuves” : liste de tes diplômes, expériences
* ➕ Page “Recevoir une preuve” : QR code, lien, etc.
* ✅ Page “Vérifier une preuve” : bouton “Vérifier” et résultat (validé/échec)

---

## 📆 **Plan de travail (8 semaines)**

| Semaine | Tâches principales                              |
| ------- | ----------------------------------------------- |
| 1       | Étude des standards (DID, VC, W3C)              |
| 2       | Choix de la stack : SpruceID, Indy, ou Ethereum |
| 3       | Mise en place Ganache / MetaMask / backend      |
| 4       | Implémentation émission de credential           |
| 5       | Implémentation vérification + interface DID     |
| 6       | Intégration frontend (React ou simple HTML/JS)  |
| 7       | Tests + génération de fausses preuves           |
| 8       | Rapport, soutenance, démonstration              |

---

## 🛡️ **Difficultés possibles**

| Problème                          | Solution proposée                                                  |
| --------------------------------- | ------------------------------------------------------------------ |
| Compréhension des specs W3C       | Utiliser les SDK prêts : SpruceID / Indy / DIDKit                  |
| Déploiement blockchain            | Utiliser **Ganache** local (aucun gas) ou Polygon Mumbai testnet   |
| Complexité des clés et signatures | Utiliser des bibliothèques abstraites type **DID-JS** ou **VC-JS** |

---

## ✅ **Faisabilité sur PC 2**

**Oui, 100% faisable localement** :

* Tu n’as pas besoin de node complet → **Ganache (lightchain)**
* Utilisation de **MetaMask** dans le navigateur = facile
* Toute la logique est en **JavaScript/Python** = léger
* Pas besoin de GPU ou VM lourde

---

## 🚀 **Extensions possibles**

* Créer une **preuve de compétence technique** (CV validé)
* Ajouter **WebAuthn ou signature biométrique** dans le wallet
* Créer une **passerelle pour université ou RH**
* Stocker les VC sur **IPFS** pour plus de décentralisation

---

## 📌 **Résumé**

| Élément             | Statut                        |
| ------------------- | ----------------------------- |
| Originalité         | ✅✅✅                           |
| Innovation          | 🔥 Très forte (Web3, SSI)     |
| Sécurité            | Forte (signatures numériques) |
| Complexité          | Moyenne (bonne doc + libs)    |
| Réalisable chez toi | ✅ Oui à 100%                  |

---
