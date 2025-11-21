# 🖐️ Hand Sign Detection with MobileNetV2 and Real-Time Classification

## Introduction

Ce projet implémente un système de **détection et reconnaissance de signes manuels** à partir de flux vidéo en temps réel. Il combine la puissance d'un modèle pré-entraîné **MobileNetV2** pour la classification d'images, et utilise un modèle de détection de mains pour localiser et classifier les signes manuels en temps réel. Le projet est divisé en deux parties principales : 
1. **L'entraînement du modèle de classification des signes manuels**.
2. **L'implémentation de la détection et classification des signes en temps réel via une webcam**.

---

## Objectifs

Les objectifs de ce projet sont :
1. **Entraîner un modèle de détection de signes manuels** basé sur MobileNetV2.
2. Utiliser des **techniques de traitement d'image** pour détecter les mains en temps réel et classifier les signes.
3. Déployer un système capable de **détecter et classifier** des signes manuels correspondant à des états de santé, comme "Mal de tête", "Au secours", "Vertige", "Vomissements".

---

## Technologies Utilisées

### 1. **TensorFlow / Keras**
   - Utilisé pour construire et entraîner le modèle de classification basé sur **MobileNetV2**.
   - [TensorFlow Documentation](https://www.tensorflow.org/)

### 2. **OpenCV**
   - Utilisé pour capturer les images en temps réel à partir de la caméra et pour la manipulation d'images.
   - [OpenCV Documentation](https://opencv.org/)

### 3. **cvzone**
   - Utilisé pour la détection des mains via le module **HandDetector**.
   - [cvzone Documentation](https://github.com/cvzone/cvzone)

### 4. **MobileNetV2**
   - Modèle de classification d'image léger et pré-entraîné sur ImageNet, utilisé pour l'apprentissage par transfert.
   - [MobileNetV2 Documentation](https://keras.io/api/applications/mobilenet/)

---

## Méthodologie et Algorithmes Utilisés

### 1. **Entraînement du Modèle de Classification**

- **Modèle : MobileNetV2** pré-entraîné sur ImageNet, utilisé pour l'apprentissage par transfert. Nous avons retiré la couche de classification originale et ajouté des couches personnalisées pour la classification des signes manuels.
- **Pré-traitement des images** : Les images sont redimensionnées à 224x224 pixels et normalisées (valeurs des pixels comprises entre 0 et 1).
- **Optimiseur : Adam** avec un taux d'apprentissage de `1e-4`, utilisé pour ajuster les poids du modèle.
- **Fonction de perte** : `categorical_crossentropy` pour les classifications multi-classes.
- **Évaluation** : Le modèle est évalué sur un ensemble de validation avec des métriques comme la précision.

### 2. **Détection et Classification des Signes en Temps Réel**

- **Détection des Mains** : Utilisation du module **HandDetector** de la bibliothèque `cvzone` pour détecter et localiser les mains dans l'image capturée en temps réel par la caméra.
- **Pré-traitement pour la Classification** : L'image capturée est redimensionnée et ajustée à une taille de 300x300 pixels, puis normalisée pour être compatible avec le modèle de classification.
- **Classification des Signes** : Le modèle pré-entraîné (MobileNetV2) est utilisé pour prédire le signe à partir de l'image de la main détectée.

---

## Resultat obtenu
vous trouverer tout  mes resultats et analyse dans notre rapport qui se dans le Dossier [Doc](Doc)
