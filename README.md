# MLFlow Project: House Price Prediction & Experiment Tracking

## 📁 Project Structure

```
.
├── Mlflow_server_tracking.ipynb
├── README.md
├── requirements.txt
├── 1-MLFlow_Project/
│   ├── gettingstarted.ipynb
│   ├── houepricepredict.ipynb
│   └── mlruns/
│       └── ... (MLflow experiment tracking data)
├── mlartifacts/
│   └── ... (MLflow model artifacts)
├── mlruns/
│   └── ... (MLflow experiment tracking data)
```

---

## 📚 Notebooks Overview

### [1-MLFlow_Project/gettingstarted.ipynb](1-MLFlow_Project/gettingstarted.ipynb)
- **Purpose:** Introduction to MLflow, experiment tracking, model logging, and model registry.
- **Topics Covered:**
  - Installing and configuring MLflow
  - Starting a local MLflow tracking server
  - Logging and registering models
  - Loading models for inference using MLflow's pyfunc flavor
  - Viewing experiment results in the MLflow UI

### [1-MLFlow_Project/houepricepredict.ipynb](1-MLFlow_Project/houepricepredict.ipynb)
- **Purpose:** House price prediction using RandomForestRegressor with hyperparameter tuning and MLflow experiment tracking.
- **Topics Covered:**
  - Data preparation with California Housing dataset
  - Hyperparameter tuning using GridSearchCV
  - Logging hyperparameters and metrics to MLflow
  - Model registration and verification

### [Mlflow_server_tracking.ipynb](Mlflow_server_tracking.ipynb)
- **Purpose:** Demonstrates MLflow server tracking and logging custom metrics.
- **Topics Covered:**
  - Logging metrics to MLflow server
  - Viewing experiment and run details

---

## 🧰 Libraries Used

- **[pandas](https://pandas.pydata.org/):** Data manipulation and analysis
- **[scikit-learn](https://scikit-learn.org/):** Machine learning models and utilities
  - `RandomForestRegressor`
  - `train_test_split`
  - `GridSearchCV`
  - `mean_squared_error`
  - `datasets.fetch_california_housing`
- **[mlflow](https://mlflow.org/):** Experiment tracking, model logging, and model registry
  - `mlflow.sklearn`
  - `mlflow.start_run`
  - `mlflow.log_param`, `mlflow.log_params`
  - `mlflow.log_metric`
  - `mlflow.set_tracking_uri`
  - `mlflow.set_experiment`
  - `mlflow.sklearn.log_model`
  - `mlflow.models.infer_signature`
  - `mlflow.pyfunc.load_model`
  - `mlflow.tracking.MlflowClient`
- **[urllib.parse](https://docs.python.org/3/library/urllib.parse.html):** URL parsing for tracking URI

---

## 🏷️ Key Methods & Functions

- **Data Preparation:**
  - `fetch_california_housing()`
  - `pd.DataFrame()`
  - `train_test_split()`
- **Modeling:**
  - `RandomForestRegressor()`
  - `GridSearchCV()`
  - `mean_squared_error()`
- **MLflow Tracking:**
  - `mlflow.start_run()`
  - `mlflow.log_param()`, `mlflow.log_params()`
  - `mlflow.log_metric()`
  - `mlflow.set_tracking_uri()`
  - `mlflow.set_experiment()`
  - `mlflow.sklearn.log_model()`
  - `mlflow.models.infer_signature()`
  - `mlflow.pyfunc.load_model()`
  - `mlflow.tracking.MlflowClient()`
  - `MlflowClient.search_registered_models()`

---

## 🔗 Useful Links

- **MLflow Documentation:** [https://mlflow.org/docs/latest/index.html](https://mlflow.org/docs/latest/index.html)
- **MLflow UI:** [http://127.0.0.1:5000](http://127.0.0.1:5000)
- **California Housing Dataset:** [scikit-learn documentation](https://scikit-learn.org/stable/datasets/real_world.html#california-housing-dataset)

---

## 🚀 How to Run

1. **Install dependencies:**
   ```sh
   pip install -r requirements.txt
   ```

2. **Start MLflow Tracking Server:**
   ```sh
   mlflow server --backend-store-uri ./mlruns --default-artifact-root ./mlartifacts --host 127.0.0.1 --port 5000
   ```

3. **Run Notebooks:**
   - Open and execute cells in [gettingstarted.ipynb](1-MLFlow_Project/gettingstarted.ipynb) for MLflow basics.
   - Use [houepricepredict.ipynb](1-MLFlow_Project/houepricepredict.ipynb) for house price prediction and experiment tracking.
   - Try [Mlflow_server_tracking.ipynb](Mlflow_server_tracking.ipynb) for server-side metric logging.

4. **View Results:**
   - Access the MLflow UI at [http://127.0.0.1:5000](http://127.0.0.1:5000) to compare runs, view metrics, and manage models.

---

## 🗂️ Explorer Navigation

- **Notebooks:**  
  - [1-MLFlow_Project/gettingstarted.ipynb](1-MLFlow_Project/gettingstarted.ipynb)  
  - [1-MLFlow_Project/houepricepredict.ipynb](1-MLFlow_Project/houepricepredict.ipynb)  
  - [Mlflow_server_tracking.ipynb](Mlflow_server_tracking.ipynb)

- **MLflow Tracking Data:**  
  - [1-MLFlow_Project/mlruns/](1-MLFlow_Project/mlruns/)  
  - [mlruns/](mlruns/)  
  - [mlartifacts/](mlartifacts/)

---

## 📝 Notes

- **Model Registration:**  
  Registered models can be checked using:
  ```python
  from mlflow.tracking import MlflowClient
  client = MlflowClient()
  print(client.search_registered_models(filter_string="name='Best_Randomforest_Model'"))
  ```
- **Tracking URI:**  
  Ensure all scripts/notebooks set the tracking URI to `http://127.0.0.1:5000` for consistent experiment logging.

---

## 📦 Requirements

See [requirements.txt](requirements.txt) for all dependencies.

---

Happy Experimenting! 🚀