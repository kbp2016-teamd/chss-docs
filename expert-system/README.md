# CHSS Expert Medical System

## Overview
The CHSS project relies on the assumption that community healthcare
workers will be basically skilled to perform essential medical
diagnostics to test for a variety of common, serious ailments. This
is as a preventative measure to help prevent serious issues later
on, as well as a means to assist with decongesting healthcare
facilities further downstream.

In order to support this, the system requires an
[expert system](https://en.wikipedia.org/wiki/Expert_system) to aid
the community healthcare worker in diagnosing the likely issues a
patient is facing, and whether or not they need to visit the clinic.

## Prevalent Health Issues
As per the [leading causes of death in South Africa](http://www.statssa.gov.za/?page_id=737&id=3)
(data from Stats SA), the following diseases are targeted for the
minimum viable product (MVP) CHSS:

1. Infectious and parasitic diseases, such as tuberculosis and HIV.
2. Circulatory system diseases, such as heart disease and strokes.
3. Respiratory diseases, such as influenza and pneumonia.

These issues accounted for approximately 40% of all deaths in
South Africa in 2013.

## Questions
### Personal Information
The following personal information needs to be asked of a user when
they are first enrolled into the system:

| Field | Type | Details/Notes |
| ----- | ---- | ------------- |
| First name | `string` |   |
| Last name | `string` |   |
| ID number | `string` | The patient's ID number |
| Address | `string` | Where the patient lives |
| Gender | `char` | `m` or `f` |
| Date of birth | `date` | Used to determine patient's age |
| Weight | `number` | The patient's measured weight, in kilograms |
| Height | `number` | The patient's height, in metres |

### Evaluation Questions
The following questions should be asked of a patient for each
separate evaluation.

| ID  | Type | Question | Details/Notes |
| --- | ---- | -------- | ------------- |
| `temp` | `number` | What is the patient's temperature? | To be taken by oral thermometer |
| `syst-blood-pressure` | `number` | Systolic blood pressure? | Taken by blood pressure cuff |
| `dia-blood-pressure` | `number` | Diastolic blood pressure? | Taken by blood pressure cuff |
| `cough` | `bool` | Does the patient have a cough? | |
| `cough-blood` | `bool` | Is the patient coughing blood? | |
| `sweats` | `bool` | Does the patient experience sweating or night sweats? | |
| `fatigue` | `bool` | Is the patient tired often? | |
| `weakness` | `bool` | Is the patient feeling weak? | |
| `weight-loss` | `bool` | Has the patient lost an unusual amount of weight? | |
| `chest-pain` | `bool` | Does the patient experience chest pain? | |
| `shortness-of-breath` | `bool` | Does the patient experience shortness of breath? | |
| `skin-rash` | `bool` | Does the patient have a widespread skin rash? | |
| `muscle-ache` | `bool` | Does the patient experience muscle ache? | |
| `joint-pain` | `bool` | Does the patient experience joint pain? | |
| `diarrhea` | `bool` | Does the patient have diarrhea? | |
| `swollen-lymph` | `bool` | Does the patient have swollen lymph nodes? | |
| `palpitations` | `bool` | Does the patient experience heart palpitations? | |
| `heartburn` | `bool` | Does the patient often have heartburn? | |
| `weight-gain` | `bool` | Has the patient gained a large amount of weight quickly? (1-2kgs) | |
| `nausea` | `bool` | Does the patient experience nausea? | |
| `paralysis` | `bool` | Does the patient experience sudden paralysis? | |
| `numbness` | `bool` | Does the patient experience numbness in the face/arm/leg? | |
| `blurred-vision` | `bool` | Is the patient's vision blurred? | |
| `dizziness` | `bool` | Is the patient feeling dizzy? | |
| `loss-of-balance` | `bool` | Has the patient lost sense of balance? | |
| `vomiting` | `bool` | Is the patient vomiting? | |
| `chills` | `bool` | Does the patient experience chills? | |
| `sore-throat` | `bool` | Does the patient have a sore throat? | |
| `dry-cough` | `bool` | Does the patient have a dry cough? | |
| `sneezing` | `bool` | Is the patient sneezing? | |
| `headache` | `bool` | Does the patient have a headache? | |
| `congestion` | `bool` | Does the patient experience sinus congestion? | |

### Possible Conditions
Each of the following possible conditions have associated symptoms based
on the patient's answers to the evaluation questions and their
demographic profile.

| Condition | Primary Symptom(s) | Supporting Symptom(s) |
| --------- | ------------------ | --------------------- |
| **Tuberculosis** | `temp` > 37.7, `cough` | `cough-blood`, `sweats`, `fatigue`, `weakness`, `weight-loss`, `chest-pain` |
| **Early-Stage HIV** | `temp` > 37.7, `skin-rash` | `muscle-ache`, `joint-pain`, `diarrhea`, `swollen-lymph` |
| **High Blood Pressure** | `syst-blood-pressure` > 140 OR `dia-blood-pressure` > 90 | |
| **Heart Disease** | `chest-pain` | `heartburn`, `shortness-of-breath`, `palpitations`, `weakness`, `nausea`, `sweats` |
| **Stroke** | `paralysis` | `numbness`, `blurred-vision`, `dizziness`, `loss-of-balance` |
| **Pneumonia** | `temp` > 37.7, `cough` | `cough-blood`, `chills`, `chest-pain`, `weakness`, `fatigue`, `nausea`, `vomiting` |
| **Flu** | `temp` > 37.7 | `sore-throat`, `dry-cough`, `sneezing`, `congestion`, `headache`, `chills`, `muscle-ache`, `fatigue`, `weakness` |

The questions for **Primary Symptoms** should always be asked, but
questions for **Supporting Symptoms** should only be asked if the
relevant criteria are met for primary symptoms.

For example, if the patient's `temp` > 37.7 and `cough` = `true`,
then only ask the remaining questions regarding **Tuberculosis**.
