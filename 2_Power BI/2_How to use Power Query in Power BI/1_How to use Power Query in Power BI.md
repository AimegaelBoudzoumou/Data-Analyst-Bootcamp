# How to use Power Query in Power BI

This is the tutorial : [How to use Power Query in Power BI](https://www.youtube.com/watch?v=gP-AxNi6uxo&list=PLUaB-1hjhk8FE_XZ87vPPSfHqb6OcM0cF&index=35&t=8s)

### 1. Supprimer les deux premières lignes 
Faire : _Accueil -> Supprimer les lignes_
![image](https://github.com/user-attachments/assets/ebdf1060-4f6c-4c10-a301-e38d82c67929)

### 2. Transformer la première ligne pour qu'elle soit considérée comme en-tête 
Faire : _Transformer -> Utiliser la première ligne pour les en-têtes_

Avant :
![image](https://github.com/user-attachments/assets/c29af5e4-7e50-4e01-abea-94fb75271429)

Après : 
![image](https://github.com/user-attachments/assets/a4e0f6fb-1846-469d-90d9-244641427471)

### 3. Transformer les type de colonnes : de "Nombre décimal" vers "Nombre décimal fixe"

Avant :
![image](https://github.com/user-attachments/assets/479a7209-f84f-47fe-a35e-4f5d2e5a9e55)

Après : 
![image](https://github.com/user-attachments/assets/41fd1fe6-6199-4650-9392-c7c5fbfef112)

### 3. Supprimer les lignes ayant la valeur _null_ dans la colonne Location

Méthode 1 : Location -> Supprimer les éléments vides

Avant :
![image](https://github.com/user-attachments/assets/27dd237c-6fdc-4272-96b2-cf06fa0012a2)

Méthode 2 : Products -> Filtres textuels -> Ne contient pas...
Avant :
![image](https://github.com/user-attachments/assets/c1058da4-d678-44de-841e-8dc4f9412390)

Après : 
![image](https://github.com/user-attachments/assets/80e4e8e8-553a-42d0-9e91-6d994c8d1670)

### 4. Supprimer la colonne "Grand Total"
Sélectionner la colonne puis Faire : _Accueil -> Supprimer les colonnes_

Avant : 
![image](https://github.com/user-attachments/assets/54d638f9-e75c-40ef-a505-c6f708d361e3)

Après : 
![image](https://github.com/user-attachments/assets/5b7ff4a9-5de0-4e88-a82a-035e4354cd49)

### 5. Pivoter/Dépivoter les colonnes : échanger les lignes et les colonnes. Objectif : Faire en sorte d'avoir le moins de colonnes possibles, pour ensuite les injecter dans les visuels.

Exemple : 
![image](https://github.com/user-attachments/assets/d109f676-d06d-4ba9-b9ad-0a5ffe1ec08d)

Séléctionner les colonnes puis Faire : _Transformer -> Dépivoter les colonnes_

Avant :
![image](https://github.com/user-attachments/assets/326b27b0-58dc-44f1-8944-a4c326a93d8e)

Après : 
![image](https://github.com/user-attachments/assets/29cc1035-d8bc-46fa-b4a9-b935f8fd7b43)

Sur la fenêtre ci-dessus : faire __Fermer & appliquer__ pour sauvegarder le travail.

On se retrouve sur la page suivante. Pour repartir dans __Power Query__, on clique sur __Transformer les données.__
