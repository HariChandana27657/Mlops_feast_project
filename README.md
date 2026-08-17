# Mlops_feast_project
# Curriculum–Industry Skill Feature Store Using Feast

## 1. Student Details

**Name:**  Naga Sai Hari Chandana Karumanchi
**Register Number:**  231FA04H02
**Section:** 15

 

## 2. Project Overview

This project focuses on building a simple **feature store using Feast** for a curriculum–industry skill-gap dataset.

The main idea behind the project is to understand the difference between the skills students learn through their curriculum and the skills that are expected in the industry. Instead of directly using the original dataset every time, I created useful features from the dataset and managed those features using Feast.

Through this project, I worked with the complete basic workflow of a feature store, starting from the original dataset and feature engineering, followed by Feast registration, historical feature retrieval, materialization, online feature retrieval, and finally using the retrieved features in a simple machine-learning model.

The assignment helped me understand how a feature store can keep features organized and make the same features available during both model training and prediction.

---

## 3. Problem Statement

There can be a gap between the skills included in an academic curriculum and the skills that are commonly required in the industry.

For example, a student may learn programming fundamentals, databases, or basic machine learning as part of their curriculum, while industry requirements may also include skills such as cloud computing, DevOps, data engineering, MLOps, or other practical technologies.

The purpose of this project is to represent this skill gap using a dataset and then create meaningful features from the dataset. These features are stored and managed using **Feast**, which acts as the feature store.

The final goal is to retrieve these features for machine-learning training as well as for prediction.

---

## 4. Objectives

The main objectives of this project are:

* Create a curriculum–industry skill-gap dataset.
* Perform feature engineering on the dataset.
* Create an entity in Feast.
* Create a Feast data source.
* Create a FeatureView.
* Register the features using `feast apply`.
* Retrieve historical features.
* Materialize features into the online store.
* Retrieve features from the online store.
* Use Feast features in a simple machine-learning model.
* Document the complete implementation in GitHub.

These objectives follow the requirements given in the assignment.

---

## 5. Dataset

The dataset used in this project represents the skills related to the curriculum and industry requirements.

### Dataset Information

**Number of skills:** `<Enter number of skills>`

**Dataset columns:**

| Column       | Description                      |
| ------------ | -------------------------------- |
| `<Column 1>` | `<Description>`                  |
| `<Column 2>` | `<Description>`                  |
| `<Column 3>` | `<Description>`                  |
| `<Column 4>` | `<Description>`                  |
| `<Target>`   | Target value used for prediction |

### Target

The target column used in the machine-learning model is:

**Target:** `<Enter target column name>`

The target represents `<briefly explain what the target means>`.

### How the Dataset Was Created

The entries in the dataset were created based on the curriculum–industry skill-gap information prepared in the previous activity.

For each skill, relevant information was recorded so that it could later be transformed into useful machine-learning features.

The original dataset is mainly used as the starting point. After feature engineering, the required features are stored in a format that can be consumed by Feast.

---

# 6. Feature Engineering

Feature engineering is the process of converting the original dataset into useful numerical or categorical information that can be used by a machine-learning model.

In this project, I selected the important columns from the original skill-gap dataset and created features that represent the curriculum and industry requirements.

### Features Used in Feast

| Feature       | Meaning     |
| ------------- | ----------- |
| `<feature_1>` | `<Meaning>` |
| `<feature_2>` | `<Meaning>` |
| `<feature_3>` | `<Meaning>` |
| `<feature_4>` | `<Meaning>` |
| `<feature_5>` | `<Meaning>` |

> Replace the above placeholders with the exact features used in your implementation.

### Example of Feature Calculation

One of the features was calculated from the original dataset by `<explain your actual calculation here>`.

For example, if a skill has a curriculum score and an industry requirement score, the skill-gap value can be represented as:

`Skill Gap = Industry Requirement Score - Curriculum Score`

This gives a simple way of identifying whether a skill has a higher industry requirement compared with its curriculum coverage.

The exact calculation should match the feature-engineering code used in the project.

---

# 7. Difference Between Original Dataset and Feature Dataset

The **original dataset** contains the information collected for the curriculum–industry skill-gap problem.

The **feature dataset** is a processed version of the original data. It contains the features required by the machine-learning model and is prepared in a form that can be used by Feast.

In simple terms:

**Original Dataset → Feature Engineering → Feature Dataset → Feast**

The feature dataset is therefore more focused on the values required for training and prediction.

---

# 8. Feast Architecture

The overall workflow of this project is:

```text
Original Dataset
       ↓
Feature Engineering
       ↓
Parquet Offline Data
       ↓
Feast FeatureView
       ↓
 ┌─────────────────────────┐
 ↓                         ↓
Historical Retrieval    Materialization
 ↓                         ↓
Model Training          Online Store
                           ↓
                    Online Retrieval
                           ↓
                       Prediction
```

This architecture shows how the same features can be used for both historical model training and online prediction.

---

# 9. Why Feast?

Feast is used as the feature store in this project.

Without a feature store, we may have to manually calculate and manage features separately during model training and prediction. This can result in duplicated code and differences between the features used during training and those used during prediction.

With Feast, the features are defined in one place and can be retrieved when required.

For this project, Feast provides:

* Historical feature retrieval.
* Online feature retrieval.
* Feature registration.
* Feature management through FeatureViews.
* Local development using file-based offline data.
* SQLite as the online store.

These capabilities are specifically relevant to the assignment requirements.

---

# 10. Feast Entity

The entity represents the object for which the features are stored.

In this project, the entity is:

**Entity:** `<Enter your entity name>`

For example, if each record represents a particular skill, the entity could be based on a unique skill identifier.

The entity helps Feast understand which feature values belong to which record.

---

# 11. Feast Data Source

The processed feature data is stored as an offline data source.

**Data Source:** `<Enter your data source name/path>`

The feature data is stored in Parquet format and is connected to Feast through the data source configuration.

The data source provides Feast with the location of the data from which historical features can be retrieved.

---

# 12. Feast FeatureView

A **FeatureView** defines the features that Feast manages for a particular entity.

The FeatureView created in this project contains the features generated during the feature-engineering stage.

### FeatureView

**Name:** `<Enter FeatureView name>`

**Entity:** `<Enter entity name>`

**Features:**

* `<feature_1>`
* `<feature_2>`
* `<feature_3>`
* `<feature_4>`
* `<feature_5>`

The FeatureView acts as the main connection between the feature definitions and the Feast data source.

---

# 13. Registering Features Using `feast apply`

After defining the entity, data source, and FeatureView, the configuration was registered using:

```bash
feast apply
```

The `feast apply` command reads the Feast configuration and registers the defined entities, data sources, and FeatureViews.

After successful execution, the feature definitions become available to Feast for further operations.

---

# 14. Historical Feature Retrieval

Historical feature retrieval is required when preparing data for model training.

In this project, historical features were retrieved using Feast's:

```python
get_historical_features()
```

The purpose of historical retrieval is to obtain the feature values associated with the required historical records and timestamps.

### Historical Feature Output

```text
<Insert your actual historical feature output here>
```

A screenshot of the historical feature retrieval output can also be added here.

**Screenshot:**

`<Insert screenshot here>`

---

# 15. Offline Store

The offline store is used for storing and retrieving historical feature data.

In this project, the processed feature data is stored in a file-based format and used for historical feature retrieval.

The offline store is mainly useful during model training because training usually requires historical data rather than only the latest feature values.

---

# 16. Materialization

Materialization is the process of moving feature values from the historical/offline data into the online store.

In this project, materialization was performed so that the latest feature values could be accessed quickly during online prediction.

The basic idea is:

```text
Offline Data
     ↓
Materialization
     ↓
Online Store
```

After materialization, the features are available for online retrieval.

---

# 17. Online Store

The online store is used to provide feature values for real-time or near-real-time prediction.

For local development in this project, SQLite is used as the online store.

The online store contains the materialized feature values and allows the application to retrieve features using the entity value.

---

# 18. Online Feature Retrieval

After materialization, the features were retrieved using Feast's:

```python
get_online_features()
```

The online retrieval process gets the required feature values for a particular entity.

### Online Feature Output

```text
<Insert your actual online feature output here>
```

**Screenshot:**

`<Insert screenshot here>`

---

# 19. Machine-Learning Model

The retrieved Feast features were used as input to a simple machine-learning model.

### Model Used

**Algorithm:** `<Enter model name>`

Examples include:

* Logistic Regression
* Decision Tree
* Random Forest
* Linear Regression

Use the model that was actually implemented in the project.

### Input Features

The model receives the features retrieved from the Feast feature store.

```text
Feast Features
      ↓
Machine-Learning Model
      ↓
Prediction
```

The main purpose of this step is to demonstrate that features managed by Feast can actually be used in a machine-learning workflow.

---

# 20. Model Training

The historical features retrieved from Feast were used to train the machine-learning model.

The general process was:

```text
Historical Feature Retrieval
          ↓
Training Dataset
          ↓
Train/Test Split
          ↓
Model Training
          ↓
Model Evaluation
```

The model was trained using the selected features and target value from the dataset.

---

# 21. Model Accuracy

The model achieved the following accuracy:

**Accuracy:** `<Enter actual accuracy>`%

The accuracy value should be taken directly from the output produced by the implemented model.

### Result

```text
Model Accuracy: <XX.XX>%
```

**Screenshot:**

`<Insert model output screenshot here>`

---

# 22. Final Prediction

After retrieving the required features from Feast, the trained model was used to make a final prediction.

### Final Prediction

```text
Input Entity: <Enter entity>
Features: <Enter feature values>
Prediction: <Enter prediction>
```

**Final predicted result:** `<Enter actual prediction>`

This demonstrates the complete flow from feature retrieval to model prediction.

---

# 23. Results

The main results obtained from the project are:

### Historical Feature Output

```text
<Insert actual output>
```

### Model Accuracy

```text
<XX.XX>%
```

### Online Feature Output

```text
<Insert actual output>
```

### Final Prediction

```text
<Insert actual prediction>
```

These results demonstrate that the features were successfully created, registered with Feast, retrieved historically, materialized into the online store, retrieved online, and finally used for machine-learning prediction. The assignment specifically requires these four outputs/results to be included.

---

# 24. Analysis

## 24.1 What is the entity in your Feast implementation?

The entity in my implementation is:

**`<Entity Name>`**

It uniquely identifies the object for which the feature values are maintained.

---

## 24.2 What features are stored in the FeatureView?

The FeatureView contains the following features:

* `<Feature 1>`
* `<Feature 2>`
* `<Feature 3>`
* `<Feature 4>`
* `<Feature 5>`

Each feature represents an important part of the curriculum–industry skill-gap information.

---

## 24.3 How was one feature calculated?

One feature was calculated using the values available in the original dataset.

For example:

```text
Skill Gap = Industry Requirement - Curriculum Coverage
```

This calculation helps represent how much additional importance or requirement exists for a skill from the industry perspective.

The actual calculation used in the project should be described here based on the implemented feature-engineering code.

---

## 24.4 What is the difference between the original dataset and the feature dataset?

The original dataset contains the raw information collected for the skill-gap problem.

The feature dataset contains processed values that are specifically prepared for machine-learning and managed through Feast.

Therefore, the feature dataset is derived from the original dataset through feature engineering.

---

## 24.5 What is the purpose of the offline store?

The offline store is mainly used to store and retrieve historical feature data.

It is useful during model training because the model needs historical feature values to learn patterns from the data.

---

## 24.6 What is the purpose of the online store?

The online store provides feature values quickly during prediction.

Instead of calculating the features again whenever a prediction is required, the application can retrieve the already prepared values from the online store.

---

## 24.7 What is the purpose of `feast apply`?

`feast apply` is used to register the Feast definitions.

It applies the configuration containing the entity, data source, FeatureView, and related definitions so that Feast can manage them.

In this project, it was used after defining the Feast configuration.

---

## 24.8 What does materialization do?

Materialization copies the required feature values from the offline source into the online store.

This makes the features available for online retrieval.

In simple terms:

```text
Offline Store → Materialization → Online Store
```

---

## 24.9 What is the advantage of using Feast instead of manually calculating features?

The main advantage is consistency.

If features are calculated separately during training and prediction, there is a possibility that the two calculations may be different.

With Feast, the feature definitions are maintained centrally and can be retrieved for both historical training and online prediction.

This makes the overall machine-learning workflow more organized and reduces repeated feature-calculation logic.

---

## 24.10 What are two limitations of the current dataset?

### Limitation 1

The dataset is limited in size and may not represent the complete range of skills required across different industries.

### Limitation 2

The skill-gap values depend on the information used while creating the dataset. More real-world curriculum and industry evidence would make the results more representative.

 

## 24.11 How can the feature store be improved in the future?

### Improvement 1

More curriculum and industry data can be collected from different colleges, job descriptions, companies, and skill surveys. This would make the feature store more comprehensive.

### Improvement 2

The feature engineering process can be expanded to include more meaningful features such as skill demand, frequency of skill occurrence in job descriptions, curriculum coverage, experience level, and technology trends.

These limitations and future improvements address the analysis requirements specified in the assignment.

 

# 25. Project Workflow

The complete implementation can be summarized as follows:

 
Create Skill-Gap Dataset
          ↓
Clean and Prepare Dataset
          ↓
Perform Feature Engineering
          ↓
Create Parquet Feature Data
          ↓
Configure Feast
          ↓
Create Entity
          ↓
Create Data Source
          ↓
Create FeatureView
          ↓
Run feast apply
          ↓
Retrieve Historical Features
          ↓
Train ML Model
          ↓
Evaluate Model
          ↓
Materialize Features
          ↓
Retrieve Online Features
          ↓
Make Final Prediction
 

This workflow helped me understand how a feature store fits into an end-to-end machine-learning project.

---

# 26. Technologies Used

* **Python** – Dataset processing, feature engineering, and machine learning
* **Feast** – Feature store
* **Pandas** – Data processing
* **Parquet** – Offline feature data
* **SQLite** – Local online store
* **Scikit-learn** – Machine-learning model
* **GitHub** – Project repository and documentation

---

# 27. Project Structure

The repository is organized approximately as follows:

 
<RegisterNumber>MLOps-Feast-SkillGap/
│
├── data/
│   ├── original_dataset.csv
│   └── feature_data.parquet
│
├── feature_store/
│   ├── feature_store.yaml
│   └── definitions.py
│
├── notebooks/
│   └── skill_gap_analysis.ipynb
│
├── src/
│   ├── feature_engineering.py
│   └── model.py
│
├── results/
│   ├── historical_features.csv
│   └── prediction.txt
│
└── README.md
 

The exact folder names should match the files actually present in the GitHub repository.
 
# 28. Conclusion

This project gave me practical experience with the basic concepts of a feature store using Feast.

I started with a curriculum–industry skill-gap dataset and converted the available information into useful machine-learning features. I then created the required Feast entity, data source, and FeatureView and registered them using `feast apply`.

After that, I retrieved historical features for model training, materialized the features into the online store, and retrieved them again for online prediction.

Finally, I used the Feast features with a simple machine-learning model and generated a prediction.

The most important thing I learned from this project is that a feature store helps maintain features in a structured and reusable way. It provides a common approach for using features during both model training and prediction instead of manually handling the same feature calculations at different stages.

Overall, this project helped me understand how **feature engineering, Feast, feature retrieval, and machine learning** can work together as part of an MLOps workflow.

 

# 29. GitHub Repository

**Repository Name:**

```text
<RegisterNumber>MLOps-Feast-SkillGap
```

**GitHub Repository Link:**

`<Paste your GitHub repository link here>`

The assignment requires the completed work to be uploaded to the student's own GitHub repository and the repository link to be submitted through the faculty-provided Google Form.

 

 
**Important:** Replace every `<...>` placeholder with the **actual values, feature names, model name, outputs, accuracy, entity, and screenshots from your implementation**. The assignment specifies what must be documented, but the uploaded document does not provide your actual dataset values or experiment outputs, so those should not be invented.
