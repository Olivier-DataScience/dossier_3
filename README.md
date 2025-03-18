# API de Scoring Crédit

Ce projet vise à développer une **API de scoring crédit** basée sur un modèle **LightGBM** entraîné sur les données de Home Credit.  
L'objectif est d’évaluer le risque de défaut de paiement d’un client en se basant sur 48 caractéristiques socio-économiques.

L’API permet de :
- Envoyer les données d'un client sous forme de requête `POST`.
- Obtenir une prédiction indiquant **si le client remboursera ou non** son crédit.
- Retourner **la probabilité associée** à la décision.


# Tester app.py :
uvicorn app:app --reload

lien :
http://127.0.0.1:8000/

Curl fonctionelle :
curl -X POST "http://127.0.0.1:8000/predict" -H "Content-Type: application/json" -d "{\"CNT_CHILDREN\": 1, \"CNT_FAM_MEMBERS\": 2, \"CODE_GENDER_F\": 1, \"CODE_GENDER_M\": 0, \"FLAG_OWN_CAR_Y\": 0, \"FLAG_OWN_CAR_N\": 1, \"FLAG_OWN_REALTY_Y\": 1, \"FLAG_OWN_REALTY_N\": 0, \"NAME_FAMILY_STATUS_Married\": 1, \"NAME_FAMILY_STATUS_Single_not_married\": 0, \"NAME_FAMILY_STATUS_Widow\": 0, \"AMT_INCOME_TOTAL\": 180000, \"AMT_CREDIT\": 600000, \"AMT_ANNUITY\": 25000, \"AMT_GOODS_PRICE\": 540000, \"INCOME_CREDIT_PERC\": 0.3, \"ANNUITY_INCOME_PERC\": 0.14, \"PAYMENT_RATE\": 0.02, \"DAYS_BIRTH\": -12000, \"DAYS_EMPLOYED\": -3000, \"DAYS_EMPLOYED_PERC\": 0.25, \"DAYS_REGISTRATION\": -4000, \"DAYS_ID_PUBLISH\": -2000, \"NAME_EDUCATION_TYPE_Higher_education\": 1, \"NAME_EDUCATION_TYPE_Secondary_secondary_special\": 0, \"NAME_EDUCATION_TYPE_Lower_secondary\": 0, \"OCCUPATION_TYPE_Accountants\": 1, \"OCCUPATION_TYPE_Core_staff\": 0, \"OCCUPATION_TYPE_Laborers\": 0, \"OCCUPATION_TYPE_Managers\": 0, \"OCCUPATION_TYPE_Sales_staff\": 0, \"EXT_SOURCE_2\": 0.7, \"EXT_SOURCE_3\": 0.5, \"AMT_REQ_CREDIT_BUREAU_YEAR\": 0, \"AMT_REQ_CREDIT_BUREAU_MON\": 0, \"AMT_REQ_CREDIT_BUREAU_QRT\": 0, \"OBS_30_CNT_SOCIAL_CIRCLE\": 2, \"DEF_30_CNT_SOCIAL_CIRCLE\": 0, \"OBS_60_CNT_SOCIAL_CIRCLE\": 1, \"DEF_60_CNT_SOCIAL_CIRCLE\": 0, \"REGION_POPULATION_RELATIVE\": 0.02, \"REGION_RATING_CLIENT\": 2, \"REGION_RATING_CLIENT_W_CITY\": 1, \"DAYS_LAST_PHONE_CHANGE\": -500, \"FLAG_PHONE\": 0, \"FLAG_EMAIL\": 1, \"FLAG_EMP_PHONE\": 1, \"FLAG_WORK_PHONE\": 0}"

# # Structure des fichiers

Le projet est organisé comme suit :

Guillaud_Olivier_3_dossier_code_022025/ 
│── api.py # Script FastAPI de l'API de scoring 
│── requirements.txt # Liste des dépendances Python 
│── README.md #Ce fichier 
├── Guillaud_Olivier_2_notebook_modélisation_022025.ipynb # Notebook de modélisation 
├── best_lightgbm_model.pkl # Modèle entraîné