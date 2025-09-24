
Evaluation Metrics
====

Corresponding to the two task objectives of VAD, the evaluation metrics for VAD tasks are also divided into two categories. One focuses on assessing the model's ability to ground anomalous events in the temporal dimension, while the other evaluates the model's ability to understand anomalous events in the semantic dimension.

In the temporal dimension, commonly used evaluation metrics include AUC, ERR/EDR, and Accuracy. Additionally, there are metrics designed for detecting anomalous regions and trajectories, such as RBDC and TBDC.

In the semantic dimension, the most commonly used metric is AP. With the growing influence of VLMs and LLMs, VAD has also adopted some metrics to evaluate the performance of large models, such as BLEU and ROUGE. Furthermore, considering the complexity of video understanding tasks, particularly anomalous video understanding, some scoring metrics based on LLMs or MLLMs have also been proposed.

AUC (Area Under the Curve). 
----
AUC refers to the area under the ROC (Receiver Operating Characteristic) curve. The ROC curve is plotted by comparing the True Positive Rate (TPR) and the False Positive Rate (FPR) across different thresholds:

$TPR = \frac{TP}{TP + FN},~ FPR = \frac{FP}{FP + TN}.$

TP (True Positive) is the number of samples that are actually positive and correctly predicted as positive, TN (True Negative) is the number of samples that are actually negative and correctly predicted as negative, FP (False Positive) is the number of samples that are actually negative but incorrectly predicted as positive, and FN (False Negative) is the number of samples that are actually positive but incorrectly predicted as negative.

EER (Equal Error Rate) and EDR (Equal Detected Rate). EER refers to the error rate at the point where the FPR equals the FNR on the ROC curve. EDR represents the proportion of anomalies detected by the system under a specific detection threshold relative to the total number of anomalies. EER provides a balance point, while EDR emphasizes the completeness of detection. Particularly in anomaly detection, a high recall rate is crucial, as missing a true anomaly could have far more severe consequences than mistakenly labeling a normal event as anomalous.

Accuracy. 
----
Accuracy is a performance metric used in classification models or diagnostic tests, defined as the ratio of correct predictions to the total number of predictions:

$Accuracy = \frac{TP + TN}{TP + TN + FP + FN}.$

The definitions of TP, TN, FP, and FN remain consistent with those provided earlier. While accuracy is an intuitive metric for evaluating performance, relying solely on accuracy can be misleading in scenarios involving class imbalance. Consequently, within the domain of VAD, accuracy is less frequently employed compared to metrics such as the AUC.

RBDC (Region-Based Detection Criterion).
----
RBDC assesses the capability of a model to precisely localize anomalous regions within individual video frames. This metric computes scores by comparing the detected anomalous regions with annotated ground-truth regions:

$RBDC = \frac{Region_{model} \cap Region_{gt}}{Region_{gt}},$

where $Region_{model}$ represents the anomalous areas detected by the model, while $Region_{gt}$ represents the ground truth.
A higher RBDC score indicates superior spatial localization performance of the model, meaning it can more accurately pinpoint the locations of anomalies within video frames.

TBDC (Track-Based Detection Criterion).
----
TBDC evaluates the model's capability for detecting and tracking anomalies along the temporal dimension, measuring performance in grounding anomalies across consecutive video frames:

$TBDC = \frac{Track_{model} \cap Track_{gt}}{Track_{gt}},$

where $Track_{model}$ represents the anomalous tracks detected by the model, while $Track_{gt}$ represents the ground truth. 
This metric is particularly suited for scenarios where anomalous events exhibit temporal continuity, such as objects moving anomalously or events spanning multiple frames.
TBDC employs Intersection-over-Union (IoU) to quantify the overlap between predicted trajectories and ground-truth trajectories and emphasizes temporal continuity, thus ensuring that the model is capable not only of detecting anomalies in individual frames but also accurately tracking anomalies throughout the entire video sequence.

AP (Average Precision). 
----
AP refers to the area under the precision-recall curve. Precision represents the proportion of correctly identified positive samples, while recall (or sensitivity) measures the proportion of positive samples that are correctly identified. AP is particularly effective in scenarios with a limited number of positive samples (e.g., anomalous samples). In the VAD, this metric not only focuses on anomaly classification but also emphasizes the ability to localize anomalies at the video frame level. Nevertheless, for the sake of comparison with AUC, AP is categorized here as an evaluation metric for anomalous video understanding.

BLEU, ROUGE, METEOR: Text Similarity Evaluation Metrics. 
----
After the introduction of VLMs/LLMs into the VAD task, many works have treated it as a VQA task or a video captioning task, providing corresponding textual annotations. As a result, the evaluation metrics from the NLP field have been introduced into the VAD domain.

In natural language processing (NLP) tasks, text similarity evaluation metrics are widely used to assess the quality of generated text compared to reference text: BLEU (Bilingual Evaluation Understudy) evaluates translation quality by calculating the precision of n-gram matches between the generated text and the reference text, focusing on surface-level similarity. ROUGE (Recall-Oriented Understudy for Gisting Evaluation) is a recall-oriented metric commonly used for text summarization, which measures the overlap of units (e.g., n-grams, word sequences) between the generated and reference summaries. METEOR (Metric for Evaluation of Translation with Explicit Ordering) combines precision, recall, and synonym matching to calculate a weighted harmonic mean score. It incorporates stemming and synonym libraries to enhance semantic understanding.
These metrics provide quantitative benchmarks for model optimization but come with their own limitations. For example, BLEU is sensitive to word order but neglects semantics, ROUGE prioritizes recall but may overlook conciseness, and METEOR relies on external resources and has computational complexity. In tasks like video understanding, where subjectivity and flexibility are significant factors, the performance of these metrics is often suboptimal.

Evaluation Metrics Based on LLMs and MLLMs.
----
In the VAD, particularly in the video anomaly understanding domain, evaluation metrics based on LLMs and MLLMs are gradually emerging as novel and effective assessment methods. LLM-based evaluation metrics draw inspiration from text similarity evaluation methods in natural language generation tasks (such as ROUGE and BLEU) and leverage the powerful semantic understanding and generation capabilities of LLMs to more comprehensively measure the similarity between generated descriptions and ground truth annotations. LLMs can capture subtle semantic differences, contextual associations, and logical coherence in text:

$Metric_{\rm LLM} = {\rm LLM}(Result, \mathcal{Y}_{test})$

However, LLM-based metrics face issues such as instability, slow computation speeds, and a heavy reliance on the quality of prompt design.

In contrast, MLLM-based evaluation metrics combine video content and textual descriptions, utilizing a multi-modal fusion approach to enhance the ability to recognize complex scenarios and more accurately capture the semantic relationships and contextual consistency between video anomalies and textual descriptions:

$Metric_{\rm MLLM} = {\rm MLLM}(Result, \mathcal{X,Y}_{test})$

These metrics guide the model to understand the task requirements through carefully designed prompts and integrate visual information with textual content for comprehensive judgment. However, their effectiveness also heavily depends on the quality of prompt design and the efficiency of video feature extraction. Additionally, they come with high computational costs, requiring continuous optimization and adjustment for practical applications.
