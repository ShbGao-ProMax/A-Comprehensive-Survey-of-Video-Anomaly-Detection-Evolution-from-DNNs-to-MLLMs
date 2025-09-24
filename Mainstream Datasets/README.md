Mainstream Datasets
====

For various VAD tasks, the existing literature provides a wealth of publicly available datasets that encompass diverse scenarios. Specifically, these datasets range from those focused on specific scenes to those covering a wide variety of complex situations. Moreover, differences exist across datasets in terms of the number of videos, average video duration, anomaly categories, and annotation methods. In the following tables, we provide a detailed comparison of the current mainstream datasets. 

***It is worth noting that some datasets were initially designed for specific VAD tasks; however, with the continuous advancement of technology, these datasets can now also be applied to other VAD tasks.***

***For instance, any semi-supervised or weakly supervised VAD dataset can be utilized for evaluating training-free VAD methods.***

Traditional SVAD Datasets
----
| Dataset               | Domain       | Video Samples | Total Frames | Anomaly Categories | Location      | Understanding | Audio |
|-----------------------|-------------|---------------|--------------|--------------------|---------------|---------------|-------|
| Subway Entrance       | Streetscape  | 1             | 86,535       | 5                  | Frame         |               |       |
| Subway Exit           | Streetscape  | 1             | 38,940       | 3                  | Frame         |               |       |
| UMN                   | Behaviors    | 5             | 3,855        | 1                  | Frame         |               |       |
| UCSD Ped1             | Streetscape  | 70            | 14,000       | 5                  | Bounding-box  |               |       |
| UCSD Ped2             | Streetscape  | 28            | 4,560        | 5                  | Bounding-box  |               |       |
| CUHK Avenue           | Streetscape  | 37            | 30,652       | 5                  | Bounding-box  |               |       |
| Street Scene          | Traffic      | 81            | 203,257      | 17                 | Bounding-box  |               |       |
| NWPU Campus           | Streetscape  | 547           | 1,466,073    | 28                 | Frame         |               |       |
| ShanghaiTech          | Streetscape  | 437           | 317,398      | 13                 | Bounding-box  |               |       |

### Subway Entrance 2008

The Subway Entrance dataset is a classic benchmark in video anomaly detection, recorded at the entrance of a New York City subway station. The single long video captures commuters passing through the turnstiles, with a simple background but multiple types of anomalies: wrong direction (passing through the entrance in reverse), jumping over the turnstile, tailgating (multiple people passing with one swipe), and loitering. The dataset consists of one long video with clearly labeled anomalies, making it a common baseline for early methods and frame-level anomaly detection evaluation.

HomePage: [link](https://vision.eecs.yorku.ca/research/anomalous-behaviour-data/sets/)

### Subway Exit 2008

The Subway Exit dataset is also collected at a New York subway station, but at the exit area. The video records people leaving the turnstiles. Anomalies include wrong direction, tailgating, and loitering. While similar to Subway Entrance, this dataset differs in viewpoint, lighting, and flow direction. It consists of one long video, with frame-level annotations, and is often used as a complementary validation set for anomaly detection methods.

HomePage: [link](https://vision.eecs.yorku.ca/research/anomalous-behaviour-data/sets/)

### UMN 2009

The UMN dataset is a classic dataset for behavior anomaly detection, featuring three different scenes (outdoor lawn, indoor lobby, indoor hallway), each with several video clips. In each video, normal behavior (people standing or walking slowly) suddenly shifts to anomalous behavior (all people start running, simulating emergency escape). The anomaly type is single, focusing on collective behavioral changes, making it suitable for testing the sensitivity of anomaly detection algorithms. Provides frame-level annotations, without object-level labels.

HomePage: [link](https://www.crcv.ucf.edu/research/projects/abnormal-crowd-behavior-detection-using-social-force-model/)

### UCSD Ped1 2010

UCSD Ped1 is a landmark dataset for street surveillance anomaly detection, captured at a pathway in UC San Diego. Normal behavior is pedestrians walking in one direction; anomalies include people riding bicycles, skateboards, or vehicles entering the scene, and group running. The dataset contains 70 video clips, with both frame-level and object-level (bounding box) anomaly annotations, enabling precise localization. Its fixed scene and small background variation make it ideal for evaluating detection of small objects and motion anomalies.

HomePage: [link](http://www.svcl.ucsd.edu/projects/anomaly/dataset.htm)

### UCSD Ped2 2010

UCSD Ped2 is similar to Ped1 but features a different camera angle and scene. It consists of 28 video clips, with normal pedestrian traffic and anomalies including bicycles, vehicles, and skateboards entering the scene. Like Ped1, it provides bounding box annotations, but anomalies are more concentrated spatially, making it suitable for evaluating detection of localized anomalies.

HomePage: [link](http://www.svcl.ucsd.edu/projects/anomaly/dataset.htm)

### CUHK Avenue 2017

The CUHK Avenue dataset was recorded at a campus path at the Chinese University of Hong Kong and consists of 37 video clips. Normal behavior involves students walking, while anomalies include sudden running, object throwing, abrupt direction changes, and loitering. The dataset provides object-level (bounding box) annotations for each anomaly, making it suitable for both detection and localization tasks. The background is complex, with moderate pedestrian density and diverse anomalies, testing the generalization capability of methods.

HomePage: [link](https://www.cse.cuhk.edu.hk/leojia/projects/detectabnormal/dataset.html)

###  Street Scene 2020

Street Scene is a large-scale video anomaly detection dataset featuring 81 video clips recorded on a busy city street. Normal behaviors include various traffic participants (pedestrians, bicycles, vehicles), while there are 17 types of anomalies, such as vehicles driving in the wrong direction, cars on sidewalks, jaywalking, and illegal U-turns. All anomalies are annotated with bounding boxes, making the dataset suitable for detection and localization in complex scenes. It offers a rich variety of scenes and targets, and is a popular recent benchmark.

HomePage: [link](https://www.merl.com/research/highlights/video-anomaly-detection)

###  NWPU Campus 2023

NWPU Campus is one of the largest public datasets for campus surveillance anomaly detection, recorded at the Northwestern Polytechnical University. It consists of 547 video clips and over 1.4 million frames. Normal behaviors are typical campus activities, while there are 28 types of anomalies like running, cycling, vehicles entering, and crowd gathering. All anomalies are frame-level annotated, covering broad scenes and diverse anomaly types, making it suitable for training and evaluating large-scale deep learning models. The dataset reflects the diversity and complexity of real-world surveillance.

HomePage: [link](https://campusvad.github.io)

### ShanghaiTech 2017

ShanghaiTech is a large-scale anomaly detection dataset collected from various locations in Shanghai, including campuses, shopping malls, and subway stations. It contains 437 video clips and over 317,000 frames. There are 13 categories of anomalies, such as cycling, running, fighting, and fence climbing. Each anomaly is annotated with bounding boxes, supporting both detection and localization. The diverse scenes and anomaly types make it a challenging and widely used benchmark in current research.

HomePage: [link](https://svip-lab.github.io/dataset/campus_dataset.html)

Traditional WVAD Datasets
----
| Dataset               | Domain       | Video Samples | Total Frames | Anomaly Categories | Location      | Understanding | Audio |
|-----------------------|-------------|---------------|--------------|--------------------|---------------|---------------|-------|
| UCF-Crimes            | Crime        | 1900          | 13,741,393   | 13                 | Frame         | Classify      |       |
| UCf-Crime Extension   | Crime        | 2183          | 14,475,793   | 15                 | Frame         | Classify      |       |
| XD-Violence           | Violence     | 800           | 114,096      | 6                  | Frame         | Classify      | ✔     |
| TAD                   | Traffic      | 344           | 721,280      | 4                  | Bounding-box  |               |       |
| CamNuvem              | Robbery      | 486           | 6,151,788    | 1                  | Frame         |               |       |
| UCVL (Not released)   | Crime        | 1699          |              | 13                 | Frame         | Classify      |       |
| DoTA                  | Traffic      | 4677          | 731,932      | 1                  | Frame         |               |       |

### UCF-Crimes  2018

UCF-Crime Extension is an expanded version of the UCF-Crimes dataset, with an increased number of videos (2183) and total frames (about 14.5 million), as well as more anomaly categories (from 13 to 15, including new types like "murder" and "public drinking"). The dataset continues with frame-level annotations and is suitable for event classification and detection. With its larger scale and more diverse crime types, it offers a more realistic testbed for generalization.

HomePage: [link](https://www.crcv.ucf.edu/projects/real-world/#:~:text=We%20construct%20a%20new%20large,Stealing%2C%20Shoplifting%2C%20and%20Vandalism.)

### UCf-Crime Extension 2021

UCF-Crime Extension is an expanded version of the UCF-Crimes dataset, with an increased number of videos (2183) and total frames (about 14.5 million), as well as more anomaly categories (from 13 to 15, including new types like "murder" and "public drinking"). The dataset continues with frame-level annotations and is suitable for event classification and detection. With its larger scale and more diverse crime types, it offers a more realistic testbed for generalization.

HomePage: [link](https://github.com/hibrahimozturk/temporal_anomaly_detection)

### XD-Violence 2021

XD-Violence is a large-scale dataset focused on the detection of violent and abnormal behaviors, featuring 800 video clips and over 114,000 frames. It covers 6 classes of violence and anomalies (e.g., fighting, quarrel, robbery, etc.). Each video contains audio (✔), enabling research in multimodal (audio-visual) anomaly detection. All anomalies are labeled at the frame level, making the dataset suitable for classification and localization tasks.

HomePage: [link](https://roc-ng.github.io/XD-Violence/)

### TAD 2021

TAD is a traffic-focused anomaly detection dataset, consisting of 344 videos and over 721,000 frames. Anomalies include 4 main types such as traffic accidents, overspeeding, and wrong-way driving. All anomalies are annotated at the object level (bounding box), enabling precise localization. The dataset is suitable for traffic event detection and autonomous driving safety research, covering a variety of environments like city roads and highways.

HomePage: [link](https://github.com/ktr-hubrt/WSAL)

### CamNuvem 2022

CamNuvem is a robbery-focused anomaly detection dataset, consisting of 486 video clips and approximately 6.15 million frames. All videos are from real surveillance scenarios, with a single anomaly category: robbery. Each anomaly is frame-level annotated. The dataset covers diverse scenes, such as banks, gas stations, and stores, making it a leading dataset for robbery event detection in surveillance video research.

HomePage: [link](https://github.com/daviduarte/camnuvem-dataset)

### UCVL (Not released) 2024

UCVL (UCF Crime Video Localization) is a new dataset developed by the UCF team for localization of crime events, containing 1699 videos and 13 types of crimes and anomalies, all frame-level annotated. The dataset emphasizes spatio-temporal localization of anomalous events, enhancing practical utility in real surveillance scenarios. Note: This dataset has not been publicly released; refer to the following links for related papers and examples.

HomePage: Not released

### DoTA 2021

DoTA is one of the largest datasets for traffic anomaly detection, with 4677 video clips and about 731,932 frames. All videos are collected from real traffic cameras, focusing on a single anomaly type: traffic accidents. Anomalies are labeled at the frame level. DoTA features diverse scenes, including various weather conditions, traffic flows, and road types, making it highly suitable for research in autonomous driving and intelligent transportation.

HomePage: [link](https://captain-whu.github.io/DOTA/dataset.html)

Open-world Datasets
----
| Dataset               | Domain       | Video Samples | Total Frames | Anomaly Categories | Location      | Understanding | Audio |
|-----------------------|-------------|---------------|--------------|--------------------|---------------|---------------|-------|
| Ubnormal              | Multiple     | 543           | 236,902      | 22                 | Pixel         | Classify      |       |

### Ubnormal 2021

Ubnormal is a large-scale, multi-scene, multi-category video anomaly detection dataset released by the UPC (Universitat Politècnica de Catalunya) team in 2023. It consists of 543 videos and 236,902 frames, covering 22 categories of anomalies (such as fighting, stealing, fainting, crowd gathering, jaywalking, etc.) across various scenes (streets, malls, subways, campuses, traffic, etc.).

A key feature of Ubnormal is its pixel-level annotation, which not only marks the frames containing anomalies but also provides precise pixel-wise segmentation of the anomalous objects—an extremely rare property among anomaly datasets.

All events are also multi-label classified, supporting complex scenarios where multiple anomalies may occur simultaneously. Ubnormal is suitable for anomaly detection, localization, video segmentation, and action recognition tasks, making it one of the most comprehensive and challenging benchmarks in video anomaly detection.

The dataset does not include audio.

HomePage: [link](https://github.com/lilygeorgescu/UBnormal)


LLM-based Datasets
----
| Dataset               | Domain       | Video Samples | Total Frames | Anomaly Categories | Location      | Understanding | Audio |
|-----------------------|-------------|---------------|--------------|--------------------|---------------|---------------|-------|
| CUVA                  | Multiple     | 1000          | 3,345,097    | 11                 | Time Duration | Video QA      | ✔     |
| ECVA                  | Multiple     | 2500          | 19,042,560   | 21                 | Time Duration | Video QA      | ✔     |
| VANE-Bench            | Multiple     | 325           | 951,482      | 19                 |               | Video QA      |       |
| PreVAD (Not released) | Multiple     | 35279         |              | 35                 | Frame         | Video QA      |       |
| HIVAU-70k             | Multiple     | 5443          | 13,855,489   | 15                 |               | Video QA      | ✔     |
| UCA                   | Crime        | 1854          | 11,817,597   | 13                 | Frame         | Video QA      | ✔     |
