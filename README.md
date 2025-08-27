# Information_Retrieval_System

This repo collects three of my final-year projects that explore applied ML for medical, language, and time-series problems. Each project is a short, reproducible pipeline: basic preprocessing → model(s) → evaluation. I focused on clear engineering, realistic baselines, and honest evaluation (no overclaiming).

## Projects (short summaries)

### Brain MRI Segmentation (U-Net)
Goal: automatic brain tumor segmentation from MRI scans.  
Method: implemented a U-Net (encoder–bottleneck–decoder) with standard skip connections; experimented with Dice+BCE and BCE losses, used preprocessing (grayscale, 256×256 resize, normalization, CLAHE + Gaussian blur).  
Result: final model reached **IoU ≈ 0.77** and **Dice ≈ 0.87** on the test set. An attention-augmented U-Net improved boundary localization but had slightly lower global metrics.

### Medical Dataset Expansion (MEQSUM)
Goal: expand and improve MEQSUM medical-question dataset to make summarization models more robust.  
Method: used **Round-Trip Translation (RTT)** across multiple pivot languages, filtered augmented samples with selection metrics (FQD, PRQD, QSV), then summarized with pre-trained models (BART, T5, DeepSeek).  
Result: added **~4,000** high-quality question–summary pairs; DeepSeek gave the best summarization scores (at higher compute cost). German RTT tended to produce the strongest augmentations.

### Daily Climate Forecasting (Delhi)
Goal: forecast daily mean atmospheric pressure from sequential climate records.  
Method: careful preprocessing (MinMax scaling, outlier removal with z-score), then tried LSTM, RNN, and GRU architectures with tuned hyperparameters. Evaluated with MAE/MSE/RMSE/R².  
Result: **GRU** provided the best tradeoff — faster training and lower test error than equivalent LSTM/RNN setups.

## Common notes & how to run
- Typical workflow: create a virtualenv → `pip install -r requirements.txt` → run the notebook or `train.py` in each project folder.  
- Each project includes a short notebook demonstrating preprocessing, training, and example outputs/plots.  
- Reproducibility: random seeds are set where applicable, but results depend on dataset splits and compute (GPU recommended for deep models).

## Takeaways
- Preprocessing (scaling, sensible augmentation, outlier handling) often matters more than small architecture tweaks.  
- For language tasks, larger LLMs (DeepSeek) help but cost more; for medical imaging, architectural attention can improve boundaries even when global metrics are similar.  
- For time series, GRUs are a practical baseline — simple, fast, and robust.

---
