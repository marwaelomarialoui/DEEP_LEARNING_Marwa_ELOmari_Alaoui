[README_Fin_Module_DEEP LEARNING_Marwa_ELOmari_Alaoui.md](https://github.com/user-attachments/files/29055709/README_Fin_Module_DEEP.LEARNING_Marwa_ELOmari_Alaoui.md)
# Projet de Fin de Module — Deep Learning
**Auteure :** Marwa EL Omari Alaoui
**École :** EMSI Casablanca — Département Informatique
**Module :** Deep Learning

## Idée générale du projet

Ce repository constitue le rendu du projet de fin de module de Deep Learning. L'idée centrale du travail est de démontrer, à travers une étude **comparative, empirique et critique**, comment le choix d'une architecture de réseau de neurones doit être guidé par la structure géométrique intrinsèque des données qu'elle traite — un principe appelé **biais inductif**.

Trois grandes familles de données et d'architectures sont ainsi étudiées dans trois notebooks indépendants :

| Partie | Type de données | Architecture | Dataset | Idée clé |
|---|---|---|---|---|
| **I** | Tabulaires (hétérogènes) | MLP (Perceptron Multicouche) | UCI Adult Income (~48 842 lignes) | Pas de structure spatiale → biais inductif minimal, réseau pleinement connecté |
| **II** | Images (grilles 2D) | CNN (style VGG-mini) | CIFAR-10 | Localité spatiale + invariance par translation → convolutions et partage de poids |
| **III** | Séquences textuelles | RNN / LSTM / GRU + Seq2Seq avec Attention | OpenSubtitles EN-FR (2 000 paires) | Dépendance temporelle → mémoire contextuelle via état caché, traduction automatique |

Chaque notebook suit une démarche similaire : positionnement théorique, implémentation PyTorch, entraînement, évaluation critique des résultats et synthèse scientifique. Le rapport final (`.docx`) consolide les trois parties dans un document académique unique avec une discussion transversale comparant les trois architectures.

### Résultats clés
- **Partie I (MLP)** : Accuracy de 84,34 % et AUC de 0,90 sur Adult Income, avec un rappel plus faible (55 %) sur la classe minoritaire (revenus > 50K), illustrant la sensibilité du MLP au déséquilibre des classes.
- **Partie II (CNN)** : Le CNN atteint 78,49 % d'Accuracy sur CIFAR-10, contre seulement 46,52 % pour un MLP appliqué aux images aplaties — démonstration empirique de la supériorité du biais inductif convolutionnel.
- **Partie III (RNN/Seq2Seq)** : Comparaison RNN simple vs LSTM vs GRU sur la perplexité, puis système de traduction Encodeur-Décodeur avec mécanisme d'Attention de Bahdanau et deux stratégies de décodage (Greedy vs Beam Search).

## Structure des dossiers et fichiers

```
.
├── Partie1_MLP_PyTorch__Marwa_ELOmari_Alaoui.ipynb
├── Partie2_CNN_Vision__Marwa_ELOmari_Alaoui.ipynb
├── Partie3_RNN_Seq2Seq__Marwa_ELOmari_Alaouii_pynb.ipynb
├── Rapport_Fin_Module_DEEP_LEARNING_Marwa_ELOmari_Alaoui.docx
└── README.md
```

### `Partie1_MLP_PyTorch__Marwa_ELOmari_Alaoui.ipynb`
Notebook Google Colab consacré au **Perceptron Multicouche** sur données tabulaires (dataset UCI Adult Income).
Sections principales :
- Installation des dépendances et vérification du dispositif de calcul (CPU/GPU)
- Concepts fondamentaux PyTorch : `nn.Module`, `state_dict`, `device`
- Chargement et préparation du dataset (encodage One-Hot, normalisation `StandardScaler`)
- Implémentation de deux versions du MLP
- Inspection des paramètres (`named_parameters()`, `state_dict()`)
- Stratégies d'initialisation des poids
- Boucle d'entraînement avec early stopping et scheduler
- Sauvegarde/rechargement du meilleur modèle
- Évaluation finale sur le jeu de test
- Visualisations et analyse des courbes
- Synthèse scientifique

### `Partie2_CNN_Vision__Marwa_ELOmari_Alaoui.ipynb`
Notebook consacré aux **Réseaux de Neurones Convolutionnels** appliqués à la vision par ordinateur (dataset CIFAR-10).
Sections principales :
- Supériorité théorique du CNN sur le MLP pour les images
- Calculs manuels (formule de taille de sortie, corrélation croisée)
- Implémentations manuelles vs PyTorch (validation algorithmique)
- Chargement de CIFAR-10 et pipeline d'augmentation de données
- Architecture CNN style VGG-mini, comparée à une baseline MLP
- Boucle d'entraînement et analyse de convergence
- Étude ablative des hyperparamètres architecturaux
- Visualisations : feature maps, étude ablative, matrices de confusion
- Synthèse scientifique

### `Partie3_RNN_Seq2Seq__Marwa_ELOmari_Alaouii_pynb.ipynb`
Notebook consacré aux **architectures récurrentes** et à la **traduction automatique** (corpus OpenSubtitles EN-FR).
Sections principales :
- Fondements théoriques : RNN, LSTM, GRU, perplexité
- Préparation du corpus : vocabulaire, encodage, padding
- Modèles de langage RNN/LSTM/GRU avec BPTT et gradient clipping
- Système Seq2Seq : Encodeur-Décodeur LSTM avec mécanisme d'Attention de Bahdanau
- Stratégies de décodage : Greedy Search vs Beam Search
- Visualisations : perplexité, normes de gradient, comparaisons des modèles
- Synthèse scientifique

### `Rapport_Fin_Module_DEEP_LEARNING_Marwa_ELOmari_Alaoui.docx`
Rapport académique complet au format Word, consolidant les trois parties :
- Remerciements et introduction générale (concept de biais inductif)
- Partie I : MLP et données tabulaires hétérogènes
- Partie II : CNN et vision par ordinateur
- Partie III : Architectures récurrentes et traduction Seq2Seq
- Discussion transversale finale comparant les trois architectures et leurs espaces latents

## Comment utiliser ce repository
1. Ouvrir les notebooks (`.ipynb`) dans Google Colab ou Jupyter pour exécuter le code, reproduire les entraînements et visualiser les résultats.
2. Consulter le rapport (`.docx`) pour une lecture théorique et synthétique des trois parties, accompagnée de l'analyse critique des résultats.
3. Chaque notebook est autonome (installation des dépendances incluse en début de fichier) et peut être exécuté indépendamment des deux autres.
