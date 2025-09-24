Basic Pipeline and Smaples
====

Semi-supervised VAD
----

As previously discussed, SVAD only utilizes samples containing normal events during the training phase, making the traditional full supervised learning paradigm inapplicable. To address this issue, the most straightforward approach is to leverage the intrinsic information of the training samples to learn the patterns of normal events or, in other words, define the boundaries of normal events. Generally, the research paradigms for SVAD can be categorized into two main types: self-supervised learning and one-class classification.

| Method          | Year | Ped2(AUC) | Avenue(AUC) | SHTech(AUC) | UBnormal(AUC) |
|-----------------|------|-----------|-------------|-------------|--------------|
| ConvAE [7]      | 2016 | 90.0%     | 72.0%       | /           | /            |
| STAE [106]      | 2017 | 91.2%     | 80.9%       | /           | /            |
| FutureFrame [8] | 2018 | 95.4%     | 85.1%       | 72.8%       | /            |
| MemAE [168]     | 2019 | 94.1%     | 83.3%       | 71.2%       | /            |
| BMAN [167]      | 2019 | 96.6%     | 90.0%       | 76.2%       | /            |
| MNaD [169]      | 2020 | 97.0%     | 88.5%       | 70.5%       | /            |
| AmmcNet [85]    | 2021 | 96.6%     | 86.6%       | 73.7%       | /            |
| MultiTVAD [170] | 2021 | 99.8%     | 92.8%       | 90.2%       | /            |
| JigsawPuzzle [97]|2022 | 99.0%     | 92.2%       | 84.3%       | 56.4%        |
| BDPN [130]      | 2022 | 98.3%     | 90.3%       | 78.1%       | /            |
| SenceAware [132]| 2023 | 98.1%     | 93.7%       | 83.4%       | /            |
| LERF [171]      | 2023 | 99.4%     | 91.5%       | 78.6%       | /            |
| Nomral-Pose VAD [172]|2023| /     | /           | 85.9%       | 71.8%        |
| SDMAE [146]     | 2024 | 95.4%     | 91.3%       | 79.1%       | 58.5%        |
| FGDVAD [173]    | 2024 | /         | 88.0%       | 78.6%       | 68.9%        |
| VADMamba [174]  | 2025 | 98.5%     | 91.5%       | 77.0%       | /            |
| MA-PDM [175]    | 2025 | 98.6%     | 91.3%       | 79.2%       | 63.4%        |

[7] M. Hasan, J. Choi, J. Neumann, A. K. Roy-Chowdhury, and L. S. Davis, “Learning temporal regularity in video sequences,” in Proceedings of the IEEE conference on computer vision and pattern recognition, 2016, pp. 733–742.

[106] Y. Zhao, B. Deng, C. Shen, Y. Liu, H. Lu, and X.-S. Hua, “Spatio-temporal autoencoder for video anomaly detection,” in Proceedings of the 25th ACM international conference on Multimedia, 2017, pp. 1933–1941.

[8] W. Liu, W. Luo, D. Lian, and S. Gao, “Future frame prediction for anomaly detection–a new baseline,” in Proceedings of the IEEE conference on computer vision and pattern recognition, 2018, pp. 6536–6545.

[168] D. Gong, L. Liu, V. Le, B. Saha, M. R. Mansour, S. Venkatesh, and A. v. d. Hengel, “Memorizing normality to detect anomaly: Memory-augmented deep autoencoder for unsupervised anomaly detection,” in Proceedings of the IEEE/CVF international conference on computer vision, 2019, pp. 1705–1714.

[167] S. Lee, H. G. Kim, and Y. M. Ro, “Bman: Bidirectional multi-scale aggregation networks for abnormal event detection,” IEEE Transactions on Image Processing, vol. 29, pp. 2395–2408, 2019.

[169] H. Park, J. Noh, and B. Ham, “Learning memory-guided normality for anomaly detection,” in Proceedings of the IEEE/CVF conference on computer vision and pattern recognition, 2020, pp. 14372–14381.

[85] R. Cai, H. Zhang, W. Liu, S. Gao, and Z. Hao, “Appearance-motion memory consistency network for video anomaly detection,” in Proceedings of the AAAI conference on artificial intelligence, vol. 35, no. 2, 2021, pp. 938–946.

[170] M.-I. Georgescu, A. Barbalau, R. T. Ionescu, F. S. Khan, M. Popescu, and M. Shah, “Anomaly detection in video via self-supervised and multi-task learning,” in Proceedings of the IEEE/CVF conference on computer vision and pattern recognition, 2021, pp. 12742–12752.

[97] G. Wang, Y. Wang, J. Qin, D. Zhang, X. Bao, and D. Huang, “Video anomaly detection by solving decoupled spatio-temporal jigsaw puzzles,” in European Conference on Computer Vision. Springer, 2022, pp. 494–511.

[130] C. Chen, Y. Xie, S. Lin, A. Yao, G. Jiang, W. Zhang, Y. Qu, R. Qiao, B. Ren, and L. Ma, “Comprehensive regularization in a bi-directional predictive network for video anomaly detection,” in Proceedings of the AAAI conference on artificial intelligence, vol. 36, no. 1, 2022, pp. 230–238.

[132] S. Sun and X. Gong, “Hierarchical semantic contrast for scene-aware video anomaly detection,” in Proceedings of the IEEE/CVF conference on computer vision and pattern recognition, 2023, pp. 22846–22856.

[171] C. Sun, C. Shi, Y. Jia, and Y. Wu, “Learning event-relevant factors for video anomaly detection,” in Proceedings of the AAAI Conference on Artificial Intelligence, vol. 37, no. 2, 2023, pp. 2384–2392.

[172] O. Hirschorn and S. Avidan, “Normalizing flows for human pose anomaly detection,” in Proceedings of the IEEE/CVF International Conference on Computer Vision, 2023, pp. 13545–13554.

[146] N.-C. Ristea, F.-A. Croitoru, R. T. Ionescu, M. Popescu, F. S. Khan, M. Shah et al., “Self-distilled masked auto-encoders are efficient video anomaly detectors,” in Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition, 2024, pp. 15984–15995.

[173] X. Tan, H. Wang, X. Geng, and L. Wang, “Frequency-guided diffusion model with perturbation training for skeleton-based video anomaly detection,” arXiv preprint arXiv:2412.03044, 2024.

[174] J. Lyu, M. Zhao, J. Hu, X. Huang, Y. Chen, and S. Du, “Vadmamba: Exploring state space models for fast video anomaly detection,” arXiv preprint arXiv:2503.21169, 2025.

[175] H. Zhou, J. Cai, Y. Ye, Y. Feng, C. Gao, J. Yu, Z. Song, and W. Yang, “Video anomaly detection with motion and appearance guided patch diffusion model,” in Proceedings of the AAAI Conference on Artificial Intelligence, vol. 39, no. 10, 2025, pp. 10761–10769.

WVAD
----

| Method         | Year | UCF-Crime(AUC) | XD-Violence(AUC) | SHTech(AUC) |
|----------------|------|----------------|------------------|-------------|
| DeepMIL [9]    | 2018 | 75.40%         | /                | /           |
| GCN [179]      | 2019 | 82.12%         | /                | 84.44%      |
| CLAWS [182]    | 2020 | 83.03%         | /                | 89.67%      |
| MIST [180]     | 2021 | 82.30%         | /                | 94.83%      |
| MSL [60]       | 2022 | 85.62%         | 78.59%           | 97.32%      |
| S3R [59]       | 2022 | 85.99%         | 80.26%           | 97.48%      |
| UMIL [69]      | 2023 | 86.75%         | /                | /           |
| DMU [196]      | 2023 | 86.97%         | 81.66%           | /           |
| VadCLIP [33]   | 2024 | 88.02%         | 84.51%           | /           |
| CLIP-TSA [197] | 2024 | 87.58%         | 82.19%           | 98.32%      |
| CMFVAD [205]   | 2024 | /              | 86.34%           | /           |

[9] W. Sultani, C. Chen, and M. Shah, “Real-world anomaly detection in surveillance videos,” in Proceedings of the IEEE conference on computer vision and pattern recognition, 2018, pp. 6479–6488.

[179] J.-X. Zhong, N. Li, W. Kong, S. Liu, T. H. Li, and G. Li, “Graph convolutional label noise cleaner: Train a plug-and-play action classifier for anomaly detection,” in Proceedings of the IEEE/CVF conference on computer vision and pattern recognition, 2019, pp. 1237–1246.

[182] M. Z. Zaheer, A. Mahmood, M. Astrid, and S.-I. Lee, “Claws: Clustering assisted weakly supervised learning with normalcy suppression for anomalous event detection,” in Computer Vision–ECCV 2020: 16th European Conference, Glasgow, UK, August 23–28, 2020, Proceedings, Part XXII 16. Springer, 2020, pp. 358–376.

[180] J.-C. Feng, F.-T. Hong, and W.-S. Zheng, “Mist: Multiple instance self-training framework for video anomaly detection,” in Proceedings of the IEEE/CVF conference on computer vision and pattern recognition, 2021, pp. 14009–14018.

[60] S. Li, F. Liu, and L. Jiao, “Self-training multi-sequence learning with transformer for weakly supervised video anomaly detection,” in Proceedings of the AAAI Conference on Artificial Intelligence, vol. 36, no. 2, 2022, pp. 1395–1403.

[59] J.-C. Wu, H.-Y. Hsieh, D.-J. Chen, C.-S. Fuh, and T.-L. Liu, “Self-supervised sparse representation for video anomaly detection,” in European Conference on Computer Vision. Springer, 2022, pp. 729–745.

[69] H. Lv, Z. Yue, Q. Sun, B. Luo, Z. Cui, and H. Zhang, “Unbiased multiple instance learning for weakly supervised video anomaly detection,” in Proceedings of the IEEE/CVF conference on computer vision and pattern recognition, 2023, pp. 8022–8031.

[196] H. Zhou, J. Yu, and W. Yang, “Dual memory units with uncertainty regulation for weakly supervised video anomaly detection,” in Proceedings of the AAAI Conference on Artificial Intelligence, vol. 37, no. 3, 2023, pp. 3769–3777.

[33] P. Wu, X. Zhou, G. Pang, L. Zhou, Q. Yan, P. Wang, and Y. Zhang, “Vadclip: Adapting vision-language models for weakly supervised video anomaly detection,” in Proceedings of the AAAI Conference on Artificial Intelligence, vol. 38, no. 6, 2024, pp. 6074–6082.

[197] H. K. Joo, K. Vo, K. Yamazaki, and N. Le, “Clip-tsa: Clip-assisted temporal self-attention for weakly-supervised video anomaly detection,” in 2023 IEEE International Conference on Image Processing (ICIP). IEEE, 2023, pp. 3230–3234.

[205] A. Ghadiya, P. Kar, V. Chudasama, and P. Wasnik, “Cross-modal fusion and attention mechanism for weakly supervised video anomaly detection,” in Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition, 2024, pp. 1965–1974.

UVAD
----

| Method         | Year | UCF-Crime(AUC) | XD-Violence(AP) | Ped2(AUC) | Avenue(AUC) | SHTech(AUC) |
|----------------|------|----------------|-----------------|-----------|-------------|-------------|
| Unmasking [206]| 2017 | /              | /               | 82.2%     | 80.6%       | /           |
| DAW [209]      | 2018 | /              | /               | 96.4%     | 85.3%       | /           |
| MC2ST [207]    | 2018 | /              | /               | 87.5%     | 84.4%       | /           |
| STDOR [214]    | 2020 | /              | /               | 83.2%     | /           | /           |
| CIL [208]      | 2022 | /              | /               | 99.4%     | 90.3%       | /           |
| LBR-SPR [211]  | 2022 | /              | /               | 97.2%     | 92.8%       | 72.6%       |
| C2FPL [215]    | 2024 | 80.7%          | 80.%            | /         | /           | /           |
| CLAP [216]     | 2024 | 83.2%          | 85.7%           | /         | /           | /           |
| CKNN [217]     | 2024 | /              | /               | /         | 94.1%       | 89.0%       |
| InterUVAD [218]| 2024 | /              | /               | /         | /           | 88.2%       |

[206] R. Tudor Ionescu, S. Smeureanu, B. Alexe, and M. Popescu, “Unmasking the abnormal events in video,” in Proceedings of the IEEE international conference on computer vision, 2017, pp. 2895–2903.

[209] S. Wang, Y. Zeng, Q. Liu, C. Zhu, E. Zhu, and J. Yin, “Detecting abnormality without knowing normality: A two-stage approach for unsupervised video abnormal event detection,” in Proceedings of the 26th ACM international conference on Multimedia, 2018, pp. 636–644.

[207] Y. Liu, C.-L. Li, and B. Póczos, “Classifier two sample test for video anomaly detections.” in BMVC, 2018, p. 71.

[214] G. Pang, C. Yan, C. Shen, A. v. d. Hengel, and X. Bai, “Self-trained deep ordinal regression for end-to-end video anomaly detection,” in Proceedings of the IEEE/CVF conference on computer vision and pattern recognition, 2020, pp. 12173–12182.

[208] X. Lin, Y. Chen, G. Li, and Y. Yu, “A causal inference look at unsupervised video anomaly detection,” in Proceedings of the AAAI Conference on Artificial Intelligence, vol. 36, no. 2, 2022, pp. 1620–1629.

[211] G. Yu, S. Wang, Z. Cai, X. Liu, C. Xu, and C. Wu, “Deep anomaly discovery from unlabeled videos via normality advantage and self-paced refinement,” in Proceedings of the IEEE/CVF Conference on computer vision and pattern recognition, 2022, pp. 13987–13998.

[215] A. Al-Lahham, N. Tastan, M. Z. Zaheer, and K. Nandakumar, “A coarse-to-fine pseudo-labeling (c2fpl) framework for unsupervised video anomaly detection,” in Proceedings of the IEEE/CVF Winter Conference on Applications of Computer Vision, 2024, pp. 6793–6802.

[216] A. Al-Lahham, M. Z. Zaheer, N. Tastan, and K. Nandakumar, “Collaborative learning of anomalies with privacy (clap) for unsupervised video anomaly detection: A new baseline,” in Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition, 2024, pp. 12416–12425.

[217] J. Yi and S. Yoon, “Cknn: Cleansed k-nearest neighbor for unsupervised video anomaly detection,” in Proceedings of the 33rd ACM International Conference on Information and Knowledge Management, 2024, pp. 3002–3011.

[218] Y. Nie, H. Huang, C. Long, Q. Zhang, P. Maji, and H. Cai, “Interleaving one-class and weakly-supervised models with adaptive thresholding for unsupervised video anomaly detection,” in European Conference on Computer Vision. Springer, 2024, pp. 449–467.

Open-set VAD
----

| Method           | Year | UCF-Crime(AUC) | XD-Violence(AP)  | Ped2(AUC) | Avenue(AUC) | SHTech(AUC) |
|------------------|------|----------------|------------------|-----------|-------------|-------------|
| MLEP [236]       | 2019 | /              | /                | /         | 92.80%      | 76.80%      |
| Zhu et al. [237] | 2021 | 80.14%         | 69.61%           | /         | /           | /           |
|                  |      | (9 anomaly seen)| (4 anomaly seen)|           |             |             |
| Hu et al. [241]  | 2021 | /              | /                | 96.20%    | 85.80%      | 77.9%       |
|                  |      |                |                  | (13 sence seen)| (13 sence seen)| (13 sence seen) |
| Huang et al. [242]|2022 | /              | /                | 95.12%    | 82.62%      | /           |
|                  |      |                |                  | (10 shot) | (10 shot)   |             |
| Aich et al. [243]| 2023 | /              | /                | 96.95%    | /           | 71.60%      |

[236] W. Liu, W. Luo, Z. Li, P. Zhao, S. Gao et al., “Margin learning embedded prediction for video anomaly detection with a few anomalies,” in IJCAI, vol. 3, 2019, pp. 023–3.

[237] Y. Zhu, W. Bao, and Q. Yu, “Towards open set video anomaly detection,” in European Conference on Computer Vision. Springer, 2022, pp. 395–412.

[241] Y. Hu, X. Huang, and X. Luo, “Adaptive anomaly detection network for unseen scene without fine-tuning,” in Pattern Recognition and Computer Vision: 4th Chinese Conference, PRCV 2021, Beijing, China, October 29–November 1, 2021, Proceedings, Part II 4. Springer, 2021, pp. 311–323.

[242] X. Huang, Y. Hu, X. Luo, J. Han, B. Zhang, and X. Cao, “Boosting variational inference with margin learning for few-shot scene-adaptive anomaly detection,” IEEE Transactions on Circuits and Systems for Video Technology, vol. 33, no. 6, pp. 2813–2825, 2022.

[243] A. Aich, K.-C. Peng, and A. K. Roy-Chowdhury, “Cross-domain video anomaly detection without target domain adaptation,” in Proceedings of the IEEE/CVF Winter Conference on Applications of Computer Vision, 2023, pp. 2579–2591.

Open-vocabulary VAD
----

| Method                | Year | Dataset & Performance                                                  |
|-----------------------|------|------------------------------------------------------------------------|
| Wu et al. [244]       | 2024 | UCF-Crime(AUC) 86.40% XD-Violence(AP) 66.53% UBnormal(AUC) 62.94%     |
| LaGoVAD [245]         | 2025 | UCF-Crime(Acc) 51.72% XD-Violence(Acc) 78.13%                         |
| Yang and Radke [246]  | 2025 | Street Scene(AUC) 67.0% Ped2(AUC) 99.0% SHTech(AUC) 81.3%             |

[244] P. Wu, X. Zhou, G. Pang, Y. Sun, J. Liu, P. Wang, and Y. Zhang, “Open-vocabulary video anomaly detection,” in Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition, 2024, pp. 18297–18307.

[245] Z. Liu, X. Wu, J. Wu, X. Wang, and L. Yang, “Language-guided open world video anomaly detection,” arXiv preprint arXiv:2503.13160, 2025.

[246] Z. Yang and R. J. Radke, “Detecting contextual anomalies by discovering consistent spatial regions,” arXiv preprint arXiv:2501.08470, 2025.

TVAD
----

| Method                | Year | UCF-Crime(AUC) | XD-Violence(AP) | Ped2(AUC) | Avenue(AUC) | SHTech(AUC) |
|-----------------------|------|----------------|-----------------|-----------|-------------|-------------|
| LAVAD [34]            | 2024 | 80.28%         | 62.01%          | /         | /           | /           |
| Anomaly Ruler [35]    | 2024 | /              | /               | 97.40%    | 81.60%      | 83.50%      |
| SUVAD [38]            | 2025 | 83.90%         | 70.10%          | 96.80%    | 89.30%      | 80.20%      |
| VADSK [219]           | 2025 | /              | /               | 86.50%    | 74.20%      | 75.30%      |
| VERA [12]             | 2025 | 86.55%         | 88.26%(AUC)     | /         | /           | /           |

[34] L. Zanella, W. Menapace, M. Mancini, Y. Wang, and E. Ricci, “Harnessing large language models for training-free video anomaly detection,” in Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition, 2024, pp. 18527–18536.

[35] Y. Yang, K. Lee, B. Dariush, Y. Cao, and S.-Y. Lo, “Follow the rules: reasoning for video anomaly detection with large language models,” in European Conference on Computer Vision. Springer, 2024, pp. 304–322.

[38] S. Gao, P. Yang, and L. Huang, “Suvad: Semantic understanding based video anomaly detection using mllm,” in ICASSP 2025-2025 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP). IEEE, 2025, pp. 1–5.

[219] T. Foltz, “Video anomaly detection with structured keywords,” arXiv preprint arXiv:2503.10653, 2025.

[12] M. Ye, W. Liu, and P. He, “Vera: Explainable video anomaly detection via verbalized learning of vision-language models,” in Proceedings of the Computer Vision and Pattern Recognition Conference, 2025, pp. 8679–8688.

ITVAD
----

| Method           | Year | Dataset & Performance                                                                                                            |
|------------------|------|----------------------------------------------------------------------------------------------------------------------------------|
| VADLlama [72]    | 2024 | TAD(AUC) 88.13% UCF-Crime(AUC) 91.77%                                                                                           |
| CUVA [10]        | 2024 | CUVA(MMEval) 79.65 58.92 50.64                                                                                                  |
| HAWK [11]        | 2024 | HAWK(GPT-Guided) 0.283 0.320 0.218                                                                                              |
| VLAVAD [71]      | 2024 | Ped2(AUC) 99.00% Avenue(AUC) 87.6% SHTech(AUC) 87.2%                                                                           |
| Holmes-VAU [13]  | 2025 | HIVAU-70k(BLEU) 0.916 0.804 0.566 UCF-Crime(AUC) 88.96% XD-Violence(AP) 87.68                                                  |
| UCVL [48]        | 2025 | UCVL(GPT-4o) 63.8                                                                                                               |
| SlowFastVAD [233]| 2025 | Ped2(AUC) 99.10% Avenue(AUC) 89.6% SHTech(AUC) 85.0% MissionGNN [234] 2025 UCF-Crime Incomplete(AUC) 91.00%                    |

[72] H. Lv and Q. Sun, “Video anomaly detection and explanation via large language models,” arXiv preprint arXiv:2401.05702, 2024.

[10] H. Du, S. Zhang, B. Xie, G. Nan, J. Zhang, J. Xu, H. Liu, S. Leng, J. Liu, H. Fan et al., “Uncovering what why and how: A comprehensive benchmark for causation understanding of video anomaly,” in Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition, 2024, pp. 18793–18803.

[11] J. Tang, H. Lu, R. Wu, X. Xu, K. Ma, C. Fang, B. Guo, J. Lu, Q. Chen, and Y. Chen, “Hawk: Learning to understand open-world video anomalies,” Advances in Neural Information Processing Systems, vol. 37, pp. 139751–139785, 2024.

[71] Y. Jiang and L. Mao, “Vision-language models assisted unsupervised video anomaly detection,” arXiv preprint arXiv:2409.14109, 2024.

[13] H. Zhang, X. Xu, X. Wang, J. Zuo, X. Huang, C. Gao, S. Zhang, L. Yu, and N. Sang, “Holmes-vau: Towards long-term video anomaly understanding at any granularity,” in Proceedings of the Computer Vision and Pattern Recognition Conference, 2025, pp. 13843–13853.

[48] H. Chen, D. Yi, M. Cao, C. Huang, G. Zhu, and J. Wang, “A benchmark for crime surveillance video analysis with large models,” arXiv preprint arXiv:2502.09325, 2025.

[233] Z. Ding, H. Zhang, P. Wu, G. Pang, Z. Yang, P. Wang, and Y. Zhang, “Slowfastvad: Video anomaly detection via integrating simple detector and rag-enhanced vision-language model,” arXiv preprint arXiv:2504.10320, 2025.

[234] S. Yun, R. Masukawa, M. Na, and M. Imani, “Missiongnn: Hierarchical multimodal gnn-based weakly supervised video anomaly recognition with mission-specific knowledge graph generation,” in 2025 IEEE/CVF Winter Conference on Applications of Computer Vision (WACV). IEEE, 2025, pp. 4736–4745.
