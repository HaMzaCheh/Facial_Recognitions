# 👤 **Easy Facial Recognition App**  
*Une application de reconnaissance faciale en temps réel avec Python*

Cette application, développée par Anis pour Defend Intelligence, utilise des modèles pré-entraînés de dlib pour détecter et reconnaître des visages en temps réel via une webcam. Elle est conçue pour identifier des visages connus à partir d’un répertoire d’images et marquer les visages inconnus.

---

## 🧠 **Présentation du Projet**  
- 🎯 **Objectif** : Créer une solution de reconnaissance faciale simple et efficace pour des applications de sécurité ou éducatives.  
- 📅 **Date** : Dernière mise à jour : 04/07/2025, 16:38 CEST.  
- 👨‍💻 **Auteur** : Anis (Defend Intelligence).  

L’application utilise des points de repère faciaux (68 ou 5 points) pour encoder les visages et compare ces encodages avec une base de données d’images connues.

---

## ✨ **Fonctionnalités**  
- 📷 Détection des visages en temps réel via webcam.  
- 🔍 Reconnaissance des visages connus à partir d’un répertoire d’images.  
- 📌 Marquage des visages inconnus comme "Unknown".  
- 🎯 Affichage des points de repère faciaux (landmarks) sur les visages détectés.  
- ⏹️ Arrêt avec la touche `q`.  

---

## 🛠️ **Prérequis**  
Assurez-vous d’avoir installé :  
- **Python** (version 3.7 ou supérieure).  
- **Bibliothèques Python** :  
  - `opencv-python` (`pip install opencv-python`)  
  - `dlib` (`pip install dlib`) *(nécessite un compilateur C++ sur Windows)*  
  - `imutils` (`pip install imutils`)  
  - `numpy` (`pip install numpy`)  
  - `Pillow` (`pip install Pillow`)  
- **Fichiers pré-entraînés** :  
  - `shape_predictor_68_face_landmarks.dat`  
  - `shape_predictor_5_face_landmarks.dat`  
  - `dlib_face_recognition_resnet_model_v1.dat`  
  👉 Téléchargez ces fichiers depuis [dlib models](http://dlib.net/files/) et placez-les dans un dossier `pretrained_model/`.

---

## 🚀 **Installation et Mise en Marche**  
### Étapes :  
1. **Cloner le dépôt** :  
   ```bash
   git clone https://github.com/votre-utilisateur/Easy-Facial-Recognition.git
   ````
   ```bash
   cd Easy-Facial-Recognition
   ````


2. **Installer les dépendances** :

   ```bash
   pip install -r requirements.txt
   ````

   *(Créer un fichier `requirements.txt` si nécessaire avec toutes les bibliothèques listées ci-dessus.)*
3. **Préparer les fichiers modèles** :

   * Créez un dossier `pretrained_model/` et ajoutez les fichiers `.dat` téléchargés.
4. **Préparer les visages connus** :

   * Créez un dossier spécifié avec l’argument `-i` (ex. `known_faces/`) et ajoutez des images `.jpg` ou `.png` des visages connus.
5. **Lancer l’application** :

   ```bash
   python main.py -i path/to/known_faces
   ````

   Remplacez `path/to/known_faces` par le chemin de votre dossier de visages connus.

---

## 🖥️ **Utilisation**

* **Démarrage** : Exécutez le script avec un chemin valide vers les visages connus.
* **Fonctionnement** :

  * La webcam s’ouvre et détecte les visages en temps réel.
  * Les visages reconnus sont étiquetés avec leur nom (nom du fichier).
  * Les visages inconnus sont marqués "Unknown".
  * Les landmarks faciaux sont affichés en violet.
* **Arrêt** : Appuyez sur `q` pour quitter l’application.

---

## 🧩 **Architecture et Fonctionnement**

* **Détection** : `dlib.get_frontal_face_detector()` pour localiser les visages.
* **Encodage** : `dlib.face_recognition_model_v1` produit des vecteurs d’encodage.
* **Comparaison** : Comparaison via `np.linalg.norm` avec une tolérance (0.6).
* **Affichage** : `OpenCV` (`cv2`) affiche les rectangles et les noms.

---

## 📦 **Structure du Dépôt**

```
Easy-Facial-Recognition/
├── main.py                 # Script principal
├── pretrained_model/       # Dossier pour les modèles .dat
│   ├── shape_predictor_68_face_landmarks.dat
│   ├── shape_predictor_5_face_landmarks.dat
│   └── dlib_face_recognition_resnet_model_v1.dat
├── known_faces/            # Dossier pour les visages connus (à créer)
├── requirements.txt        # Liste des dépendances
└── README.md               # Ce fichier
```

---

## 🎥 **Démonstration**

* Ouvre une fenêtre webcam affichant les visages détectés.
* Les visages reconnus s'affichent avec leur nom, sinon "Unknown".
* Les points de repère sont dessinés sur les visages.

---

## 🤝 **Contribution**

Les contributions sont bienvenues !

1. Forkez le dépôt :

   ```bash
   git clone https://github.com/HaMzaCheh/Facial_Recognitions.git
   ```
2. Créez une branche :

   ```bash
   git checkout -b nouvelle-fonctionnalite
   ```
3. Soumettez une pull request après tests.

---

## 📄 **Licence**

Distribué sous **licence MIT**. Voir le fichier [LICENSE](LICENSE) pour plus d’informations.

---

## 👨‍💻 **Auteur**

* **Hamza CHEHAIBI**

---

## 🚧 **Améliorations Futures**

* 📥 Ajouter une interface graphique avec Tkinter.
* 🚀 Optimiser les performances (multithreading, traitement GPU).
* 🔐 Sécuriser les encodages par chiffrement ou hachage.

---

## 🙏 **Remerciements**

Merci d’avoir consulté ce projet !
N’hésitez pas à proposer des améliorations ou signaler des bugs via [Issues](https://github.com/HaMzaCheh/Facial_Recognitions/issues). 🎉

