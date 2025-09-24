Taxonomy
====

Traditional DNN-based VAD methods can be categorized into four distinct types based on the supervision signal: semi-supervised VAD (SVAD), weakly supervised VAD (WVAD), fully supervised VAD (FVAD) and unsupervised VAD (UVAD). 

Due to the difficulty of collecting anomalous data and the labor-intensive nature of annotation, fully supervised VAD has gradually fallen out of favor. Meanwhile, the rapid development of VLMs and LLMs has introduced new categories to VAD, including open-set supervised VAD (OSVAD), open-vocabulary VAD (OVVAD), training-free VAD (TVAD), and instruction tuning VAD (ITVAD).

Although the task objectives of VAD under different supervision paradigms are similar, they involve distinct training and testing setups. We illustrate these differences in the fig.

Comparison diagram between different types of VAD tasks
----
![Comparison](https://github.com/ShbGao-ProMax/A-Comprehensive-Survey-of-Video-Anomaly-Detection-Evolution-from-DNNs-to-MLLMs/blob/main/pic/difference.png)

Semi-supervised VAD
----
Semi-supervised VAD assumes that training videos only contain normal events during the training phase, i.e.,

$$\mathcal{Y}_{\text{train}} = \left( y_{\text{train}, t} \right)_{t=1}^{T},$$

$$y_{train,t} = 0.$$

Under this supervision paradigm, the model learns the normal patterns from normal data and treats samples deviating from these patterns as anomalies. In this setting, datasets typically exhibit no scene transitions or only a minimal number of transitions. Due to the absence of anomalous samples during training, the annotation cost for semi-supervised VAD is relatively low. However, training exclusively on normal samples may lead the model to classify any samples not present in the training set as anomalies, resulting in a high false positive rate. Moreover, this paradigm is often tightly coupled with specific scenes, meaning that even minor deviations, such as slight camera rotations, can cause catastrophic performance degradation.

Weakly supervised VAD
----
Compared to semi-supervised VAD, weakly supervised VAD provides stronger supervision signals. During training, both normal and anomalous videos are provided, but the anomalous videos only contain video-level labels. In other words, the model will be not provided the exact timestamps of anomalous events in the videos, i.e.,

$$\mathcal{Y}_{train,n} = \{y_{train,n,t}\}_{t=1}^{T},~ y_{train,t} = 0,$$

$$\mathcal{Y}_{train,a} = A, A \in \mathcal{A},$$

where $\mathcal{A}$ represent the set of anomaly classes contained in the dataset.
Due to the stronger supervision signals, weakly-supervised VAD usually achieves better performance than semi-supervised VAD and exhibits some adaptability to scene transitions. However, this paradigm imposes higher requirements on algorithm design, and collecting anomalous videos requires additional effort.

Unsupervised VAD
----
Unsupervised VAD aims to detect anomalies directly from completely unlabeled videos in an unsupervised manner. Under this paradigm, no division between training and testing sets is required, i.e.,

$$\mathcal{X} = \mathcal{X}_{test},~\mathcal{Y}_{train} = \emptyset.$$

Unsupervised VAD allows the model to continuously update itself during anomaly detection without relying on any data collection or annotation process. However, due to the lack of labels, unsupervised algorithms are often more complex and tend to exhibit inferior detection performance.

Open-set VAD
----
Open-set VAD aims to detect anomalies that are unseen during training. Specifically, the training set includes normal samples and anomalous samples with video-level labels,

$$\mathcal{Y}_{train,n} = \{y_{train,n,t}\}_{t=1}^{T},~ y_{train,t} = 0,$$

$$\mathcal{Y}_{train,a} = A,~A \in \mathcal{A}_{base},$$

where $\mathcal{A}_{base}$ represents the basic seen category of anomalies.

The test set consists of both anomalies seen during training and unseen anomalies, referred to as "seen anomalies" and "unseen anomalies," respectively, i.e.,

$$\mathcal{Y}_{train,a} = A,~A \in \mathcal{A},~ \mathcal{A} = \mathcal{A}_{base} \cup \mathcal{A}_{novel},$$

where $\mathcal{A}_{novel}$ represents the unseen category of anomalies. It is worth noting that open-set VAD typically does not require identifying the exact category of unseen anomalies. Compared to mainstream semi-supervised and weakly-supervised VAD, open-set VAD demonstrates strong scene generalization and holds significant value for real-world applications. However, this superior performance often relies on specially designed additional modules or the construction of pseudo anomalies to detect unseen anomalies.

Open-vocabulary VAD
----
Open-vocabulary VAD aims to precisely classify anomalies that have not been encountered in the training set. Specifically, the training set provides normal samples and anomalous samples with detailed labels. The test set includes anomalies seen in the training set as well as those unseen, referred to as visible anomalies and unseen anomalies. These are consistent with open-set VAD.
Unlike open-set VAD, open-vocabulary VAD requires not only detecting unseen anomalies but also identifying their specific categories. This setting enhances the model's adaptability in diverse scenarios, making it particularly effective in handling new types of anomalies in real-world applications. However, achieving open vocabulary VAD typically requires sophisticated model design and heavily relies on the rich prior knowledge learned by pre-trained models.

Training-free VAD
----
Training-free VAD aims to leverage the powerful prior knowledge of VLMs or LLMs for anomaly detection. Specifically, training-free VAD analyzes videos directly based on preset rules or general knowledge without requiring any adjustment to model parameters, represented as

$$\Phi(\theta;\mathcal{X}) = \Phi(\emptyset;\mathcal{X}).$$

In this setting, the detection system can identify anomalous events without relying on specific training data, while ensuring a certain level of detection performance. The advantage of training-free VAD lies in its efficiency and flexibility, enabling rapid adaptation to new scenarios and new types of anomalies, thereby significantly enhancing practical applicability. However, despite the absence of additional training, the model's performance remains dependent on the quality of predefined rules and prior knowledge. Moreover, while the VLMs/LLMs employed in this method exhibit strong capabilities, they are associated with high computational costs.

Instruction tuning VAD
----
Instruction tuning VAD aims to fine-tune pre-trained large models to optimize their performance in VAD tasks. Specifically, instruction fine-tuning VAD involves training the model on specific datasets, adjusting its parameters to better adapt to particular scenarios and task requirements. During this process, the model learns the characteristics of anomalous samples and adjusts its behavior based on user-specific instructions, thereby improving detection accuracy and robustness. The advantage of instruction fine-tuning VAD lies in leveraging the knowledge of pre-trained models while achieving personalized and targeted anomaly detection, enhancing the model's effectiveness in practical applications. However, this approach requires additional training data and computational resources, and the fine-tuning process may reduce the model's generalization ability on new tasks. Moreover, excessive fine-tuning may lead to overfitting the model to specific datasets, thereby compromising its performance in diverse scenarios.
