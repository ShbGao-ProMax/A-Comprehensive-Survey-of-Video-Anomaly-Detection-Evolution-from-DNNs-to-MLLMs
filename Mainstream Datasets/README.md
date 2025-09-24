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

Traditional WVAD Datasets
----
| Dataset               | Domain       | Video Samples | Total Frames | Anomaly Categories | Location      | Understanding | Audio |
|-----------------------|-------------|---------------|--------------|--------------------|---------------|---------------|-------|
| UCF-Crimes            | Crime        | 1900          | 13,741,393   | 13                 | Frame         | Classify      |       |
| UCf-Crime Extension   | Crime        | 2183          | 14,475,793   | 15                 | Frame         | Classify      |       |
| XD-Violence           | Violence     | 800           | 114,096      | 6                  | Frame         | Classify      | ✔     |
| TAD                   | Traffic      | 344           | 721,280      | 4                  | Bounding-box  |               |       |
| BOSS                  | Multiple     | 16            | 48,624       | 11                 | Frame         | Classify      | ✔     |
| CamNuvem              | Robbery      | 486           | 6,151,788    | 1                  | Frame         |               |       |
| UCVL (Not released)   | Crime        | 1699          |              | 13                 | Frame         | Classify      |       |
| DoTA                  | Traffic      | 4677          | 731,932      | 1                  | Frame         |               |       |

Open-world Datasets
----
| Dataset               | Domain       | Video Samples | Total Frames | Anomaly Categories | Location      | Understanding | Audio |
|-----------------------|-------------|---------------|--------------|--------------------|---------------|---------------|-------|
| Ubnormal              | Multiple     | 543           | 236,902      | 22                 | Pixel         | Classify      |       |

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
