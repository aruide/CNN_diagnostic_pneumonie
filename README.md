# 🧬 Diagnostic de la Pneumonie via CNN

## 🏷️ Tags

![Deep Learning](https://img.shields.io/badge/deep--learning-orange?style=flat-square)
![convolutional-neural-networks](https://img.shields.io/badge/convolutional--neural--networks-orange?style=flat-square)
![cnn ](https://img.shields.io/badge/cnn-orange?style=flat-square)
![image-classification](https://img.shields.io/badge/image--classification-orange?style=flat-square)
![computer-vision](https://img.shields.io/badge/computer--vision-orange?style=flat-square)
![healthcare-ai](https://img.shields.io/badge/healthcare--ai-orange?style=flat-square)
![transfer-learning](https://img.shields.io/badge/transfer--learning-orange?style=flat-square)
![binary-classification](https://img.shields.io/badge/binary--classification-orange?style=flat-square)
![ai-for-healthcare](https://img.shields.io/badge/ai--for--healthcare-orange?style=flat-square)
![DenseNet121/ChexNet](https://img.shields.io/badge/DenseNet121/CheXNet-blueviolet?style=flat-square)
![MobileNetV3Large](https://img.shields.io/badge/MobileNetV3Large-blueviolet?style=flat-square)
![EfficientNetB0](https://img.shields.io/badge/EfficientNetB0-blueviolet?style=flat-square)
![Tensorflow](https://img.shields.io/badge/tensorflow-FF3F06?style=&logo=tensorflow&logoColor=white=flat-square)
![Keras](https://img.shields.io/badge/keras-FF0000?style=&logo=keras&logoColor=white=flat-square)
![Medical Imaging](https://img.shields.io/badge/medical--imaging-green?style=flat-square)
![Pneumonia Detection](https://img.shields.io/badge/pneumonia--detection-green?style=flat-square)
![chest-xray ](https://img.shields.io/badge/chest--xray-green?style=flat-square)
![radiology](https://img.shields.io/badge/radiology-green?style=flat-square)
![WSL2](https://img.shields.io/badge/wsl2-informational?style=flat-square)
![WINDOWS](https://img.shields.io/badge/windows-informational?style=flat-square)
![CUDA 12.1](https://img.shields.io/badge/cuda-informational?style=flat-square)
![CUDNN 8.9](https://img.shields.io/badge/cudnn-informational?style=flat-square)

## ⚠️ Avertissement
Ce projet est à but éducatif uniquement. Les modèles développés ici ne doit pas être utilisé pour des diagnostics médicaux réels sans validation clinique appropriée.

## 📚 Modèles utilisés et mentions légales

Les poids préentraînés de CheXNet (DenseNet121 modifié) utilisés dans ce projet proviennent de :

> https://www.kaggle.com/datasets/theewok/chexnet-keras-weights  
> **Licence** : La licence spécifique de ces poids n'est pas clairement indiquée sur la page Kaggle. Veuillez consulter la page Kaggle pour les conditions d'utilisation et restrictions éventuelles.

Ce modèle est basé sur l'article original :  
> Rajpurkar et al., “CheXNet: Radiologist-Level Pneumonia Detection on Chest X-Rays with Deep Learning”, Stanford ML Group, 2017. [arXiv:1711.05225](https://arxiv.org/abs/1711.05225)  
> **Licence** :  le papier scientifique ne propose pas de licence de données ou de modèle formelle et l’article est sous copyright classique.
Merci de consulter cet article et de citer correctement les auteurs si vous utilisez ce modèle.

Les images utilisées pour l'entraînement, la validation et le test proviennent du jeu de données suivant :
> https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia  
> **Licence** : CC BY 4.0

**⚠️ Utilisation dans ce projet à but pédagogique uniquement.**

## 🩺 Présentation

Ce projet a été réalisé dans le cadre d’une formation chez **Simplon**. L’objectif est de construire un modèle de deep learning capable de diagnostiquer la **pneumonie** à partir d’images **radiographiques pulmonaires** mais surtout à partir d'un modéle préexistant. Trois modèles CNN sont explorés, chacun avec une approche différente pour évaluer leurs performances et leur pertinence.

---

## 🧠 Objectifs

- Détecter la pneumonie sur des radiographies thoraciques.
- Comparer les performances de trois architectures CNN :
  - **ChexNet (modele DenseNet121 modifié)**
  - **MobileNetV3Large**
  - **EfficientNetB0**
- Expérimenter la récupération, l’entraînement et l’évaluation de modèles pré-entraînés.

---

## 🏗️ Modèles Utilisés

### 🔬 ChexNet (basé sur DenseNet121 modifié)
- **Approche** : Concrète et orientée application réelle
- **Pourquoi ?** ChexNet est un modèle dérivé de DenseNet121, spécialement conçu pour l’analyse d’images médicales, notamment les radiographies thoraciques.  Il a été initialement développé pour détecter 14 pathologies (dont la pneumonie), avec une précision comparable à celle des radiologues.
- **Avantages** : Architecture profonde et performante, excellents résultats sur les jeux de données médicaux. Il bénéficie de l’héritage DenseNet tout en étant optimisé pour les cas d’usage cliniques.

### 📱 MobileNetV3Large
- **Approche** : Pédagogique
- **Pourquoi ?** Permet d'explorer la récupération et la réutilisation de modèles légers.
- **Avantages** : Léger, rapide à entraîner, idéal pour les systèmes embarqués.

### ⚖️ EfficientNetB0
- **Approche** : Intermédiaire
- **Pourquoi ?** Bon équilibre entre précision et performance.
- **Avantages** : Bonne efficacité computationnelle avec de bons résultats.

---

## 🗂️ Structure du projet

```bash
CNN_diagnostic_pneumonie/
├── CheXNet_diagnostic_pneumonie.ipynb
├── EfficientNetB0_diagnostic_pneumonie.ipynb
├── MobileNetV3Large_diagnostic_pneumonie.ipynb
├── data/                    # Données train/test/val
├── cache/                   # Données en cache
├── corrupt_images/          # dossier créer lors de la verif des images corrompue
├── img/
├── weights/                 # contient le poids du modele chexnet (mais aussi contient les poids sauvegardé des test de modele)
│   └────── model/           # dossier créer lors du test du modele qui sauvegarde les poids (en .keras)
├── mlruns/                  # dossier est générer lors de l'appelle de mlflow
├── requirements.txt         # Dépendances
├── LICENCE
└── README.md
```

## ⚙️ Installation (environnement WSL Ubuntu)

1. Cloner le dépôt :
```bash
git clone https://github.com/aruide/CNN_diagnostic_pneumonie.git
cd CNN_diagnostic_pneumonie
```

2. Installer python (version 3.10 afin de faire fonction tensorflow en version 2.16.2)
```bash
sudo apt update                                                 # mettre à jour les package
sudo apt install -y software-properties-common                  # installer les dependances
sudo add-apt-repository ppa:deadsnakes/ppa                      # ajout du dépôt deadsnake (afin de récuperer la version 3.10)
sudo apt update
sudo apt install -y python3.10 python3.10-venv python3.10-dev   # installer python 3.10
python3.10 --version                                            # vérifier l'installation
```

2. Créer un environnement virtuel et l’activer :
```bash
python3.10 -m venv .venv
source .venv/bin/activate  # (Windows : env\Scripts\activate)
```

3. Installer les dépendances :
```bash
pip install -r requirements.txt
```

⚠️ pour utiliser le GPU: décommenter ces lignes de code dans le `requirements.txt`
```bash
#nvidia-cudnn-cu12==8.9.2.26
#nvidia-cublas-cu12==12.1.3.1
#nvidia-cuda-runtime-cu12==12.2.140
```

## 🚀 Utilisation

Structure attendue pour les données :
```bash
data/
├── train/
│   ├── NORMAL/
│   └── PNEUMONIA/
├── val/
│   ├── NORMAL/
│   └── PNEUMONIA/
└── test/
│   ├── NORMAL/
│   └── PNEUMONIA/
```

Lance l’un des notebooks selon l’architecture souhaitée :
- `CheXNet_diagnostic_pneumonie.ipynb` ⚠️ **utilisation du GPU fortement conseillé**
- `EfficientNetB0_diagnostic_pneumonie.ipynb` ⚠️ **utilisation du GPU fortement conseillé**
- `MobileNetV3Large_diagnostic_pneumonie.ipynb`

suivez les instructions dans les cellules Markdown.

ℹ️ Pour accélérer l'exécution des deux premiers modèles, lancez d'abord le notebook `MobileNetV3Large_diagnostic_pneumonie.ipynb`\
afin de mettre en cache les données de validation et de test.

## 📊 Résultats attendus
Les modèles sont évalués avec les métriques suivantes :

- Précision
- Rappel
- F1-score
- Matrice de confusion

Les comparaisons permettent de choisir le meilleur modèle selon :

- La précision diagnostique
- Le temps d'entraînement
- Les ressources disponibles

## 📊 Suivi des Expériences avec MLflow

Ce projet utilise **MLflow** pour suivre et gérer les expériences de machine learning.

### 🔍 Pourquoi MLflow ?

MLflow permet de :

- 📁 **Suivre les expériences** : enregistre les paramètres, les métriques, les modèles, et les artefacts (graphiques, fichiers, etc.).
- 🔄 **Comparer les runs** : facilite l’analyse des performances entre plusieurs expérimentations.
- 💾 **Sauvegarder les modèles** : possibilité de versionner et de recharger les modèles entraînés.
- 🌐 **Interface web** : accès à une interface graphique pour visualiser tous les runs et leurs résultats.

### ⚙️ Comment l'utiliser

1. **Lancer le tracking MLflow** (dans un terminal à la racine du projet) :

   ```bash
   mlflow ui
   ```
Cela ouvre une interface web à l'adresse : http://localhost:5000

## 👤 Auteur
@aruide

## 📄 Licence

Ce projet est sous licence MIT. Voir le fichier LICENSE pour plus d'informations.

Les poids préentraînés et le modèle original sont la propriété de leurs auteurs respectifs.  
Merci de consulter les conditions d'utilisation spécifiques pour chacun.