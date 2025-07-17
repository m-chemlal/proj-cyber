 ---

## 🛡️ **Simulateur de Zero Trust Architecture (ZTA)**

### 🏗️ *"Modéliser une mini-infrastructure réseau Zero Trust avec microsegmentation, contrôle d’accès contextuel et surveillance temps réel."*

---

## 🧠 **Résumé du projet**

Le **Zero Trust Network Architecture (ZTNA)** repose sur un principe fort :

> “Ne jamais faire confiance, toujours vérifier.”
> Même à l’intérieur du réseau de l’entreprise, **aucun utilisateur, appareil ou service n’est fiable par défaut**.

L’objectif du projet est de **simuler une infrastructure de type Zero Trust** dans un environnement local ou virtualisé, avec vérification des identités, segmentation réseau, accès par rôles, et surveillance des comportements.

---

## 🎯 **Objectifs pédagogiques**

* Comprendre les **6 piliers du Zero Trust** : Identité, Appareils, Réseau, Applications, Données, Analyse
* Déployer une **mini-architecture réseau segmentée**
* Appliquer les **contrôles de sécurité dynamiques** (MFA, RBAC, détection comportementale)
* Visualiser les accès, les journaux et les incidents via un dashboard ou un SIEM

---

## 🧰 **Stack technique recommandée**

| Composant                   | Rôle                                                    |
| --------------------------- | ------------------------------------------------------- |
| **VMs VirtualBox**          | Créer un mini-lab réseau local (serveur, client, admin) |
| **Ubuntu/Debian**           | Systèmes légers pour simuler clients/serveurs           |
| **Keycloak / Authelia**     | Fournisseur d’identité avec support MFA, RBAC           |
| **nginx / HAProxy**         | Proxy avec règles d’accès basées sur l’identité         |
| **Wireguard**               | Microsegmentation + tunnels chiffrés                    |
| **Open Policy Agent (OPA)** | Moteur de politique Zero Trust côté accès               |
| **Wireshark + UFW**         | Contrôle + visualisation du trafic réseau               |
| **Grafana + Loki / ELK**    | SIEM léger pour centraliser et visualiser les logs      |

---

## 🔑 **Ce que tu vas simuler (Architecture)**

```bash
+----------------+       +---------------+       +-----------------+
| Poste employé  | <---> | Proxy ZeroTrust| <--->| App web interne |
| (VM 1)         |       | (RBAC/MFA)     |       | (VM 2)          |
+----------------+       +---------------+       +-----------------+
        |                           |
        ▼                           ▼
      MFA                   Audit + Logs + Alertes
                        (Grafana / OPA / Logs API)
```

---

## 🟦 **Les 6 piliers du Zero Trust appliqués**

| Pilier           | Implémentation dans le projet                                                  |
| ---------------- | ------------------------------------------------------------------------------ |
| **Identité**     | Authentification avec Keycloak ou Authelia + MFA + RBAC                        |
| **Appareils**    | Utiliser UFW ou script de validation (ex : check version OS, ports, antivirus) |
| **Réseau**       | Microsegmentation via Wireguard ou VLAN, plus règles pare-feu strictes         |
| **Applications** | Contrôle d’accès par rôle/contextes via nginx + reverse proxy sécurisé         |
| **Données**      | Séparation des données sensibles + chiffrage + journalisation des accès        |
| **Analyse**      | Logs centralisés via Loki / ELK + visualisation Grafana + alertes              |

---

## 📂 **Livrables attendus**

* 🧪 Un lab Zero Trust simulé (VM ou réseau Docker)
* 🎯 Un dashboard montrant les accès autorisés/refusés
* 🔐 Un exemple d’accès par rôle : `admin`, `RH`, `finance`
* 🛡️ Des journaux d’activité réseau et authentification
* 📘 Rapport d’architecture et plan d’extension vers cloud

---

## 🔧 **Exemples de scénarios à tester**

* ✅ Authentification réussie via MFA → accès autorisé
* ❌ Authentification échouée → blocage total + alerte
* ⚠️ Tentative d’accès à une app interdite selon le rôle → refus + log
* 🚫 Appareil non conforme (test via script) → refus d’accès réseau
* ⏱️ Tentative d’accès à 4h du matin → rejet basé sur contexte horaire

---

## 📊 **Dashboard à inclure**

* 📈 Accès par utilisateur (graphique par heure)
* 🚦 Tentatives d’accès refusées (alarme rouge)
* 🧭 Comportement anormal (via règles heuristiques simples ou OPA)
* 📄 Logs de sessions + logs nginx/wireguard

---

## 🛠️ **Techniques clés à implémenter**

* Reverse proxy avec authentification contextuelle
* Script de validation “device posture” (check antivirus, OS, etc.)
* Politique RBAC/ABAC simple via Keycloak ou fichiers JSON
* Microsegmentation réseau (iptables + Wireguard)
* Monitoring via Promtail → Loki → Grafana

---

## 📆 **Plan de travail proposé (8 semaines)**

| Semaine | Tâches principales                                 |
| ------- | -------------------------------------------------- |
| 1       | Étude de Zero Trust + plan d’architecture          |
| 2       | Mise en place des VMs ou conteneurs Docker         |
| 3       | Déploiement d’un IdP (Keycloak/Authelia) + MFA     |
| 4       | Configuration proxy + segmentation réseau          |
| 5       | Implémentation des règles d’accès RBAC/ABAC        |
| 6       | Collecte et visualisation des logs (Grafana / ELK) |
| 7       | Scénarios de test (refus, alerte, MFA…)            |
| 8       | Rapport final + soutenance                         |

---

## ✅ **Faisabilité sur PC **

| Élément        | Détail                                     |
| -------------- | ------------------------------------------ |
| VMs            | ✅ 2–3 petites VMs suffisent (1 Go RAM max) |
| Docker         | ✅ Tu peux tout faire avec Docker Compose   |
| RAM            | 6 Go ou plus recommandé                    |
| GPU / CPU      | Pas nécessaire                             |
| Accès Internet | Optionnel (tout en local possible)         |

---

## 🚀 **Extensions possibles**

* Intégration d’**Azure AD ou LDAP** comme IdP externe
* Scénarios de **privilege escalation** ou **lateral movement**
* Ajouter une **API Gateway + JWT + OPA**
* Intégration Cloud (AWS IAM ou GCP BeyondCorp)

---

## 📌 **Résumé stratégique**

| Élément            | Statut                     |
| ------------------ | -------------------------- |
| Originalité        | 🔥 Très forte (Zero Trust) |
| Valeur carrière    | ✅ Très demandée            |
| Difficulté         | Moyenne                    |
| Matériel requis    | PC normal, pas de GPU      |
| Outils à apprendre | Réseaux, auth, logs, SIEM  |

---

