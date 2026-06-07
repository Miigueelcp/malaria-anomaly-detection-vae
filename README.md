# 🔬 Unsupervised Malaria Anomaly Detection via Denoising VAE

An end-to-end Computer Vision and Deep Learning pipeline that utilizes an unsupervised **Variational Autoencoder (VAE)** to detect and localize *Plasmodium* parasites in red blood cells. By training exclusively on healthy cellular profiles, the model learns the normal biological manifold, projecting infected cells onto it and isolating anomalies via spatial residual heatmaps.

## 🚀 Key Features
* **Unsupervised Latent Topology:** Trained only on normal cells; detects pathogens without requiring anomaly labels during training.
* **Level 3 Denoising Pipeline:** Spatial filtering (2D Median Filters) integrated into the inference loop to isolate biological signals from sensor noise.
* **Periphery-Safe Pathology BBox Engine:** Dynamic OpenCV localization that catches marginal and coastal parasites down to a 2-pixel footprint.
* **Edge-Ready AI Optimization:** Quantized deployment graph (`.tflite` FP16) compressing the model architecture for resource-constrained hardware.

## 📊 Performance & Clinical Metrics
* **Discrimination Capacity (AUC):** 0.7664
* **Optimal Diagnostic Threshold:** 0.002863
* **Clinical Sensitivity (TPR):** 84.86%
* **False Positive Rate (FPR):** 38.07%

## 🛠️ Tech Stack
* **Deep Learning:** TensorFlow 2.21, Keras
* **Computer Vision & Processing:** OpenCV (`cv2`), SciPy, NumPy
* **Evaluation & Visuals:** Scikit-Learn, Matplotlib


## 📂 Project Structure
- `malaria_vae_detector.ipynb`: The main notebook containing the full 8-part modular unsupervised deep learning and computer vision pipeline.
- **`models/`**: Serialized model distributions and production outputs:
  * `malaria_anomaly_vae_quantized.tflite`: Edge-AI Float16 optimized deployment graph compiled for resource-constrained hardware.
- **`images/`**: Resulting visual and clinical assets organized by validation phase:
  * `01_convergence`: Loss visualization charts displaying Reconstruction Loss (MSE) and Kullback-Leibler (KL) Divergence trends.
  * `02_clinical_evaluation`: Receiver Operating Characteristic (ROC) analysis, Youden's J-Index optimization, and population density histograms.
  * `03_inference_results`: Production inference reports, absolute diagnostic heatmaps, and localized anomaly bounding boxes.
- `requirements.txt`: Environment dependencies and core framework versions for absolute reproducibility.
- `LICENSE`: MIT Open-Source License terms and permissions.
- `README.md`: Core project documentation, architectural blueprint, and the complete clinical analysis report.

  

## 🧬 Data Source & Clinical Citation

### Description
The Malaria dataset contains a total of 27,558 cell images with equal instances of parasitized and uninfected cells from the thin blood smear slide images of segmented cells. It is ingested into this project pipeline via the official `tfds.load('malaria')` API call.

### Scientific Reference
If you use this layout, framework, or want to reference the underlying clinical dataset, please cite the original peer-reviewed publication:

> *Rajaraman S, Antani SK, Poostchi M, Silamut K, Hossain MA, Maude RJ, Jaeger S, Thoma GR. (2018) Pre-trained convolutional neural networks as feature extractors toward improved malaria parasite detection in thin blood smear images. PeerJ 6:e4568.* [https://doi.org/10.7717/peerj.4568](https://doi.org/10.7717/peerj.4568)

### BibTeX Format
```bibtex
@article{rajaraman2018pre,
  title={Pre-trained convolutional neural networks as feature extractors toward improved malaria parasite detection in thin blood smear images},
  author={Rajaraman, Sivaramakrishnan and Antani, Sameer K and Poostchi, Mahdieh and Silamut, Kamolrat and Hossain, Md A and Maude, Richard J and Jaeger, Stefan and Thoma, George R},
  journal={PeerJ},
  volume={6},
  pages={e4568},
  year={2018},
  publisher={PeerJ Inc.}
}
```

## Conclusion

This project successfully demonstrates the power of the Unsupervised Anomaly Detection paradigm in digital pathology. We engineered a generative system from the ground up using manifold learning. This allows the model to isolate malaria parasites naturally through reconstruction errors, completely eliminating the need for labeled anomaly datasets during the training phase.

### Key Architectural Insights:
* **Biolofical Manifold Learning:** The Variational Autoencoder (VAE) succesfully mastered the high-dimensional statistical variance of uninfected red blood cells. When exposed to *Plasmodium* structures, its systematic inability yo reconstruct foreign morphologies provided a highly reliable, automated diagnostic signal.
* **Clinical Viability & Safety:** Utilizing Youden's J-Index to mathematically pin down the optimal decision boundary guarantees that the pipelines maximizes clinical sensitivity  (True Positive Rate). This architecture prioritizes patient safety by minimizing dangerous false negatives.
* **Production and Edge AI Readiness:** The integration of spatial computer vision filters effectively isolates organic pathology from sensor and background noise. Furthermore, by converting the heavy framework into an optimized **Float16 TFLite binary**, this study proves that higher-tier deep learning diagnostics can be compressed for field deployment in low-resource, remote medical environments.

