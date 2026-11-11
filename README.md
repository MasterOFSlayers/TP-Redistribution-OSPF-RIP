# TP Redistribution OSPF / RIP : ActivePresenter et vidéo

**Atelier WAN, RSI 3, ISET de Nabeul, 2026/2027**
**Étudiant :** Malik SAIED
**Enseignant :** M. Zied Romdane
**Date :** Novembre 2026

---

## Présentation

Ce dépôt contient la partie **« live action » et ActivePresenter** du TP *Redistribution de routes*.

Le TP reproduit sous **GNS3** l'exemple du cours : un domaine OSPF (R1, area 0), un domaine RIPv2 (R3) et un routeur de frontière R2 sur lequel on configure la redistribution mutuelle. La manipulation a été filmée avec **ActivePresenter**, puis montée et exportée en vidéo MP4.

> Le compte rendu de la redistribution (Word et PDF) et le projet GNS3 (archive) ont déjà été remis dans le devoir sur Google Classroom.

## Contenu du dépôt

| Fichier | Description |
|---|---|
| [TP_Redistribution_OSPF_RIP_Malik_SAIED.mp4](TP_Redistribution_OSPF_RIP_Malik_SAIED.mp4) | Vidéo finale de la manipulation (MP4 H.264, 1920 × 1080, 4:04) |
| [TP_Redistribution_OSPF_RIP_Malik_SAIED.approj](TP_Redistribution_OSPF_RIP_Malik_SAIED.approj) | Projet ActivePresenter modifiable |
| [CR_TP_ActivePresenter_Malik_SAIED.pdf](CR_TP_ActivePresenter_Malik_SAIED.pdf) | Compte rendu du TP ActivePresenter (version PDF) |
| [CR_TP_ActivePresenter_Malik_SAIED.docx](CR_TP_ActivePresenter_Malik_SAIED.docx) | Compte rendu du TP ActivePresenter (version Word) |

## Maquette

- 3 routeurs Cisco 3725 avec module NM-4T (liaisons Serial1/0 et Serial1/1) : **R1** (OSPF), **R2** (frontière), **R3** (RIP)
- 2 commutateurs : SW-OSPF et SW-RIP
- 2 hôtes VPCS : **PC-OSPF** (1.1.1.100) et **PC-RIP** (3.3.3.100)
- Les routeurs démarrent sans configuration : tout est configuré devant la caméra

## Scénario de la vidéo

| Temps | Séquence |
|---|---|
| 0:08 | Topologie : domaine OSPF (area 0) à gauche, domaine RIPv2 à droite, R2 = routeur de frontière |
| 0:31 | Étape 1 : adressage IP des routeurs et des PC |
| 1:51 | Étape 2 : OSPF (area 0) sur R1 et R2, RIP version 2 sur R2 et R3 |
| 2:35 | R2 connaît les deux domaines : routes O (OSPF) et R (RIP) |
| 2:42 | Étape 3 : avant la redistribution, R1 ignore 3.3.3.0/24 et R3 ignore 1.1.1.0/24 |
| 3:02 | Étape 4 : redistribution mutuelle OSPF ↔ RIP sur R2 |
| 3:16 | Étape 5 : R1 reçoit les routes RIP en O E2, R3 reçoit les routes OSPF en R |
| 3:30 | Étape 6 : test de bout en bout entre PC-OSPF et PC-RIP |
| 3:47 | Fin de la démonstration |
| 3:53 | Diapositive « Ce qu'il faut retenir » |

## Résultats

| Avant la redistribution | Après la redistribution |
|---|---|
| R1 ne connaît que 1.1.1.0/24 et 192.168.12.0/24 | R1 apprend 3.3.3.0/24 et 192.168.23.0/24 en O E2 [110/10] |
| R3 ne connaît que 3.3.3.0/24 et 192.168.23.0/24 | R3 apprend 1.1.1.0/24 et 192.168.12.0/24 en R [120/2] |
| ping PC-OSPF → PC-RIP : *Destination host unreachable* | ping et traceroute réussis |

## Outils utilisés

- **ActivePresenter 10.6.2** (édition gratuite) : capture, montage et export
- **GNS3 2.2.61** : maquette réseau
- **PuTTY** : consoles des routeurs et des PC

## Paramètres de capture et d'export

- Capture plein écran (1920 × 1080), 30 images par seconde
- Audio et webcam désactivés : les explications sont données par des légendes écrites animées
- Export : MP4 (H.264, AAC), 14,4 Mo

---

*Malik SAIED, RSI 3, ISET de Nabeul*
