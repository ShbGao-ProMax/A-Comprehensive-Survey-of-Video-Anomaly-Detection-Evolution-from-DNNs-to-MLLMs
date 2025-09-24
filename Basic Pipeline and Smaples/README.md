Basic Pipeline and Smaples
====

Semi-supervised VAD
----

As previously discussed, SVAD only utilizes samples containing normal events during the training phase, making the traditional full supervised learning paradigm inapplicable. To address this issue, the most straightforward approach is to leverage the intrinsic information of the training samples to learn the patterns of normal events or, in other words, define the boundaries of normal events. Generally, the research paradigms for SVAD can be categorized into two main types: self-supervised learning and one-class classification.

On classic benchmarks like Ped2 and Avenue, the AUC scores of state-of-the-art approaches have reached or even surpassed 99\%, indicating that these datasets are nearly saturated. However, on more challenging and recently introduced datasets such as SHTech and UBnormal, the performance is still relatively low, which highlights the limitations in the generalization ability of existing methods. Overall, while recent advances leverage self-supervised learning and multi-modal cues to push performance boundaries, robust SVAD under complex real-world scenarios remains an open research problem.

| Method          | Year | Ped2(AUC) | Avenue(AUC) | SHTech(AUC) | UBnormal(AUC) |
|-----------------|------|-----------|-------------|-------------|--------------|
| ConvAE [1]      | 2016 | 90.0%     | 72.0%       | /           | /            |
| STAE [2]        | 2017 | 91.2%     | 80.9%       | /           | /            |
| FutureFrame [3] | 2018 | 95.4%     | 85.1%       | 72.8%       | /            |
| MemAE [4]       | 2019 | 94.1%     | 83.3%       | 71.2%       | /            |
| BMAN [5]        | 2019 | 96.6%     | 90.0%       | 76.2%       | /            |
| MNaD [6]        | 2020 | 97.0%     | 88.5%       | 70.5%       | /            |
| AmmcNet [7]     | 2021 | 96.6%     | 86.6%       | 73.7%       | /            |
| MultiTVAD [8]   | 2021 | 99.8%     | 92.8%       | 90.2%       | /            |
| JigsawPuzzle [9]| 2022 | 99.0%     | 92.2%       | 84.3%       | 56.4%        |
| BDPN [10]       | 2022 | 98.3%     | 90.3%       | 78.1%       | /            |
| SenceAware [11] | 2023 | 98.1%     | 93.7%       | 83.4%       | /            |
| LERF [12]       | 2023 | 99.4%     | 91.5%       | 78.6%       | /            |
| Nomral-Pose VAD [13]|2023| /     | /           | 85.9%       | 71.8%        |
| SDMAE [14]      | 2024 | 95.4%     | 91.3%       | 79.1%       | 58.5%        |
| FGDVAD [15]     | 2024 | /         | 88.0%       | 78.6%       | 68.9%        |
| VADMamba [16]   | 2025 | 98.5%     | 91.5%       | 77.0%       | /            |
| MA-PDM [17]     | 2025 | 98.6%     | 91.3%       | 79.2%       | 63.4%        |

```
[1] M. Hasan, J. Choi, J. Neumann, A. K. Roy-Chowdhury, and L. S. Davis, “Learning temporal regularity in video sequences,” in Proceedings of the IEEE conference on computer vision and pattern recognition, 2016, pp. 733–742.

[2] Y. Zhao, B. Deng, C. Shen, Y. Liu, H. Lu, and X.-S. Hua, “Spatio-temporal autoencoder for video anomaly detection,” in Proceedings of the 25th ACM international conference on Multimedia, 2017, pp. 1933–1941.

[3] W. Liu, W. Luo, D. Lian, and S. Gao, “Future frame prediction for anomaly detection–a new baseline,” in Proceedings of the IEEE conference on computer vision and pattern recognition, 2018, pp. 6536–6545.

[4] D. Gong, L. Liu, V. Le, B. Saha, M. R. Mansour, S. Venkatesh, and A. v. d. Hengel, “Memorizing normality to detect anomaly: Memory-augmented deep autoencoder for unsupervised anomaly detection,” in Proceedings of the IEEE/CVF international conference on computer vision, 2019, pp. 1705–1714.

[5] S. Lee, H. G. Kim, and Y. M. Ro, “Bman: Bidirectional multi-scale aggregation networks for abnormal event detection,” IEEE Transactions on Image Processing, vol. 29, pp. 2395–2408, 2019.

[6] H. Park, J. Noh, and B. Ham, “Learning memory-guided normality for anomaly detection,” in Proceedings of the IEEE/CVF conference on computer vision and pattern recognition, 2020, pp. 14372–14381.

[7] R. Cai, H. Zhang, W. Liu, S. Gao, and Z. Hao, “Appearance-motion memory consistency network for video anomaly detection,” in Proceedings of the AAAI conference on artificial intelligence, vol. 35, no. 2, 2021, pp. 938–946.

[8] M.-I. Georgescu, A. Barbalau, R. T. Ionescu, F. S. Khan, M. Popescu, and M. Shah, “Anomaly detection in video via self-supervised and multi-task learning,” in Proceedings of the IEEE/CVF conference on computer vision and pattern recognition, 2021, pp. 12742–12752.

[9] G. Wang, Y. Wang, J. Qin, D. Zhang, X. Bao, and D. Huang, “Video anomaly detection by solving decoupled spatio-temporal jigsaw puzzles,” in European Conference on Computer Vision. Springer, 2022, pp. 494–511.

[10] C. Chen, Y. Xie, S. Lin, A. Yao, G. Jiang, W. Zhang, Y. Qu, R. Qiao, B. Ren, and L. Ma, “Comprehensive regularization in a bi-directional predictive network for video anomaly detection,” in Proceedings of the AAAI conference on artificial intelligence, vol. 36, no. 1, 2022, pp. 230–238.

[11] S. Sun and X. Gong, “Hierarchical semantic contrast for scene-aware video anomaly detection,” in Proceedings of the IEEE/CVF conference on computer vision and pattern recognition, 2023, pp. 22846–22856.

[12] C. Sun, C. Shi, Y. Jia, and Y. Wu, “Learning event-relevant factors for video anomaly detection,” in Proceedings of the AAAI Conference on Artificial Intelligence, vol. 37, no. 2, 2023, pp. 2384–2392.

[13] O. Hirschorn and S. Avidan, “Normalizing flows for human pose anomaly detection,” in Proceedings of the IEEE/CVF International Conference on Computer Vision, 2023, pp. 13545–13554.

[14] N.-C. Ristea, F.-A. Croitoru, R. T. Ionescu, M. Popescu, F. S. Khan, M. Shah et al., “Self-distilled masked auto-encoders are efficient video anomaly detectors,” in Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition, 2024, pp. 15984–15995.

[15] X. Tan, H. Wang, X. Geng, and L. Wang, “Frequency-guided diffusion model with perturbation training for skeleton-based video anomaly detection,” arXiv preprint arXiv:2412.03044, 2024.

[16] J. Lyu, M. Zhao, J. Hu, X. Huang, Y. Chen, and S. Du, “Vadmamba: Exploring state space models for fast video anomaly detection,” arXiv preprint arXiv:2503.21169, 2025.

[17] H. Zhou, J. Cai, Y. Ye, Y. Feng, C. Gao, J. Yu, Z. Song, and W. Yang, “Video anomaly detection with motion and appearance guided patch diffusion model,” in Proceedings of the AAAI Conference on Artificial Intelligence, vol. 39, no. 10, 2025, pp. 10761–10769.
```

Weakly Supervised VAD
----

Among all conventional DNN-based VAD methods, weakly supervised VAD (WVAD) has consistently been a focal point of research within the academic community. Although research on WVAD began somewhat later than that on SVAD, its use of video-level anomaly annotations aligns more closely with real-world application scenarios. Without the need for extensive manual labeling efforts, WVAD can effectively achieve anomaly detection in complex environments and attain relatively satisfactory detection performance.

As shown, the AUC scores on classic weakly-supervised datasets such as UCF-Crime and XD-Violence have seen steady but incremental improvements over recent years, primarily driven by advances in multiple instance learning and the incorporation of external knowledge (e.g., CLIP-based models). However, due to the low quality of these benchmark datasets and the inherent ambiguity in anomaly frame labeling, it has become increasingly difficult for current WVAD approaches to achieve breakthrough improvements. As a result, while newer methods push the boundaries with more sophisticated modeling techniques, the overall progress on these classic benchmarks has started to plateau, highlighting the urgent need for more reliable and higher-quality datasets to further advance the field.

| Method         | Year | UCF-Crime(AUC) | XD-Violence(AUC) | SHTech(AUC) |
|----------------|------|----------------|------------------|-------------|
| DeepMIL [18]    | 2018 | 75.40%         | /                | /           |
| GCN [19]        | 2019 | 82.12%         | /                | 84.44%      |
| CLAWS [20]      | 2020 | 83.03%         | /                | 89.67%      |
| MIST [21]       | 2021 | 82.30%         | /                | 94.83%      |
| MSL [22]        | 2022 | 85.62%         | 78.59%           | 97.32%      |
| S3R [23]        | 2022 | 85.99%         | 80.26%           | 97.48%      |
| UMIL [24]       | 2023 | 86.75%         | /                | /           |
| DMU [25]        | 2023 | 86.97%         | 81.66%           | /           |
| VadCLIP [26]    | 2024 | 88.02%         | 84.51%           | /           |
| CLIP-TSA [27]   | 2024 | 87.58%         | 82.19%           | 98.32%      |
| CMFVAD [28]     | 2024 | /              | 86.34%           | /           |

```
[18] W. Sultani, C. Chen, and M. Shah, “Real-world anomaly detection in surveillance videos,” in Proceedings of the IEEE conference on computer vision and pattern recognition, 2018, pp. 6479–6488.

[19] J.-X. Zhong, N. Li, W. Kong, S. Liu, T. H. Li, and G. Li, “Graph convolutional label noise cleaner: Train a plug-and-play action classifier for anomaly detection,” in Proceedings of the IEEE/CVF conference on computer vision and pattern recognition, 2019, pp. 1237–1246.

[20] M. Z. Zaheer, A. Mahmood, M. Astrid, and S.-I. Lee, “Claws: Clustering assisted weakly supervised learning with normalcy suppression for anomalous event detection,” in Computer Vision–ECCV 2020: 16th European Conference, Glasgow, UK, August 23–28, 2020, Proceedings, Part XXII 16. Springer, 2020, pp. 358–376.

[21] J.-C. Feng, F.-T. Hong, and W.-S. Zheng, “Mist: Multiple instance self-training framework for video anomaly detection,” in Proceedings of the IEEE/CVF conference on computer vision and pattern recognition, 2021, pp. 14009–14018.

[22] S. Li, F. Liu, and L. Jiao, “Self-training multi-sequence learning with transformer for weakly supervised video anomaly detection,” in Proceedings of the AAAI Conference on Artificial Intelligence, vol. 36, no. 2, 2022, pp. 1395–1403.

[23] J.-C. Wu, H.-Y. Hsieh, D.-J. Chen, C.-S. Fuh, and T.-L. Liu, “Self-supervised sparse representation for video anomaly detection,” in European Conference on Computer Vision. Springer, 2022, pp. 729–745.

[24] H. Lv, Z. Yue, Q. Sun, B. Luo, Z. Cui, and H. Zhang, “Unbiased multiple instance learning for weakly supervised video anomaly detection,” in Proceedings of the IEEE/CVF conference on computer vision and pattern recognition, 2023, pp. 8022–8031.

[25] H. Zhou, J. Yu, and W. Yang, “Dual memory units with uncertainty regulation for weakly supervised video anomaly detection,” in Proceedings of the AAAI Conference on Artificial Intelligence, vol. 37, no. 3, 2023, pp. 3769–3777.

[26] P. Wu, X. Zhou, G. Pang, L. Zhou, Q. Yan, P. Wang, and Y. Zhang, “Vadclip: Adapting vision-language models for weakly supervised video anomaly detection,” in Proceedings of the AAAI Conference on Artificial Intelligence, vol. 38, no. 6, 2024, pp. 6074–6082.

[27] H. K. Joo, K. Vo, K. Yamazaki, and N. Le, “Clip-tsa: Clip-assisted temporal self-attention for weakly-supervised video anomaly detection,” in 2023 IEEE International Conference on Image Processing (ICIP). IEEE, 2023, pp. 3230–3234.

[28] A. Ghadiya, P. Kar, V. Chudasama, and P. Wasnik, “Cross-modal fusion and attention mechanism for weakly supervised video anomaly detection,” in Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition, 2024, pp. 1965–1974.
```

Unsupervised VAD
----

Compared to other supervised VAD methods, unsupervised VAD~(UVAD) offers the advantages of eliminating the need for labor-intensive manual annotations and enabling the model to autonomously determine anomaly boundaries. On the one hand, it is difficult to clearly define what constitutes normal human behavior in real-world scenarios; for instance, riding a bicycle on a playground may be considered acceptable, whereas riding in a corridor is often deemed anomalous. On the other hand, it is impractical to anticipate all possible normal events in advance, especially in real-world applications. Therefore, early research into UVAD held significant academic value. However, with the advent of vision-language models and large language models that provide rich pre-trained semantic information, the advantages of UVAD have diminished. Currently, the progress of research in UVAD has been relatively slow.

It can be observed that, although recent approaches have made noticeable advances by integrating ideas from both SVAD and WVAD paradigms, the overall performance on large-scale and complex datasets such as UCF-Crime and XD-Violence still lags behind that of fully supervised or strongly supervised settings. Classic datasets like Ped2 and Avenue see higher AUC scores, indicating that UVAD methods generalize better to simpler scenarios, but struggle in the face of higher diversity and ambiguity. As shown by the recent results of C2FPL~\cite{216_al2024coarse} and CLAP~\cite{al2024collaborative}, even with the development of more sophisticated frameworks, there remains a significant gap to be closed before UVAD methods can match the robustness and accuracy of traditional paradigms on challenging benchmarks.

| Method           | Year | UCF-Crime(AUC) | XD-Violence(AP) | Ped2(AUC) | Avenue(AUC) | SHTech(AUC) |
|------------------|------|----------------|-----------------|-----------|-------------|-------------|
| Unmasking [29]   | 2017 | /              | /               | 82.2%     | 80.6%       | /           |
| DAW [30]         | 2018 | /              | /               | 96.4%     | 85.3%       | /           |
| MC2ST [31]       | 2018 | /              | /               | 87.5%     | 84.4%       | /           |
| STDOR [32]       | 2020 | /              | /               | 83.2%     | /           | /           |
| CIL [33]         | 2022 | /              | /               | 99.4%     | 90.3%       | /           |
| LBR-SPR [34]     | 2022 | /              | /               | 97.2%     | 92.8%       | 72.6%       |
| C2FPL [35]       | 2024 | 80.7%          | 80.%            | /         | /           | /           |
| CLAP [36]        | 2024 | 83.2%          | 85.7%           | /         | /           | /           |
| CKNN [37]        | 2024 | /              | /               | /         | 94.1%       | 89.0%       |
| InterUVAD [38]   | 2024 | /              | /               | /         | /           | 88.2%       |

```
[29] R. Tudor Ionescu, S. Smeureanu, B. Alexe, and M. Popescu, “Unmasking the abnormal events in video,” in Proceedings of the IEEE international conference on computer vision, 2017, pp. 2895–2903.

[30] S. Wang, Y. Zeng, Q. Liu, C. Zhu, E. Zhu, and J. Yin, “Detecting abnormality without knowing normality: A two-stage approach for unsupervised video abnormal event detection,” in Proceedings of the 26th ACM international conference on Multimedia, 2018, pp. 636–644.

[31] Y. Liu, C.-L. Li, and B. Póczos, “Classifier two sample test for video anomaly detections.” in BMVC, 2018, p. 71.

[32] G. Pang, C. Yan, C. Shen, A. v. d. Hengel, and X. Bai, “Self-trained deep ordinal regression for end-to-end video anomaly detection,” in Proceedings of the IEEE/CVF conference on computer vision and pattern recognition, 2020, pp. 12173–12182.

[33] X. Lin, Y. Chen, G. Li, and Y. Yu, “A causal inference look at unsupervised video anomaly detection,” in Proceedings of the AAAI Conference on Artificial Intelligence, vol. 36, no. 2, 2022, pp. 1620–1629.

[34] G. Yu, S. Wang, Z. Cai, X. Liu, C. Xu, and C. Wu, “Deep anomaly discovery from unlabeled videos via normality advantage and self-paced refinement,” in Proceedings of the IEEE/CVF Conference on computer vision and pattern recognition, 2022, pp. 13987–13998.

[35] A. Al-Lahham, N. Tastan, M. Z. Zaheer, and K. Nandakumar, “A coarse-to-fine pseudo-labeling (c2fpl) framework for unsupervised video anomaly detection,” in Proceedings of the IEEE/CVF Winter Conference on Applications of Computer Vision, 2024, pp. 6793–6802.

[36] A. Al-Lahham, M. Z. Zaheer, N. Tastan, and K. Nandakumar, “Collaborative learning of anomalies with privacy (clap) for unsupervised video anomaly detection: A new baseline,” in Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition, 2024, pp. 12416–12425.

[37] J. Yi and S. Yoon, “Cknn: Cleansed k-nearest neighbor for unsupervised video anomaly detection,” in Proceedings of the 33rd ACM International Conference on Information and Knowledge Management, 2024, pp. 3002–3011.

[38] Y. Nie, H. Huang, C. Long, Q. Zhang, P. Maji, and H. Cai, “Interleaving one-class and weakly-supervised models with adaptive thresholding for unsupervised video anomaly detection,” in European Conference on Computer Vision. Springer, 2024, pp. 449–467.
```

Open-set VAD
----

Deploying well-trained supervised models to detect unseen anomalies in real-world scenarios is crucial for the practical application of VAD. Since it is impossible to anticipate all possible anomalies in advance, OSVAD was proposed to address this challenge. Unlike traditional closed-set VAD, where anomaly types are predefined and known, OSVAD must identify unforeseen and unknown anomalies. Research on OSVAD is still limited compared to semi-supervised and weakly supervised VAD. Furthermore, with the rapid progress of VLMs and LLMs, OSVAD is gradually being replaced by training-free and instruction-tuned VAD. Due to the scarcity of related research, we focus on describing the few existing methods, rather than following our earlier framework. Generally, OSVAD can be divided into two main categories: open-set VAD and few-shot VAD.

While OSVAD methods have achieved competitive results on certain datasets, their overall performance is still constrained by the limited supervision available for unseen or rare anomaly types. For example, as shown by Zhu et al., the performance notably drops as the number of seen anomaly categories decreases, reflecting the inherent difficulty of open-set settings. Methods based on few-shot learning, such as Hu et al. and Huang et al., demonstrate promising results on simpler datasets like Ped2 and Avenue, but their effectiveness on more complex and large-scale benchmarks remains to be fully validated. Overall, although recent OSVAD approaches have made progress by leveraging meta-learning and cross-domain adaptation, the challenge of reliably detecting truly novel anomalies with minimal supervision still persists, highlighting the need for more robust and generalizable solutions.

| Method            | Year | UCF-Crime(AUC) | XD-Violence(AP)  | Ped2(AUC) | Avenue(AUC) | SHTech(AUC) |
|-------------------|------|----------------|------------------|-----------|-------------|-------------|
| MLEP [39]         | 2019 | /              | /                | /         | 92.80%      | 76.80%      |
| Zhu et al. [40]   | 2021 | 80.14%         | 69.61%           | /         | /           | /           |
|                   |      | (9 anomaly seen)| (4 anomaly seen)|           |             |             |
| Hu et al. [41]    | 2021 | /              | /                | 96.20%    | 85.80%      | 77.9%       |
|                   |      |                |                  | (13 sence seen)| (13 sence seen)| (13 sence seen) |
| Huang et al. [42] | 2022 | /              | /                | 95.12%    | 82.62%      | /           |
|                   |      |                |                  | (10 shot) | (10 shot)   |             |
| Aich et al. [43]  | 2023 | /              | /                | 96.95%    | /           | 71.60%      |

```
[39] W. Liu, W. Luo, Z. Li, P. Zhao, S. Gao et al., “Margin learning embedded prediction for video anomaly detection with a few anomalies,” in IJCAI, vol. 3, 2019, pp. 023–3.

[40] Y. Zhu, W. Bao, and Q. Yu, “Towards open set video anomaly detection,” in European Conference on Computer Vision. Springer, 2022, pp. 395–412.

[41] Y. Hu, X. Huang, and X. Luo, “Adaptive anomaly detection network for unseen scene without fine-tuning,” in Pattern Recognition and Computer Vision: 4th Chinese Conference, PRCV 2021, Beijing, China, October 29–November 1, 2021, Proceedings, Part II 4. Springer, 2021, pp. 311–323.

[42] X. Huang, Y. Hu, X. Luo, J. Han, B. Zhang, and X. Cao, “Boosting variational inference with margin learning for few-shot scene-adaptive anomaly detection,” IEEE Transactions on Circuits and Systems for Video Technology, vol. 33, no. 6, pp. 2813–2825, 2022.

[43] A. Aich, K.-C. Peng, and A. K. Roy-Chowdhury, “Cross-domain video anomaly detection without target domain adaptation,” in Proceedings of the IEEE/CVF Winter Conference on Applications of Computer Vision, 2023, pp. 2579–2591.
```

Open-vocabulary VAD
----

In real-world anomaly detection tasks, traditional methods typically rely on predefined anomaly categories or specific event labels, which fall under the paradigm of closed vocabulary. However, in practical applications, the types of anomalies are diverse and often unpredictable, making it difficult for a limited set of labels to cover all potential anomalous scenarios. To address this challenge, open vocabulary VAD has emerged. OVVAD enables models to represent anomalous events using open-ended natural language descriptions, rather than being restricted to the labels or categories seen during training.

Unlike OSVAD, OVVAD emphasizes the “semantic openness” of anomalous events, allowing detection models to recognize a wide array of anomalies described freely in natural language. This means users can query for anomalies using novel phrases (e.g., “someone suddenly collapsing” or “appearance of an unauthorized vehicle”) without predefined labels. Although OVVAD, as an extension of OSVAD, shares objectives and formats with WVAD, instruction-tuned VAD, and TVAD, it remains fundamentally distinct and is thus considered a separate category. Like OSVAD, research on OVVAD is limited, so we focus on describing the few existing methods rather than following our earlier framework.

The result reflects that OVVAD, as an emerging research direction, is still in its early stages, with overall performance lagging behind other more established paradigms. Although some methods, such as Wu et al., have achieved competitive results on UCF-Crime and Ped2, their performance on more challenging or diverse datasets, like UBnormal or Street Scene, remains relatively low. This indicates that current OVVAD methods still struggle to detect unseen and open-vocabulary anomalies robustly in real-world scenarios. In summary, while recent works have demonstrated the potential of integrating language models and open-set recognition to address the OVVAD task, reliable and generalizable detection of open-vocabulary anomalies remains a significant challenge for future research.

| Method                | Year | Dataset & Performance                                                  |
|-----------------------|------|------------------------------------------------------------------------|
| Wu et al. [44]        | 2024 | UCF-Crime(AUC) 86.40% XD-Violence(AP) 66.53% UBnormal(AUC) 62.94%     |
| LaGoVAD [45]          | 2025 | UCF-Crime(Acc) 51.72% XD-Violence(Acc) 78.13%                         |
| Yang and Radke [46]   | 2025 | Street Scene(AUC) 67.0% Ped2(AUC) 99.0% SHTech(AUC) 81.3%             |

```
[44] P. Wu, X. Zhou, G. Pang, Y. Sun, J. Liu, P. Wang, and Y. Zhang, “Open-vocabulary video anomaly detection,” in Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition, 2024, pp. 18297–18307.

[45] Z. Liu, X. Wu, J. Wu, X. Wang, and L. Yang, “Language-guided open world video anomaly detection,” arXiv preprint arXiv:2503.13160, 2025.

[46] Z. Yang and R. J. Radke, “Detecting contextual anomalies by discovering consistent spatial regions,” arXiv preprint arXiv:2501.08470, 2025.
```

Training-free VAD
----

In the field of VAD, severe imbalance between positive and negative samples, as well as difficulties in data annotation, have long been significant factors limiting model performance. With the rapid development of LLMs and MLLMs, researchers have discovered that the vast amount of pre-trained knowledge embedded in these models can be leveraged for anomaly detection without the need for additional model training. In this context, TVAD has emerged. The core idea of TVAD is to utilize the semantic interaction capabilities and multimodal understanding abilities of LLMs and MLLMs to first summarize videos into specific captions, and then analyze these captions to detect anomalies. It is worth noting that, although many works employing such models claim to belong to semi-supervised or weakly supervised VAD, they merely use the same types of data annotations as other VAD paradigms, without any actual model training. Therefore, we also categorize these methods within the scope of TVAD.

The result demonstrates that the TVAD paradigm, which focuses on temporal or segmented video anomaly detection, is gaining increasing attention in recent years. As shown, methods such as SUVAD and VERA have achieved notable improvements in both classic and large-scale datasets, especially in terms of AUC and AP scores. In particular, VERA achieves state-of-the-art performance on challenging benchmarks like XD-Violence, indicating the effectiveness of leveraging fine-grained temporal segmentation and multi-modal reasoning in TVAD tasks. However, there are still considerable gaps in performance across different datasets, and some methods are only evaluated on a limited subset of benchmarks, making it difficult to comprehensively assess their generalization ability. Overall, while TVAD methods are showing promising results by introducing more precise temporal modeling, robust detection under diverse and long-duration real-world scenarios remains a challenging open problem.

| Method                | Year | UCF-Crime(AUC) | XD-Violence(AP) | Ped2(AUC) | Avenue(AUC) | SHTech(AUC) |
|-----------------------|------|----------------|-----------------|-----------|-------------|-------------|
| LAVAD [47]            | 2024 | 80.28%         | 62.01%          | /         | /           | /           |
| Anomaly Ruler [48]    | 2024 | /              | /               | 97.40%    | 81.60%      | 83.50%      |
| SUVAD [49]            | 2025 | 83.90%         | 70.10%          | 96.80%    | 89.30%      | 80.20%      |
| VADSK [50]            | 2025 | /              | /               | 86.50%    | 74.20%      | 75.30%      |
| VERA [51]             | 2025 | 86.55%         | 88.26%(AUC)     | /         | /           | /           |

```
[47] L. Zanella, W. Menapace, M. Mancini, Y. Wang, and E. Ricci, “Harnessing large language models for training-free video anomaly detection,” in Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition, 2024, pp. 18527–18536.

[48] Y. Yang, K. Lee, B. Dariush, Y. Cao, and S.-Y. Lo, “Follow the rules: reasoning for video anomaly detection with large language models,” in European Conference on Computer Vision. Springer, 2024, pp. 304–322.

[49] S. Gao, P. Yang, and L. Huang, “Suvad: Semantic understanding based video anomaly detection using mllm,” in ICASSP 2025-2025 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP). IEEE, 2025, pp. 1–5.

[50] T. Foltz, “Video anomaly detection with structured keywords,” arXiv preprint arXiv:2503.10653, 2025.

[51] M. Ye, W. Liu, and P. He, “Vera: Explainable video anomaly detection via verbalized learning of vision-language models,” in Proceedings of the Computer Vision and Pattern Recognition Conference, 2025, pp. 8679–8688.
```

Instruction Tuning VAD
----

Compared to training-free VAD methods based on LLM/MLLM, constructing anomaly-related datasets and using them to perform instruction tuning on LLMs is also an important paradigm. Instruction tuning enables LLMs to transfer their general knowledge to specific anomaly detection tasks, thereby enhancing the model's understanding and discrimination of abnormal events. In recent years, with the continuous enrichment of open-source video anomaly datasets and advancements in multimodal annotation techniques, more and more researchers are exploring how to instruction-tune LLMs using high-quality abnormal videos and their language descriptions. Moreover, instruction tuning can not only directly update the parameters of the large model itself but also achieve efficient adaptation by freezing the large model and fine-tuning downstream modules. It is worth noting that model architectures under the instruction tuning paradigm are becoming increasingly diverse, including multimodal fusion architectures based on VLMs and LLMs, as well as hybrid models that combine GNNs, Transformers, or RAG to enhance reasoning capabilities.

With its flexible data-driven characteristics and strong knowledge transfer capabilities, instruction-tuned VAD is becoming an important development direction in the field of video anomaly detection, driving continuous improvements in accuracy, efficiency, and interpretability of VAD models.

The result shows that ITVAD methods, by leveraging large language and multi-modal models, have achieved impressive results on classic datasets. Both efficient module tuning and full fine-tuning strategies demonstrate strong performance, indicating the value of integrating advanced language-vision models for anomaly detection. However, differences in evaluation metrics and limited real-world validation mean that the generalization and robustness of these methods need further study.

| Method              | Year | Dataset & Performance                                                                                                            |
|---------------------|------|----------------------------------------------------------------------------------------------------------------------------------|
| VADLlama [52]       | 2024 | TAD(AUC) 88.13% UCF-Crime(AUC) 91.77%                                                                                           |
| CUVA [53]           | 2024 | CUVA(MMEval) 79.65 58.92 50.64                                                                                                  |
| HAWK [54]           | 2024 | HAWK(GPT-Guided) 0.283 0.320 0.218                                                                                              |
| VLAVAD [55]         | 2024 | Ped2(AUC) 99.00% Avenue(AUC) 87.6% SHTech(AUC) 87.2%                                                                            |
| Holmes-VAU [56]     | 2025 | HIVAU-70k(BLEU) 0.916 0.804 0.566 UCF-Crime(AUC) 88.96% XD-Violence(AP) 87.68                                                   |
| UCVL [57]           | 2025 | UCVL(GPT-4o) 63.8                                                                                                               |
| SlowFastVAD [58]    | 2025 | Ped2(AUC) 99.10% Avenue(AUC) 89.6% SHTech(AUC) 85.0% |

```
[52] H. Lv and Q. Sun, “Video anomaly detection and explanation via large language models,” arXiv preprint arXiv:2401.05702, 2024.

[53] H. Du, S. Zhang, B. Xie, G. Nan, J. Zhang, J. Xu, H. Liu, S. Leng, J. Liu, H. Fan et al., “Uncovering what why and how: A comprehensive benchmark for causation understanding of video anomaly,” in Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition, 2024, pp. 18793–18803.

[54] J. Tang, H. Lu, R. Wu, X. Xu, K. Ma, C. Fang, B. Guo, J. Lu, Q. Chen, and Y. Chen, “Hawk: Learning to understand open-world video anomalies,” Advances in Neural Information Processing Systems, vol. 37, pp. 139751–139785, 2024.

[55] Y. Jiang and L. Mao, “Vision-language models assisted unsupervised video anomaly detection,” arXiv preprint arXiv:2409.14109, 2024.

[56] H. Zhang, X. Xu, X. Wang, J. Zuo, X. Huang, C. Gao, S. Zhang, L. Yu, and N. Sang, “Holmes-vau: Towards long-term video anomaly understanding at any granularity,” in Proceedings of the Computer Vision and Pattern Recognition Conference, 2025, pp. 13843–13853.

[57] H. Chen, D. Yi, M. Cao, C. Huang, G. Zhu, and J. Wang, “A benchmark for crime surveillance video analysis with large models,” arXiv preprint arXiv:2502.09325, 2025.

[58] Z. Ding, H. Zhang, P. Wu, G. Pang, Z. Yang, P. Wang, and Y. Zhang, “Slowfastvad: Video anomaly detection via integrating simple detector and rag-enhanced vision-language model,” arXiv preprint arXiv:2504.10320, 2025.
```
