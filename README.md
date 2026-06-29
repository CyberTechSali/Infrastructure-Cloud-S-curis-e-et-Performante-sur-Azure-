# azure-secure-cloud-infrastructure
Azure Secure Cloud Infrastructure. Mise en place d'une plateforme cloud complète incluant VPN sécurisé (NetBird/WireGuard), supervision Zabbix, détection de menaces Wazuh, pare-feu FortiGate, SSO Authentik, stockage collaboratif Nextcloud et gestion de tickets Zammad. L'ensemble est interconnecté via un réseau VPN full-mesh sur Azure.

# ☁️ Infrastructure Cloud Sécurisée et Performante sur Microsoft Azure

![Azure](https://img.shields.io/badge/Azure-0078D4?style=for-the-badge&logo=microsoft-azure&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)
![Fortinet](https://img.shields.io/badge/Fortinet-EE3124?style=for-the-badge&logo=fortinet&logoColor=white)

## 📖 Aperçu du Projet

Ce projet, réalisé dans le cadre de mon **Projet de Fin d'Études (PFE)**, consiste à concevoir et déployer une **infrastructure cloud entièrement sécurisée, supervisée et collaborative** sur Microsoft Azure.

L'objectif principal était de construire une plateforme d'entreprise résiliente qui centralise la gestion des identités, garantit la sécurité réseau, assure une supervision en temps réel, détecte les menaces et facilite la collaboration. Le tout en utilisant un mix d'outils open-source et professionnels, interconnectés via un **réseau VPN maillé et sécurisé (NetBird)**.

---

## 🏗️ Architecture et Topologie

Tous les composants sont déployés sur plusieurs machines virtuelles (VM) Azure et connectés via un **VPN full-mesh** basé sur WireGuard (NetBird), assurant une communication chiffrée entre tous les services.

![Topologie](assets/topology.png)

> *La topologie intègre un serveur VPN, la supervision (Zabbix), un SIEM (Wazuh), un pare-feu (FortiGate), le partage de fichiers (Nextcloud), la gestion de tickets (Zammad) et la gestion des identités (Authentik).*

---

## 🛠️ Technologies et Outils Utilisés

| **Catégorie** | **Technologies** |
| :--- | :--- |
| **Plateforme Cloud** | Microsoft Azure (VMs, VNet, NSG, Disques) |
| **Réseau Sécurisé (VPN)** | NetBird (basé sur WireGuard) |
| **Supervision & Observabilité** | Zabbix (avec monitoring SNMP & Agent) |
| **SIEM & Détection des menaces** | Wazuh (Agents + Indexer/Manager) |
| **Pare-feu nouvelle génération** | FortiGate (déployé depuis la Place de marché Azure) |
| **Gestion des identités (IAM)** | Authentik + Zitadel (SSO Open Source) |
| **Collaboration & Stockage** | Nextcloud (avec Docker) |
| **Gestion de tickets & Support** | Zammad (déploiement Docker) |
| **DNS & Proxy de sécurité** | Cloudflare (DNSSEC, Routage email, Reverse Proxy) |
| **Conteneurisation** | Docker & Docker Compose |
| **Systèmes d'exploitation** | Ubuntu 22.04 / Rocky Linux 9 |

---

## ✨ Principales Fonctionnalités Implémentées

- **✅ Accès réseau Zero-Trust** : Configuration du VPN NetBird pour relier de manière sécurisée le serveur VPN, le serveur SIEM, le serveur de supervision et les clients Windows.
- **✅ Supervision centralisée (Zabbix)** : Surveillance de tous les serveurs (Linux/Windows) et du pare-feu FortiGate via SNMP, avec des tableaux de bord personnalisés et des géocartes.
- **✅ Détection des menaces (Wazuh)** : Déploiement d'agents Wazuh sur Linux et Windows pour collecter les logs, détecter les intrusions et surveiller l'intégrité des fichiers.
- **✅ Sécurité périmétrique (FortiGate)** : Installation et configuration d'un pare-feu FortiGate NGFW dans Azure pour filtrer le trafic et protéger le périmètre.
- **✅ Authentification unique (Authentik)** : Mise en place d'une solution IAM open-source pour centraliser l'authentification (OAuth/OpenID).
- **✅ Collaboration métier (Nextcloud + Zammad)** :
  - Nextcloud pour le stockage et le partage de fichiers.
  - Zammad pour la gestion des tickets de support client.
  - Intégration de Nextcloud avec Zammad pour gérer efficacement les pièces jointes.
- **✅ Gestion DNS globale (Cloudflare)** : Gestion des enregistrements DNS, activation de DNSSEC, routage des e-mails et sécurisation de l'accès web via SSL/Let's Encrypt.

---

## 📂 Contenu du Dépôt

Voici la structure de ce dépôt :

- **[`/docs/`](docs/)** : Contient le rapport de projet complet et détaillé (en français).
- **[`/assets/`](assets/)** : Diagrammes d'architecture et captures d'écran des tableaux de bord.
- **[`/scripts/`](scripts/)** : Scripts d'automatisation pour l'installation de Docker, la configuration de NetBird et le déploiement des agents Zabbix.
- **[`/configs/`](configs/)** : Fichiers de référence `docker-compose.yml` pour Nextcloud, Zammad et Authentik.
- **[`/networking/`](networking/)** : Règles des groupes de sécurité réseau (NSG) Azure et configurations des ports utilisés.

---

## 🚀 Résumé du Déploiement (Étapes clés)

1. **Configuration Azure** : Création des groupes de ressources et déploiement des VMs (Ubuntu/Rocky) dans les régions requises.
2. **Maillet VPN** : Installation de NetBird sur tous les serveurs pour établir un réseau privé sécurisé.
3. **Services principaux** : Déploiement des conteneurs Docker pour Zammad, Nextcloud et Authentik sur leurs VMs respectives.
4. **Supervision** : Installation du serveur Zabbix et déploiement des agents sur tous les endpoints. Configuration SNMP sur FortiGate.
5. **Sécurité** : Déploiement de Wazuh (SIEM) et configuration des agents pour envoyer les logs au gestionnaire central.
6. **Pare-feu** : Déploiement de FortiGate depuis la Place de marché Azure, redimensionnement de la VM pour correspondre à la licence d'évaluation, et configuration des politiques de base.
7. **DNS/Proxy** : Pointage du domaine vers Cloudflare, configuration des enregistrements A pour chaque sous-domaine (ex : `vpn.`, `monitoring.`, `ticket.`) et activation de SSL.

---

## 🔮 Améliorations Futures

- Mettre en place un scaling automatique pour la stack de supervision.
- Ajouter un plan de reprise d'activité (PRA) utilisant Azure Backup et Site Recovery.
- Automatiser l'ensemble du provisionnement de l'infrastructure avec **Terraform**.
- Intégrer **TheHive** pour la réponse aux incidents en complément de Wazuh.

---

## 👩‍💻 Auteure

- **Ouchahed Salma** - *IT engineer* - [Profil GitHub](https://github.com/yourusername)

---

## 📝 Licence

Ce projet est réalisé à des fins éducatives et de valorisation de compétences. Les outils utilisés sont soumis à leurs licences open-source ou commerciales respectives.

---
