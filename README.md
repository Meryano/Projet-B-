# Projet-B-

<img width="386" alt="image" src="https://github.com/Meryano/Projet-B-/assets/148442282/472ae51f-247c-4fc6-8a2e-44a5136694ba">


Le but de ce projet est la création d'un système capable de compter des composants électroniques en s'appuyant sur la reconnaissance et la classificattion d'image. Le dispositif utilisé est composé:
        - d'une carte Arduino Nano 33 BLE
        - une camera OV7670
        - une plateforme Edge Impulse
        - l'outil de programmation Nodered
Les composants à compter ici, sont placés sur un espace de travail et défilent de manière individuelle toutes les deux secondes. Le système de reconnaissance se fait grace à un modèle de deep learning entrainé au préalable avec TensorFlowLite ou Edge Impulse

<img width="399" alt="image" src="https://github.com/Meryano/Projet-B-/assets/148442282/1b37f899-2477-4971-b423-ec5cb076a016">

Après la classification, les données sont transmises via Bluetooth Low Energy (BLE) vers Node-RED, qui est responsable de les compter et de les présenter sur un tableau de bord interactif.


**DIFFERENTES ETAPES DE REALISATION DU PROJET**

**1- Utilisation d'Edge Impulse pour effectuer la classification d'image**

Edge Impulse est une plate-forme qui simplifie le processus de création de modèles d’apprentissage automatique en choisissant des valeurs par défaut raisonnables pour les innombrables paramètres que nous pouvons définir lors de la création d’un modèle ML. Pour entraîner un modèle ML à classifier une image, nous devons l’alimenter avec les données d’image de cet objet. Au cours du processus d’apprentissage, le modèle sera entraîné à l’aide d’un concept appelé apprentissage supervisé.

      -->  Exploitation du modèle issu du projet 4
      
<img width="562" alt="image" src="https://github.com/Meryano/Projet-B-/assets/148442282/c8f668ec-98cd-416d-a925-38f22bfe49fd">

      -->  Chargement du modèle entraîné sur la carte Arduino Nano 33 BLE

<img width="472" alt="image" src="https://github.com/Meryano/Projet-B-/assets/148442282/a815a5e0-df61-4b9c-a205-3d8745d608c6">

      -->  Mise en œuvre d'un programme utilisant la caméra OV7670 pour capturer des images des composants
<img width="528" alt="image" src="https://github.com/Meryano/Projet-B-/assets/148442282/3f998ff6-80fe-4ab4-8ce8-f77d4c3d4928">

      -->  Mise en place d'un programme pour capturer des images avec la caméra OV7675, effectuer l'inférence avec le modèle Edge Impulse, puis envoyer la classe identifiée via Bluetooth en utilisant BLE
       Je n'ai pas pu réaliser cette partie car le port USB de ma carte Arduino ne fonctionnait pas


**2- Utilisation de Nodered pour le traitement de données**

Le tableau de bord Node-RED est un module qui fournit un ensemble de nœuds dans Node-RED pour créer rapidement un tableau de bord de données en direct.

      -->   Téléchargement des bibliothèques
      
<img width="366" alt="image" src="https://github.com/Meryano/Projet-B-/assets/148442282/ebfeaad5-f06e-4f16-b6ec-4a16b6809856">

      -->  Création d'un flux pour recevoir les données BLE
      
<img width="533" alt="image" src="https://github.com/Meryano/Projet-B-/assets/148442282/51711c84-107c-449f-b910-b698d8492dbf">

<img width="533" alt="image" src="https://github.com/Meryano/Projet-B-/assets/148442282/6a9f5bf4-4f83-4cf7-8398-960c769c33c4">

<img width="533" alt="image" src="https://github.com/Meryano/Projet-B-/assets/148442282/ccbb8058-92b8-4db7-9617-355774e066d6">


**3- Connexion de la carte Arduino Nano 33BLE avec le Bluetooth**

Il s'agit de réaliser l'échange d'informations entre deux cartes Arduino, la Nano 33 BLE et la Nano 33 BLE Sense, via Bluetooth Low Energy.
L’une des cartes, la Nano 33 BLE Sense, sera configurée en tant qu’appareil central tandis que l’autre carte, la Nano 33 BLE, sera configurée en tant que périphérique. Les informations que nous allons partager entre les cartes proviendront du capteur gestuel embarqué de la carte Nano 33 BLE Sense.
Pour ce faire, nous devons créer un service appelé gestureService qui aura une caractéristique appelée gesture_type. L’appareil central, le Nano 33 BLE Sense, va se connecter à l’appareil périphérique, le Nano 33 BLE, et recherchera le service appelé gestureService. Une fois qu’une connexion est établie entre le périphérique central et le périphérique, si le périphérique central détecte un geste avec son capteur de geste, il écrira le type du geste détecté dans la caractéristique gesture_type du gestureService. 
Les codes pour le test de l'appareil central et l'appareil périphérique sont dans les fichiers joints au projet.

Je n'ai pas pu terminer cette partie car le port USB de ma carte Arduino ne fonctionnait pas





    


      





