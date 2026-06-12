# 🛡️ Analyse de risques EBIOS RM — Société BIOÉNERGIE TECH

> **M2 Cybersécurité · Ecole 2600 · Gestion des risques & Cyberdefense**  
> Analyse de risques complète selon la méthode EBIOS Risk Manager sur un site industriel critique combinant systèmes IT et OT.

[![EBIOS RM](https://img.shields.io/badge/Méthode-EBIOS%20RM-E63946?style=flat-square)](https://www.ssi.gouv.fr/guide/ebios-risk-manager-la-methode/)
[![MITRE ATT&CK](https://img.shields.io/badge/Framework-MITRE%20ATT%26CK-E63946?style=flat-square)](https://attack.mitre.org/)
[![ICS](https://img.shields.io/badge/Périmètre-IT%2FOT%20convergé-orange?style=flat-square)](https://attack.mitre.org/matrices/ics/)
[![ANSSI](https://img.shields.io/badge/Référentiel-ANSSI-003189?style=flat-square)](https://www.ssi.gouv.fr/)
[![ISO 27001](https://img.shields.io/badge/ISO-27001%3A2022-blue?style=flat-square)](https://www.iso.org/standard/27001)
[![IEC 62443](https://img.shields.io/badge/IEC-62443-blue?style=flat-square)](https://www.iec.ch/homepage)

---

## 📋 Présentation du projet

Ce projet est une **analyse de risques complète** menée selon la méthode **EBIOS Risk Manager (EBIOS RM)** de l'ANSSI sur la société fictive **BIOÉNERGIE TECH** — spécialiste de la fabrication de cellules et modules de batteries innovantes et de turbines mini-hydrauliques, implantée à Chambéry.

L'étude couvre l'horizon stratégique **2026–2029** et traite en particulier la convergence **IT/OT** dans un environnement industriel complexe et dense, avec 49 salariés, plusieurs sous-traitants réguliers (DataSys, ProClean, ThermoVent) et des clients majeurs (Voltis Mobility, Hydron Storage Systems, AlpEnergy Réseaux).

### Objectifs pédagogiques

- Maîtriser les 5 ateliers de la méthode EBIOS RM dans un contexte industriel réel
- Identifier et hiérarchiser des risques cyber, physiques et environnementaux
- Construire des scénarios stratégiques et opérationnels réalistes (chemin CONNAÎTRE → ENTRER → TROUVER → EXPLOITER)
- Produire un plan de traitement du risque avec KPIs mesurables
- Appliquer les référentiels ISO 27001, IEC 62443 et le framework MITRE ATT&CK ICS

---

## 🏭 Contexte de l'étude

| Attribut | Détail |
|---|---|
| Entreprise | BIOÉNERGIE TECH |
| Secteur | Industrie chimique / énergie / batteries |
| Localisation | Chambéry — zone industrielle dense |
| Surface | 3 hectares — 2 bâtiments (4 200 m² et 12 000 m²) |
| Effectif | 49 salariés + sous-traitants réguliers |
| Période d'analyse | 2026–2029 |
| Périmètre | Production IT + OT convergé |
| Enjeux clés | R&D stratégique, traçabilité contractuelle, continuité de production |

### Environnement à risques

```
                       ┌─────────────────────────────────┐
         Voie ferrée   │   Zone industrielle Chambéry    │  Fret régional
         (vibrations)  │                                  │  (nord du site)
                       │   CHEMIKALIA (solvants/acides)   │
                       │   ← 40 m ← BIOÉNERGIE TECH       │
                       │                                  │
                       │   TRANSLOGISTIQUE SAVOIE ← 70 m  │
                       │   Ateliers métallurgiques ← 80 m │
                       └─────────────────────────────────┘
```

---

## 📂 Structure du repo

```
EBIOS-RM-BioenergieTech/
├── README.md
├── docs/
│   ├── rapport-complet.pdf                  # Rapport intégral (5 ateliers)
│   └── synthese-executive.pdf               # Résumé décisionnel
├── atelier1-cadrage/
│   ├── valeurs-metiers.md                   # VM1, VM2, VM3
│   ├── evenements-redoutes.md               # DICT — gravité 1-4
│   └── socle-securite.md                    # Écarts ISO/IEC 27001, IEC 62443
├── atelier2-sources-risques/
│   ├── identification-SR-OV.md              # Sources de risques & objectifs visés
│   └── evaluation-pertinence.md             # Motivation / Ressources / Activité
├── atelier3-scenarios-strategiques/
│   ├── parties-prenantes.md                 # Tableau + formule de menace
│   ├── PP-critiques.md                      # DataSys, ProClean, ThermoVent
│   ├── scenarios-strategiques.md            # SS1, SS2, SS3
│   └── mesures-securite-PP.md              # Réduction menace initiale
├── atelier4-scenarios-operationnels/
│   ├── SS1-SO1-compromission-ProClean.md
│   ├── SS1-SO2-acces-SI-recherche.md
│   ├── SS2-SO1-ransomware-DataSys.md
│   ├── SS2-SO2-propagation-IT-OT.md
│   ├── SS3-SO1-alteration-config-interne.md
│   ├── SS3-SO2-detournement-ThermoVent.md
│   └── evaluation-vraisemblance.md
└── atelier5-traitement/
    ├── synthese-risques.md                  # Diagramme de Farmer
    ├── mesures-R1-R2-R3.md                 # Plans de réduction
    ├── risques-residuels.md                 # Niveaux finaux
    └── plan-actions.md                      # KPIs, responsables, échéances
```

---

## 🔬 Méthodologie — 5 Ateliers EBIOS RM

### Atelier 1 — Cadrage et socle de sécurité

**3 valeurs métiers identifiées** et leurs biens supports :

| Valeur Métier | Description | Critère dominant |
|---|---|---|
| **VM1** | Production des cellules et modules de batteries | Disponibilité / Intégrité |
| **VM2** | Stockage temporaire des produits finis | Disponibilité / Traçabilité |
| **VM3** | Activités R&D (alliages recyclables, formulations) | Confidentialité / Disponibilité |

**7 événements redoutés** identifiés selon le critère DICT (Disponibilité, Intégrité, Confidentialité, Traçabilité) avec gravité 1–4 :

| ER | VM | Critère | Gravité | Description |
|---|---|---|---|---|
| ER1 | VM1 | D | 3 | Panne automates / coupure énergie paralysant la production |
| ER2 | VM1 | I | 3 | Altération des réglages presses → cellules non conformes |
| ER3 | VM1 | C | 2 | Observation non autorisée des procédés par des tiers |
| ER4 | VM2 | D | 4 | Destruction des stocks par incendie / explosion (effet domino Chemikalia) |
| ER5 | VM2 | T | 4 | Effacement des historiques de traçabilité AlpEnergy |
| ER6 | VM3 | D | 4 | Indisponibilité des instruments R&D (incendie, retrait autorisation) |
| ER7 | VM3 | C | 4 | Exfiltration des formules et secrets industriels |

**7 écarts au socle** documentés (ISO 27001, IEC 62443, ISO 45001) :

```
⚠️ Absence totale de contrôle d'accès au 2e étage (Direction, R&D, comptabilité)
⚠️ Sauvegardes sur bandes obsolètes — non testées en restauration
⚠️ Réglages machines informels — aucune gestion des changements
⚠️ Serveur central vieillissant — vulnérabilités connues non corrigées
⚠️ Absence de segmentation IT/OT
⚠️ EPI non contrôlés systématiquement
⚠️ Absence de gestion des changements IT/OT formalisée
```

---

### Atelier 2 — Sources de risques

**7 sources de risques** identifiées, **3 couples SR/OV retenus** après évaluation de pertinence (Motivation / Ressources / Activité) :

| SR retenue | Objectif Visé | Pertinence |
|---|---|---|
| Groupes d'espionnage industriel | Exfiltrer les formules R&D avant brevetage | **Élevée** |
| Cyberattaquant (ransomware) | Détruire les historiques de traçabilité AlpEnergy | **Élevée** |
| Activiste idéologiste | Altérer les configurations machines (conflit RH) | **Moyenne** |

---

### Atelier 3 — Scénarios stratégiques

**Évaluation de la menace des parties prenantes** par la formule :

```
Menace = (Dépendance × Pénétration) / (Maturité × Confiance)
```

**3 parties prenantes critiques** (menace ≥ 1) :

| Partie Prenante | Menace initiale | Vecteur principal |
|---|---|---|
| **DataSys** (maintenance IT/SI) | **4.0** | SS2 — Ransomware via accès distant privilégié |
| **ProClean** (nettoyage) | **4.0** | SS1 — Exfiltration R&D via accès physique non contrôlé |
| **ThermoVent** (maintenance CVC/OT) | **1.5** | SS3 — Altération configurations OT |

**3 scénarios stratégiques** élaborés :

```
SS1 ─ Exfiltration R&D via ProClean          → Gravité 4/4
       SR: Espionnage industriel · PP: ProClean · VM: VM3

SS2 ─ Ransomware + destruction traçabilité   → Gravité 4/4
       SR: Cyberattaquant · PP: DataSys · VM: VM2

SS3 ─ Altération configs sur fond de conflit → Gravité 3/4
       SR: Activiste idéologiste · PP: ThermoVent · VM: VM1
```

---

### Atelier 4 — Scénarios opérationnels

**6 scénarios opérationnels** construits selon la séquence **CONNAÎTRE → ENTRER → TROUVER → EXPLOITER** :

| SO | Scénario stratégique | Vraisemblance | Niveau de risque |
|---|---|---|---|
| SS1-SO1 | Compromission agent ProClean (nettoyage soir, 2e étage) | **4/4** | **16** |
| SS2-SO1 | Détournement accès distant DataSys (ransomware) | **4/4** | **16** |
| SS1-SO2 | Accès SI recherche depuis zone non contrôlée | **3/4** | **12** |
| SS2-SO2 | Propagation IT/OT vers serveur central | **3/4** | **12** |
| SS3-SO1 | Altération réglages via accès interne (conflit RH) | **3/4** | **9** |
| SS3-SO2 | Détournement intervention ThermoVent (OT) | **2/4** | **6** |

> Seuil d'acceptabilité défini par la direction : niveau ≤ 8

---

### Atelier 5 — Traitement du risque

**Risques initiaux → résiduels** après mesures :

| Risque | Niveau initial | Niveau résiduel | Décision |
|---|---|---|---|
| R1 (Exfiltration R&D) | **16** | **8** | Accepté sous suivi |
| R2 (Ransomware traçabilité) | **16** | **6** | Accepté sous suivi |
| R3 (Altération config OT) | **9** | **6** | Accepté sous suivi |

**Plan d'actions prioritaires** (P1 = T0+3 mois, P2 = T0+6 mois) :

| Priorité | Mesure | Risque | Échéance |
|---|---|---|---|
| **P1** | Contrôle d'accès badge au 2e étage (R&D) | R1 / R3 | S1 2026 |
| **P1** | MFA + bastion d'administration pour accès distants | R2 | S1 2026 |
| **P1** | Sauvegardes 3-2-1 testées (hors ligne, immuables) | R2 | S1 2026 |
| **P1** | Segmentation IT/OT + patch management | R2 / R3 | S2 2026 |
| **P2** | Déploiement EDR + supervision centralisée | R2 | S2 2026 |
| **P2** | Gestion des changements OT + golden config | R3 | S2 2026 |
| **P2** | Chiffrement au repos données R&D + classification | R1 | S2 2026 |
| **P2** | NDA + criblage prestataires (ProClean, DataSys) | R1 | S1-S2 2026 |

---

## 📊 Synthèse des risques

```
DIAGRAMME DE FARMER — Avant traitement

Gravité
  4 │   ·R1(16)   ·R2(16)
    │
  3 │              ·R3(9)
    │
  2 │
    │
  1 │
    └────────────────────── Vraisemblance
        1    2    3    4

DIAGRAMME DE FARMER — Après traitement

Gravité
  4 │        ·R1(8)
    │
  3 │   ·R3(6)    ·R2(6)
    │
  2 │ ─ ─ ─ seuil=8 ─ ─
    │
  1 │
    └────────────────────── Vraisemblance
        1    2    3    4
```

---

## 🧰 Référentiels appliqués

| Référentiel | Usage dans l'étude |
|---|---|
| **EBIOS RM (ANSSI)** | Méthode structurante des 5 ateliers |
| **ISO/IEC 27001:2022** | Socle de sécurité SI (A.7, A.8, A.11, A.12) |
| **ISO/IEC 27002** | Contrôles de sécurité de l'information |
| **IEC 62443** | Sécurité des systèmes industriels (IT/OT) |
| **ISO 45001** | Sécurité et santé au travail (EPI, coactivité) |
| **ISO 9001** | Gestion de la qualité (réglages machines) |
| **ISO 22301** | Continuité d'activité (PCA/PRA) |
| **MITRE ATT&CK ICS** | Modélisation des techniques d'attaque OT |
| **NIST CSF** | Évaluation de la maturité cybersécurité |

---

## 🎯 Compétences développées

| Domaine | Compétences |
|---|---|
| Analyse de risques | EBIOS RM 5 ateliers, identification des valeurs métiers, DICT |
| Gestion des risques | Évaluation gravité/vraisemblance, seuil d'acceptabilité, Farmer |
| Threat Modeling | Construction de scénarios opérationnels, chemin CONNAÎTRE/ENTRER/TROUVER/EXPLOITER |
| Sécurité industrielle | Convergence IT/OT, IEC 62443, segmentation réseau industriel |
| Gouvernance | KPIs, plan d'actions priorisé, modalités de suivi, comité de sécurité |
| Référentiels | ISO 27001, IEC 62443, NIST CSF, EBIOS RM |
| Rédaction | Rapport structuré, fiche de risque, synthèse exécutive |

---

## 👥 Équipe

Ce projet a été réalisé dans le cadre du **Master 2 Cybersécurité — Ecole 2600** :

| Auteur | Profil |
|---|---|
| **Alberick Mahoussi** | M2 Cybersécurité — Blue Team / SOC — Ecole 2600 |
| Lucas Poignard | M2 Cybersécurité — Ecole 2600 |
| Sam Levy | M2 Cybersécurité — Ecole 2600 |

---

## 👤 Contact

**Alberick Mahoussi (K)**  
Étudiant M2 Cybersécurité — Ecole 2600  
Spécialisation Blue Team · SOC Analysis · Gestion des risques  
En recherche d'alternance SOC — septembre 2026

[![LinkedIn](https://img.shields.io/badge/LinkedIn-alberick--mahoussi-0A66C2?style=flat-square&logo=linkedin)](https://linkedin.com/in/alberick-mahoussi)
[![TryHackMe](https://img.shields.io/badge/TryHackMe-Top%202%25-212C42?style=flat-square&logo=tryhackme)](https://tryhackme.com/p/huen992)
[![GitHub](https://img.shields.io/badge/GitHub-alberick--mahoussi-181717?style=flat-square&logo=github)](https://github.com/alberick-mahoussi)

---

## 🔗 Projets liés

- [SIEM-Splunk-Lab](https://github.com/alberick-mahoussi/SIEM-Splunk-Lab) — Lab Splunk avec détection SPL et mapping MITRE ATT&CK
- [Active-Directory-Build-Break-Secure](https://github.com/alberick-mahoussi/Active-Directory-Build-Break-Secure) — Lab Active Directory : construction, attaque, durcissement
- [SIEM-Log-Monitoring-Threat-Detection](https://github.com/alberick-mahoussi/SIEM-Log-Monitoring-Threat-Detection) — Monitoring de logs et détection de menaces

---

## 📜 Licence

Ce projet est publié à des fins académiques et pédagogiques. Les données de l'entreprise BIOÉNERGIE TECH sont fictives et issues d'un cas d'étude de l'Ecole 2600.

> ⚠️ Ce document ne constitue pas un rapport de sécurité destiné à une entreprise réelle. Toute utilisation à des fins commerciales sans autorisation est interdite.
