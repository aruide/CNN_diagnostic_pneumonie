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
![Tensorflow](https://img.shields.io/badge/keras-FF0000?style=&logo=keras&logoColor=white=flat-square)
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
> Licence : La licence spécifique de ces poids n'est pas clairement indiquée sur la page Kaggle. Veuillez consulter la page Kaggle pour les conditions d'utilisation et restrictions éventuelles.

Ce modèle est basé sur l'article original :  
> Rajpurkar et al., “CheXNet: Radiologist-Level Pneumonia Detection on Chest X-Rays with Deep Learning”, Stanford ML Group, 2017. [arXiv:1711.05225](https://arxiv.org/abs/1711.05225)  
> Licence :  le papier scientifique ne propose pas de licence de données ou de modèle formelle et l’article est sous copyright classique.
Merci de consulter cet article et de citer correctement les auteurs si vous utilisez ce modèle.

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
- **Pourquoi ?** ChexNet est un modèle dérivé de DenseNet121, spécialement conçu pour l’analyse d’images médicales, notamment les radiographies thoraciques. Il a été initialement développé pour détecter la pneumonie avec une précision comparable à celle des radiologues.
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
├── data/                    # Données d'entraînement/test
├── img/                     # Résultats visuels
├── requirements.txt         # Dépendances
└── README.md
```

## ⚙️ Installation

1. Cloner le dépôt :
```bash
git clone https://github.com/aruide/CNN_diagnostic_pneumonie.git
cd CNN_diagnostic_pneumonie
```
2. Créer un environnement virtuel et l’activer :
```bash
python -m venv env
source env/bin/activate  # (Windows : env\Scripts\activate)
```

3. Installer les dépendances :
```bash
pip install -r requirements.txt
```

4. Installer les dépendances Nvidia (optionnel) :
**cette partie n'est pas necessaire mais fortement recomander si vous avez une carte graphique Nvida compatible avec CUDA12.2 et CUDNN 8.9**

**cette partie marche avec un WSL ubuntu**

pour CUDA: suivre les étape du site:
> https://developer.nvidia.com/cuda-12-2-0-download-archive

pour CUDNN télécharger l'archive sur ce site (avoir un compte NVIDIA developpeur):
>https://developer.nvidia.com/rdp/cudnn-archive

ensuite suivre ces étape:
```bash
#decompresser l'archive
tar -xzvf cudnn-linux-x86_64-8.9.*.tgz
#compier le contenu des fichier
sudo cp cuda/include/cudnn*.h /usr/local/cuda/include
sudo cp -P cuda/lib64/libcudnn* /usr/local/cuda/lib64
sudo chmod a+r /usr/local/cuda/include/cudnn*.h /usr/local/cuda/lib64/libcudnn*
#creer la variable d'environnement
export LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH
#mettre à jour
source ~/.bashrc
```

il y à des les codes une partie pour tester si votre carte graphique est reconnu ou non

## 🚀 Utilisation

Structure attendue :
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
- `EfficientNetB0_diagnostic_pneumonie.ipynb`
- `MobileNetV3Large_diagnostic_pneumonie.ipynb`

Suivre les instructions dans les cellules Markdown.

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

## 👤 Auteur
@aruide

## 📄 Licence

Ce projet est sous licence MIT. Voir le fichier LICENSE pour plus d'informations.

Les poids préentraînés et le modèle original sont la propriété de leurs auteurs respectifs.  
Merci de consulter les conditions d'utilisation spécifiques pour chacun.