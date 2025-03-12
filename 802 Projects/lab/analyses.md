---
id: lab-analysis-report
aliases: 
tags:
  - lab
  - 3eme-annee
  - project
---


# 📖 Dictionnaire de Données - Système de Gestion des Analyses Sanguines  

## 🩸 Table : Analyse  
| Nom de l'attribut  | Type         | Description |  
|--------------------|-------------|-------------|  
| `id_analyse`      | INT (PK)     | Identifiant unique de l'analyse |  
| `patient_id`      | INT (FK)     | Référence vers le patient concerné |  
| `doctor_id`       | INT (FK)     | Référence vers le médecin prescripteur |  
| `date_requested`  | DATE         | Date de la demande d'analyse |  
| `status`          | VARCHAR(20)  | Statut de l'analyse (En attente, Complétée, etc.) |  

---

## 🏥 Table : Numération Formule Sanguine (Blood Count Analysis)  
| Nom de l'attribut    | Type  | Description | Min | Max | Pourquoi cette analyse ? | Symptômes courants |  
|----------------------|------|-------------|----|----|----------------------|------------------|  
| `id_blood_count`     | INT (PK) | Identifiant unique | - | - | - | - |  
| `id_analyse`        | INT (FK) | Référence analyse | - | - | - | - |  
| `hemoglobin`        | FLOAT | Hémoglobine (g/dL) | 7.0 | 18.0 | Détecter l'anémie | Fatigue, pâleur, essoufflement |  
| `white_blood_cells` | FLOAT | Globules blancs (10^9/L) | 4.0 | 11.0 | Identifier les infections | Fièvre, frissons, inflammations |  
| `platelets`         | FLOAT | Plaquettes (10^9/L) | 150 | 450 | Vérifier la coagulation sanguine | Saignements fréquents, ecchymoses |  
| `hematocrit`        | FLOAT | Hématocrite (%) | 35.0 | 50.0 | Évaluer l’hydratation et l’anémie | Fatigue, déshydratation |  

---

## 🍔 Table : Bilan Lipidique (Lipid Panel)  
| Nom de l'attribut     | Type  | Description | Min | Max | Pourquoi cette analyse ? | Symptômes courants |  
|----------------------|------|-------------|----|----|----------------------|------------------|  
| `id_lipid_panel`      | INT (PK) | Identifiant unique | - | - | - | - |  
| `id_analyse`         | INT (FK) | Référence analyse | - | - | - | - |  
| `total_cholesterol`  | FLOAT | Cholestérol total (mg/dL) | 100 | 240 | Évaluer les risques cardiovasculaires | Douleurs thoraciques, fatigue |  
| `hdl_cholesterol`    | FLOAT | Bon cholestérol (mg/dL) | 40 | 80 | Protéger le cœur et les artères | - |  
| `ldl_cholesterol`    | FLOAT | Mauvais cholestérol (mg/dL) | 50 | 190 | Détecter les risques d'athérosclérose | Engourdissement, douleurs thoraciques |  
| `triglycerides`      | FLOAT | Triglycérides (mg/dL) | 50 | 200 | Vérifier les déséquilibres lipidiques | Prise de poids, fatigue |  

---

## 🏵 Table : Tests Hépatiques (Liver Function Test)  
| Nom de l'attribut | Type  | Description | Min | Max | Pourquoi cette analyse ? | Symptômes courants |  
|------------------|------|-------------|----|----|----------------------|------------------|  
| `id_liver_test` | INT (PK) | Identifiant unique | - | - | - | - |  
| `id_analyse`   | INT (FK) | Référence analyse | - | - | - | - |  
| `alt`         | FLOAT | Alanine Aminotransférase (U/L) | 7 | 55 | Détecter des dommages hépatiques | Fatigue, jaunisse |  
| `ast`         | FLOAT | Aspartate Aminotransférase (U/L) | 8 | 48 | Vérifier les atteintes hépatiques | Nausées, douleurs abdominales |  
| `bilirubin`   | FLOAT | Bilirubine (mg/dL) | 0.1 | 1.2 | Évaluer les problèmes biliaires | Urines foncées, peau jaunâtre |  
| `albumin`     | FLOAT | Albumine (g/dL) | 3.5 | 5.0 | Vérifier l’état nutritionnel | Œdèmes, fatigue chronique |  

---

## 🍬 Table : Test de Glycémie (Glucose Test)  
| Nom de l'attribut   | Type  | Description | Min | Max | Pourquoi cette analyse ? | Symptômes courants |  
|---------------------|------|-------------|----|----|----------------------|------------------|  
| `id_glucose_test`  | INT (PK) | Identifiant unique | - | - | - | - |  
| `id_analyse`       | INT (FK) | Référence analyse | - | - | - | - |  
| `fasting_glucose`  | FLOAT | Glycémie à jeun (mg/dL) | 70 | 99 | Détecter le diabète | Soif excessive, fatigue |  
| `hba1c`           | FLOAT | Hémoglobine glyquée (%) | 4.0 | 5.7 | Suivi du diabète à long terme | Vision floue, infections fréquentes |  

---

🗂 **Notes** :  
- Les valeurs minimales et maximales sont basées sur des références médicales générales et peuvent varier selon les laboratoires.  
- Chaque analyse est associée à un enregistrement dans la table `Analyse`.  

