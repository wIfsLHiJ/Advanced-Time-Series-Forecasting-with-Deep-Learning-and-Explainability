Advanced Time-Series Forecasting with Deep Learning and Explainability

    This project demonstrates an end-to-end workflow for multivariate time-series forecasting using deep learning methods, combined with Explainable AI (XAI) to interpret model behavior.
  It includes:
         Synthetic data generatio
         Windowed supervised learning transformation
         Walk-forward cross-validation
         Deep learning forecasting model
         Final evaluation and visualization
         SHAP-based model explainability (with fallback method)
All deliverables (metrics, plots, data files, SHAP explanations) are exported automatically into the outputs/ folder.

📌 Project Structure
├── src/
│   ├── data_generation.py
│   ├── preprocessing.py
│   ├── model_training.py
│   ├── evaluation.py
│   ├── explainability.py
│   └── main.py
├── outputs/
│   ├── synthetic_multivariate.csv
│   ├── cv_metrics.json
│   ├── final_forecast.csv
│   ├── final_plot.png
│   ├── shap_values.png (KernelExplainer fallback)
│   └── shap_summary.png
├── requirements.txt
├── README.md
└── LICENSE

🔧 Installation
      1. Clone the repository
                    git clone https://github.com/your-username/Advanced-Time-Series-Forecasting-with-Deep-Learning-and-Explainability.git
cd Advanced-Time-Series-Forecasting-with-Deep-Learning-and-Explainability

  2. Create a virtual environment
           python -m venv venv
           source venv/bin/activate     # Linux/Mac
           venv\Scripts\activate        # Windows
     
  4. Install dependencies
           pip install -r requirements.txt
  ▶️ How to Run the Project
                
      Run the full pipeline using:python src/main.py
This runs all steps automatically:
     Generate synthetic multivariate time-series
     Create sliding-window supervised dataset
     Train model using walk-forward cross-validation
     Compute RMSE & MAE per fold
     Train final model
     Generate final forecast
     Run XAI explainability
     Save all results to outputs/

📊 Outputs Generated
                  After running, the following files will appear in outputs/:
                  Data Files
                  synthetic_multivariate.csv — generated dataset
                  final_forecast.csv — model predictions
                  Metrics
                  cv_metrics.json — RMSE & MAE for all folds

Example:
{
  "fold_0": {"rmse": 3.13, "mae": 2.60},
  "fold_1": {"rmse": 2.09, "mae": 1.71},
  "fold_2": {"rmse": 2.80, "mae": 2.34},
  "fold_3": {"rmse": 1.74, "mae": 1.46}
}
Visualizations
final_plot.png — full predictions vs actuals
shap_summary.png — SHAP feature importance
shap_values.png — SHAP explanation per timestep

🧠 Explainability (SHAP)

        The project attempts to use SHAP DeepExplainer.However, recent TensorFlow versions produce errors such as:
        gradient registry has no entry for: shap_TensorListStack Therefore, the pipeline automatically falls back to:
        ✔ SHAP KernelExplainer (works with all models)
This ensures XAI results are still produced and included in the deliverables.

📈 Model Architecture
    The model is a multi-step forecasting network built with:
    1× LSTM Layer
    1× Dense projection
    Multi-output forecasting head
The architecture is optimized for small synthetic datasets, ensuring stable convergence.

🔍 Walk-Forward Cross-Validation
    The project uses expanding-window walk-forward CV:
        Train → Validate
        Expand window → Validate
        Expand window → Validate
…

This mimics real forecasting conditions and avoids test leakage.
   📝 Notes for Academic Submission
      This project includes:
         ✔ Synthetic data explanation
         ✔ RMSE/MAE metrics per fold
         ✔ Final forecast visualization
         ✔ 500-word Explainability report (inside REPORT.md if required)
         ✔ All outputs reproducible
         ✔ Clear documentation
 
📄 License

This project is open-source and distributed under the MIT License.

🤝 Contributions

Pull requests and improvements are welcome.
