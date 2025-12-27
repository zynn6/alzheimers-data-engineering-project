# alzheimers-data-engineering-project
Raw hospital dataset for AI data cleaning and messaging system
import pandas as pd
import numpy as np

data = {
    "patient_id": [
        # Existing 18
        101,102,103,104,105,106,107,108,109,110,111,112,113,114,
        101,104,108,110,
        # New 20
        115,116,117,118,119,120,121,122,123,124,
        125,126,127,128,129,130,131,132,133,134
    ],
    "patient_name": [
        "Ahmad Ali","Salma Noor","Khaled Omar","Fatima Hassan",
        "Yousef Amin","Lina Mahmoud","Omar Saleh","Nour Hasan",
        "Rami Adel","Huda Yasin",None,"Maha Khalil",
        "Samir Farouq","Dana Zaid",
        "Ahmad Ali","Fatima Hassan","Nour Hasan","Huda Yasin",

        "Ibrahim Naji","Sara Fawzi","Adel Mansour","Reem Khalaf",
        "Fadi Awad","Hanan Odeh","Nabil Qasem","Yara Saeed",
        None,"Ziad Hamdan",
        "Noor Jaber","Bilal Shami","Alaa Khatib","Mona Faris",
        "Hussein AbuZaid","Rasha Salem","Majed Rafi","Samar Eid",
        "Tamer Qadi","Layla Saqr"
    ],
    "age": [
        72,68,80,65,74,45,32,58,29,None,40,61,55,34,
        72,65,None,52,

        66,59,83,47,71,64,None,38,
        90,56,42,67,60,None,
        75,33,69,58,81,44
    ],
    "diagnosis": [
        "Alzheimer","Alzheimer",None,"Alzheimer",
        "None","None","Diabetes","None",
        "None","Hypertension","None","None",
        "Asthma",None,
        "Alzheimer","Alzheimer","None","Hypertension",

        "Alzheimer","None","Alzheimer","None",
        "None","Alzheimer","Diabetes","None",
        "Alzheimer","None","None","Alzheimer",
        "None",None,
        "Alzheimer","None","Hypertension","None",
        "Alzheimer","None"
    ],
    "medication_name": [
        "Donepezil","Memantine","Amlodipine","Donepezil",
        "Metformin","Ibuprofen",None,"Vitamin D",
        "Paracetamol","Losartan","Vitamin C",None,
        "Salbutamol","Iron",
        "Donepezil","Donepezil","Vitamin D","Losartan",

        "Donepezil","Vitamin D","Memantine","Ibuprofen",
        "Metformin","Donepezil","Insulin","Calcium",
        None,"Aspirin","Vitamin B12","Donepezil",
        "Atorvastatin",None,
        "Memantine","Iron","Losartan","Vitamin D",
        "Donepezil","Paracetamol"
    ],
    "medication_time": [
        "08:00","20:00",None,"08:00",
        "07:30","12:00","08:00",None,
        "14:00","09:30","11:00","08:30",
        None,"13:00",
        "08:00",None,"10:00","09:30",

        "08:00","10:00","20:00","12:00",
        None,"08:00","07:00","09:00",
        "08:30",None,"11:00","08:00",
        "21:00",None,
        "19:00","13:00","09:30","10:30",
        "08:00","14:00"
    ],
    "medication_start_datetime": [
        "2025-01-01 08:00","2025-01-05 20:00",None,"2025/01/03 08:00",
        "2025-01-10 07:30","2025-01-12 12:00",None,"2025-01-15 10:00",
        "2025-01-20 14:00",None,"2025-01-18 11:00","2025-01-25 08:30",
        None,"2025-01-30 13:00",
        "2025-01-01 08:00",None,"2025-01-15 10:00","2025-01-18 09:30",

        "2025-02-01 08:00","2025-02-03 10:00","2025-02-05 20:00",
        "2025-02-07 12:00","2025-02-10 07:30",
        "2025-02-12 08:00","2025-02-14 07:00",
        None,"2025-02-16 08:30",None,
        "2025-02-18 11:00","2025-02-20 08:00",
        "2025-02-22 21:00",None,
        "2025-02-24 19:00","2025-02-26 13:00",
        "2025-02-28 09:30","2025-03-01 10:30",
        "2025-03-03 08:00","2025-03-05 14:00"
    ],
    "medication_end_date": [
        "2025-06-01","2025-06-05","2025-03-15",None,
        "2025-04-10","2025-02-12",None,"2025-05-15",
        None,"2025-06-30","2025-03-18",None,
        "2025-04-01","2025-02-28",
        "2025-06-01",None,"2025-05-15","2025-06-30",

        "2025-07-01","2025-04-03","2025-08-05",
        "2025-03-07","2025-06-10","2025-07-12",
        None,"2025-05-01",
        None,"2025-04-30","2025-06-18","2025-08-20",
        "2025-09-22",None,
        "2025-07-24","2025-04-26","2025-06-28",
        None,"2025-08-03","2025-05-05"
    ],
    "risk_level": [
        "High","Medium","Low","High",
        None,"Low","Medium","Low",
        "Low","Medium","Low",None,
        "Medium","Low",
        "High","High","Low","Medium",

        "High","Low","High","Low",
        "Medium","High","Medium","Low",
        "High","Low","Low","High",
        "Medium",None,
        "High","Low","Medium","Low",
        "High","Low"
    ],
    "consent_given": [
        True,True,True,True,
        False,True,True,True,
        True,None,True,True,
        True,True,
        True,True,True,None,

        True,True,True,True,
        False,True,True,True,
        True,True,True,True,
        True,None,
        True,True,True,True,
        True,True
    ],
    "email_provided": ["No Email"] * 38
}

raw_patients_df = pd.DataFrame(data)

raw_patients_df
