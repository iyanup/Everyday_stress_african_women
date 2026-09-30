# Dataset Card: Everyday Stress Survey for African Women

## 1. Dataset Overview

**Dataset title:** Everyday Stress Survey for African Women  
**Dataset type:** Primary survey data  
**Data format:** CSV  
**Number of records:** 24  
**Data collection method:** Online questionnaire  
**Data content:** Structured and open-ended written responses about experiences of stress, common stressors, effects of stress, coping strategies, and support needs.

This dataset was collected as part of a class exercise on primary data collection, preprocessing, validation, documentation, and responsible data sharing.

---

## 2. Data Collection

The data were collected using an online survey designed to gather information about everyday experiences of stress among adult women.

The questionnaire included questions about:

- Age group
- Country of residence
- Residential setting
- Occupation
- Recent stressful experiences
- Effects of stress
- Places where stress is commonly experienced
- Frequency of stressful experiences
- Common daily stressors
- Coping strategies
- Support needed

A total of **24 responses** were collected.

### Ethical Considerations

Participants were informed about the purpose of the survey and provided consent before submitting their responses. The dataset was reviewed to minimise the inclusion of personally identifying information.

The public version does not contain:

- Names
- Email addresses
- Telephone numbers
- Survey submission timestamps
- Individual consent responses

Anonymous record IDs were assigned to the final dataset.

---

## 3. Preprocessing

The dataset was processed using five main preprocessing steps.

### 3.1 Cleaning

Cleaning was performed to remove errors, irrelevant information, and potentially identifying content.

The following actions were taken:

- Removed the timestamp field from the public dataset.
- Removed the consent field after verifying that all respondents had consented.
- Removed unnecessary leading and trailing spaces.
- Corrected an obvious typographical error: `Take a day off to restCos` → `Take a day off to rest`.
- Standardised an unclear residence response as `Unclear response`.
- Privacy-reduced one unusually detailed clinical narrative while retaining its general meaning.

### 3.2 Normalisation

Responses were made more consistent without changing their intended meaning.

Examples include:

- `About once a week` → `Once a week`
- `I do not understand the options.` → `Unclear response`
- Repeated spaces were standardised.
- The dataset was saved using UTF-8 encoding.

The original meaning of participants' qualitative responses was preserved.

### 3.3 Deduplication

The dataset was checked for repeated records.

- Duplicate records identified: **0**
- Duplicate records removed: **0**

Therefore, all 24 records were retained.

### 3.4 Formatting

The cleaned dataset was formatted as a UTF-8 encoded CSV file.

Anonymous identifiers were added:

`S001, S002, ..., S024`

The dataset therefore has a consistent structure that can be read by common data-analysis and machine-learning tools.

### 3.5 Splitting

For educational model-development purposes, the dataset was divided into:

| Subset | Number of records |
|---|---:|
| Training | 17 |
| Validation | 4 |
| Test | 3 |
| **Total** | **24** |

A fixed random seed of 42 was used to make the split reproducible.

Because the dataset is small, these splits should be considered suitable for classroom experimentation rather than for making statistically reliable claims about model performance.

---

## 4. Validation

Both manual and automatic validation were performed.

### Manual Validation

The responses were reviewed for:

- Obvious typing errors
- Inconsistent categorical responses
- Empty responses
- Unclear responses
- Potentially identifying information
- Repeated records
- Whether preprocessing changed the intended meaning of responses

Errors identified during manual review were corrected during preprocessing.

### Automatic Validation

The processed dataset was checked programmatically for:

- Missing values
- Duplicate records
- Unique record IDs
- Email-address patterns
- Telephone-number patterns
- Consistent dataset structure

### Validation Results

- Records after preprocessing: **24**
- Missing cells: **0**
- Duplicate records: **0**
- Unique record IDs: **Yes**
- Obvious email addresses detected: **0**
- Obvious telephone numbers detected: **0**

---

## 5. Dataset Variables

| Variable | Description |
|---|---|
| `record_id` | Anonymous identifier assigned to each response |
| `age_group` | Age category of the respondent |
| `country` | Country of residence |
| `residence` | Broad residential setting |
| `occupation` | Occupational category |
| `stress_event` | Description of a recent stressful or overwhelming experience |
| `stress_effects` | Reported effects or reactions to the stressful experience |
| `stress_location` | Place/context where stress is experienced most often |
| `stress_frequency` | Frequency of stressful experiences |
| `daily_stressors` | Reported sources of everyday pressure |
| `coping_strategy` | Strategy used to manage stress |
| `support_needed` | Support identified by the respondent as potentially helpful |

---

## 6. Intended Use

The dataset is intended for:

- Classroom exercises in dataset preparation
- Data cleaning and preprocessing demonstrations
- Exploratory data analysis
- Qualitative text analysis
- Introductory natural language processing exercises
- Demonstrations of responsible AI and data management

---

## 7. Limitations

The dataset contains only **24 responses** and is a small convenience sample. It should not be considered representative of African women generally.

The responses are self-reported and reflect the individual experiences of the participants who completed the survey.

The dataset should **not** be used to:

- Make clinical diagnoses
- Estimate the prevalence of stress among African women
- Generalise findings to the entire African population
- Make decisions about individual participants

The small sample size also limits the reliability of machine-learning performance evaluation.

---

## 8. Privacy and Responsible Use

The dataset contains sensitive qualitative information concerning personal experiences, work, finances, relationships, family responsibilities, and stress.

Users should:

- Avoid attempting to identify participants.
- Not combine the dataset with other information for re-identification.
- Use the data only for legitimate educational or research purposes.
- Avoid publishing verbatim responses in contexts where they could reveal participant identity.
- Treat the dataset as sensitive even though direct identifiers have been removed.

---

## 9. Files

The repository contains the following main files:

- `Everyday_Stress_African_Women_Cleaned_Formatted.csv` — final cleaned dataset.
- `README.md` — this Dataset Card.
- `train.csv` — training subset.
- `validation.csv` — validation subset.
- `test.csv` — test subset.

---

## 10. Citation

Adegun, I. P. (2026). *Everyday Stress Survey for African Women: Anonymised Primary Survey Dataset*. GitHub repository.

---

## 11. License

The dataset should be shared under a licence appropriate to the course requirements and the consent obtained from participants. If no specific licence has been provided by the course instructor, the dataset should be treated as restricted educational/research data rather than assumed to be freely reusable.
