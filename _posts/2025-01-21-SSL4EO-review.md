---
layout: archive
title: 'SSL4EO-2024: A review of the 1st summer school on “Self-Supervised Learning for Earth Observation”'
date: 2025-01-21
permalink: /posts/SSL4EO-2024-review/
author_profile: true
tags:
  - SSL4EO
  - summer course
  - workshop
---

![image_info](https://lh3.googleusercontent.com/pw/AP1GczMe-dzf6SSNUfbOkSEf5IEiNkJT9EhiqYNnfbHbIHFyTsJU5nFeZFay8W_POU_k9gxFITX5HtUfJ__4eknCCG2DaT64xNV1dMBNioyhUZ7qla4nLy3sxyTUcUsZ-IWB_-FLnIdtfFqfcFQcKZA5ZZPh=w2880-h1272-s-no?authuser=0)
*The SSL4EO-2024 cohort with 40 participants from 17 institutions (sold out!)*

Learning representations is at the heart of modern machine learning. While supervised deep learning has led to major advances, many crucial applications with limited reference data cannot easily profit from these promises. Self-supervised learning (SSL), a research direction aiming to learn semantic representations from unlabeled data, has seen recent advances and seems a promising direction to explore to better interpret Earth observation (EO) data like optical satellite images, synthetic aperture radar, or climate data.

In order to support further progress at the intersection of SSL and EO, we organized the first SSL4EO summer school in July 2024 in Copenhagen. 
This full-week program brought together leading experts working on SSL and EO to teach recent advances and discuss open research questions at this intersection. We were very happy that the first cohort of PhD students joining this format was sold out. The 40 participants from 17 international institutions heard from 8 invited speakers and worked on mini-projects to gain hands-on experience with the methods discussed. Thanks to the generous support from [Danish e-infrastructure Consortium (DeiC)](https://www.deic.dk/en) which provided access to their GPU-cluster during the course, the participants studied the role of augmentations, learning objectives, architectural design, and sampling strategies.

**Real-World Impact of Earth Observation Data**\
EO data are the key to understand important processes on Earth. How do human activities affect our ecosystems? How does climate change influence the harvest of crops? How do natural hazards such as wildfires, droughts, heat waves, floods, landslides, tropical cyclones, volcanic activity, earthquakes, and avalanches impact our society?

All these major questions can be better understood with the help of EO data. However, while the raw observations provide an abundant source of unlabeled data (speaking petabytes of data), we need efficient, scalable, and robust methods to extract the information we need.

<img src="https://lh3.googleusercontent.com/pw/AP1GczO-9Gg3T6L7ECe-bmZYY-XStdwUs93onvcNE1IH6orBtREqLrvFK1oIjcqPR132vD9SegqIP9E221UGbcUNiKwXO8K-G7qCwyH9qVSL-egP546fYW87O2U_Pg7vEFxcWSbe5BFKQW0geSkasP0r5dHT=w1186-h1582-s-no?authuser=0" alt="randall" width="49%"/>
<img src="https://lh3.googleusercontent.com/pw/AP1GczMi4gpFxkJyT3hOipMSYJuFRDPRJrs2Ti9K59o5D5TtCZxfobgrYJF4j6NjCSfKL66e7633VpQ-3f1VU3sUhyx0foemc-PNuLtK5cgUwmYMMX7SxoAfAcT-HrALaXypzKRmvJ0uCWxLfZfBdwcR9lDo=w1186-h1582-s-no?authuser=0" alt="randall" width="49%"/>
*Randall Balestriero introducing the core principles of self-supervised learning*

**From the Core Principles of SSL to the Key Characteristics of EO Data**\
Randall Balestriero (Brown University, Meta AI Research), the first author of the [Cookbook of SSL](https://arxiv.org/abs/2304.12210) kicked off the course with a deep introduction to SSL and an extensive summary of small “tricks” that add up to large performance gains. Randall’s perspective is that “_SSL is a superset of supervised and unsupervised learning_”. Puzhao Zhang (DHI) summarized important [EO sensors and their characteristics](https://business.esa.int/newcomers-earth-observation-guide) for several remote sensing applications and discussed the opportunities and challenges for machine learning. These introductions set the foundation to look at the potential of EO data and its metadata for learning representations. Nico Lang (University of Copenhagen) introduced some key ideas of prior works such as [Geography-Aware Self-Supervised Learning (GASSL)](https://arxiv.org/abs/2011.09980) and [Seasonal Contrast: Unsupervised Pre-Training from Uncurated Remote Sensing Data (SeCO)](https://arxiv.org/abs/2103.16607), which exploit the _geospatial_ and _temporal_ aspects of EO data to design better augmentations and thus positive pairs for SSL. The third key aspect of EO is _multi-modality_. EO data from different sensors and map products can be aligned at virtually no costs using geolocation and time information, as shown in [MMEarth: Exploring Multi-Modal Pretext Tasks For Geospatial Representation Learning](https://vishalned.github.io/mmearth/). Datasets like MMEarth can for example be used to train multi-modal, cross-modal, or single-sensor encoders that aim to yield general-purpose representations that generalize to diverse downstream tasks.

**Encoding Geospatial Data**\
One focus topic was _deep location encoders_ and how geospatial data can be represented in neural networks. Marc Rußwurm (Wageningen University) gave a lecture on the foundations of storing geospatial data and the lessons learned from the literature on implicit neural representations that are highly driven by the development of [Neural Radiance Fields (NeRFs)](https://www.matthewtancik.com/nerf). He showed how these techniques impact real world applications like e.g. [global-scale species distribution modelling](https://www.climatechange.ai/blog/2023-09-05-grant-species-mapping) and presented their recent work that introduces principles from Geodesy for [Geographic Location Encoding with Spherical Harmonics and Sinusoidal Representation Networks](https://marcrusswurm.com/locationencoder/). Konstantin Klemmer (Microsoft Research) presented how such geographic location encoders can be learned in a self-supervised way by leveraging techniques known from [CLIP (for Contrastive Language-Image Pre-training)](https://arxiv.org/abs/2103.00020), in their approach called [SatCLIP: Global, General-Purpose Location Embeddings with Satellite Imagery](https://arxiv.org/abs/2311.17179).

**Towards Earth and Climate Foundation Models**\
Since SSL strategies are also driving the development of large pre-trained models - also termed *Foundation models* - another big topic was the development of such models for EO data. We had the pleasure to hear Xiaoxiang Zhu’s (TUM) perspective [On the Foundations of Earth and Climate Foundation Models](https://arxiv.org/abs/2405.04285) covering questions like “_Why do we need them?_” or “_How does the ideal Earth FM look like?_”. One such model called DOFA (Dynamic One-For-All) that can be applied to data from different sensors was presented by Zhitong Xiong (TUM) from their work called [Neural Plasticity-Inspired Multimodal Foundation Model for Earth Observation](https://arxiv.org/abs/2403.15356). The key idea is to condition the model on the sensors’ wavelengths and pre-train on a multi-sensor dataset covering a range of wavelengths from the visible to the microwave spectrum (SAR data).

***"So What?"***\
This is how Bruno Sanchez-Andrade Nuño (Clay) started his session to get our cohort out of their comfort zone - which means stop thinking about technical challenges for a moment and think beyond the models. “_The model itself is important, but the product and stories around it are what makes it work._” Bruno summarized his thoughts for a detailed read in this post: [If you think "AI for Earth" is about AI on Earth data, you are not paying attention](https://www.linkedin.com/pulse/you-think-ai-earth-data-paying-attention-bruno-sanchez-andrade-nu%25C3%25B1o-u9hsf/?trackingId=FGmwqgMYS4ylWUdCBq%2FTig%3D%3D) and Ankit Kariryaa (KU) responded in his [Reflections on the PhD Course SSL4EO](https://www.linkedin.com/pulse/convergence-collapse-reflections-phd-course-learning-earth-kariryaa-jzguf/).

Following this discussion, Jan Dirk Wegner (University of Zurich) provided some answers to this question in his keynote sharing recent advances in crucial applications covering [snow depth estimation at country-scale](https://doi.org/10.1016/j.isprsjprs.2023.01.017), [high-resolution species distribution modelling](https://doi.org/10.5194/isprs-annals-X-2-2024-41-2024), and [remote monitoring of armed conflicts](https://arxiv.org/abs/2406.02506).

During this energetic week, we not only gained new knowledge, but also enjoyed several social events, dinners, museum visits, and a boat cruise though the waters of Copenhagen. 
A new little community was born. 

To close this review, I would like to leave you with a piece called “EPOCH” a visual representation of Earth created by Kevin McGloughlin:

<iframe src="https://player.vimeo.com/video/309715467?badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" width="1920" height="1080" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write; encrypted-media" title="EPOCH"></iframe>
>Epoch is a visual representation of our connection to earth and it's vulnerable glory.\
>Our time here is esoteric, limited and intangible.\
>The fragility which exists in all aspects of life is one thing that is certain.\
>We are brittle, and so is Mother Earth.


**Acknowledgement**: This course was supported by the [University of Copenhagen](https://ku.dk/english), [Danish e-infrastructure Consortium (DeiC)](https://www.deic.dk/en), and the [Pioneer Centre for AI](https://www.aicentre.dk/).


# Resources

- Course website: <https://ankitkariryaa.github.io/ssl4eo/>

- Recordings: [[Youtube playlist](https://youtube.com/playlist?list=PLZbT99RJ8DPM2VtPhgWaACm9uiEmRfB6t&si=8mS3RoxW7680uYa8)]

- Slides: [[google drive](https://drive.google.com/drive/folders/1w98tdDctMOVy0ToD1lt9ZM3V2vV3VXtV?usp=sharing)]

- Waiting list: *Would you be interested in a future edition of this summer school? Please sign up for the waiting list and let us know what topic you would be interested in.* [[form](https://forms.gle/pq7kFhNUGCpyrav17)]


## Reading list

[A Cookbook of Self-Supervised Learning](https://arxiv.org/abs/2304.12210)

[VICReg: Variance-Invariance-Covariance Regularization for Self-Supervised Learning](https://arxiv.org/abs/2105.04906)

[SimCLR: A Simple Framework for Contrastive Learning of Visual Representations](https://arxiv.org/abs/2002.05709)

[BYOL: Bootstrap your own latent: A new approach to self-supervised Learning](https://arxiv.org/abs/2006.07733)

[Barlow Twins: Self-Supervised Learning via Redundancy Reduction](https://arxiv.org/abs/2103.03230)

[MAE: Masked Autoencoders Are Scalable Vision Learners](https://arxiv.org/abs/2111.06377)

[ConvNeXt V2: Co-designing and Scaling ConvNets with Masked Autoencoders](https://arxiv.org/abs/2301.00808)

[Benchmarking Representation Learning for Natural World Image Collections](https://arxiv.org/abs/2103.16483)

[Geography-Aware Self-Supervised Learning](https://arxiv.org/abs/2011.09980)

[Seasonal Contrast: Unsupervised Pre-Training from Uncurated Remote Sensing Data](https://arxiv.org/abs/2103.16607)

[MMEarth: Exploring Multi-Modal Pretext Tasks For Geospatial Representation Learning](https://vishalned.github.io/mmearth/)

[Geographic Location Encoding with Spherical Harmonics and Sinusoidal Representation Networks](https://marcrusswurm.com/locationencoder/)

[Spatial Implicit Neural Representations for Global-Scale Species Mapping](https://arxiv.org/abs/2306.02564)

[SatCLIP: Global, General-Purpose Location Embeddings with Satellite Imagery](https://arxiv.org/abs/2311.17179)

[On the Foundations of Earth and Climate Foundation Models](https://arxiv.org/abs/2405.04285)

[Neural Plasticity-Inspired Multimodal Foundation Model for Earth Observation](https://arxiv.org/abs/2403.15356)

[Snow depth estimation at country-scale with high spatial and temporal resolution](https://doi.org/10.1016/j.isprsjprs.2023.01.017)

[Sat-SINR: High-Resolution Species Distribution Models Through Satellite Imagery](https://doi.org/10.5194/isprs-annals-X-2-2024-41-2024)

[An Open-Source Tool for Mapping War Destruction at Scale in Ukraine using Sentinel-1 Time Series](https://arxiv.org/abs/2406.02506)

# Impressions

<script src="https://cdn.jsdelivr.net/npm/publicalbum@latest/embed-ui.min.js" async></script>
<div class="pa-carousel-widget" style="width:100%; height:600px; display:none;"
  data-link="https://photos.app.goo.gl/Sn2bYybqyktznJh1A"
  data-title="SSL4EO-2024 summer course in Copenhagen"
  data-description="31 new items added to shared album"
  data-delay="2"
  data-background-color="#ffffff">
  <object data="https://lh3.googleusercontent.com/pw/AP1GczOpBEqdfa6eAFVwo5FolF5ovGpuBj_JyGsD87A7nTVXmNFQlWtMikno9WoYGMaNGQMB8CKYfK5lszuWwQi2N-0_y1ZgmVeTOiCddBIpHsfdHggylLY=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczN2QuwlmKlJ8-3LHC-P6K5yqa9UTomzc2WF162AnvQh2X9BZxvzsmDzKDIGuKsJ_1uHvw5KjcnCP2EnkSKYINzvM_N-HcFHzgJyDm0K0Z_LjSqlyoY=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczMBgP2aFxg8rf41bEQm77YLBZ1qC-B70dZJi7iiKg6oPPNFmyEjrHALSNvATcWJDzx80_a2HLL8QKP03PfEvs1_oJ60ZdBR6aCtGbZHcxl5S551w9U=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczNT8zWl4fXNRUKWycxx_iWCnb2e4F_wEDEC4txE-aFvSxXjO_gdAEJUIVO9vrZmmcQKBET7Ik9zdmriuLIAgpP7su8XWT0bSy-TsxnPWM264UGUhSo=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczOuC2DsdFeVrwPfwncoPKo36Kqq9W9eIAvPk-NBOY1JoDG_7kl1wd8MAsoglxXKSxl4eoApNf3SwgzYGPfSZlCJIEkcN9YDEXL37ktaAFDj34NSbqw=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczP_EGMHunAse5QKW9jZiLSczaujdGUu_7FB-rtfThsRY7UB8c_rmVyySw1ABNgmvvxxbUcrs3XRzYnXsAJUJn0Thyd0r45PpLuWsIY4qRHwp4-HXis=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczPFExc4JJH9D8Y2g32OA_Oek2VWbYAH_Wq9RYgdt3497Bnycw-LNXPG-FpznfDGKbZmWkG38NyfCKxsaTcqxXxDsESRUVRPEkr7HEz5ekP4bRsevU4=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczOmHzc4TtRj2EO1MPfcfW6N1T-ODVjWO_lf16EGRivV10268mUJMKZDCMyRdpQRMTuWvTNXId5MkByk6lfFpPsVx16aRbVItMNxaYSbLj58tYTTXCU=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczOq_t8P2UUwlq1KP1JWjWZ8pBLsTYB3PfR8nzsyLqIgZEDo5KDCwQVToR_AuFhZJBto-fInCKG9BiYJVSSzTUOghRTpS9k-NjpzP03X6rjVpkJWOMQ=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczNHgIGxhBMGiKz1stkTPvsroESpSGhKqUkRBqWSOUQ3VcmuvitvGVZ6_I8ywFQNiVIq9gAVv50Kwy2sGwrh42Bk6fe9zYoE0AWgeSfkFiDYTLWgXfk=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczNHpD_E5O0Q7l83ChC2X_57oonM2K6iwHQVlNQgf3H1-kjTKphWrXJ6kga91eHd38tGVyhNdFOXx3h3K7KCwnYM66KRXjATzpjNCIBO2J63Q7uyeCo=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczOestRT3MLtlM__UJof8r4RcXHAXITtzqLD5J104jM9NeXRBYuoyRWIJaKqV3GD9AFO9WaLV6CCCwqFuZe2WgohzVQEYcJo-JkfBoJVd_csjWKcOZY=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczNHjsGM4W2_WBQ_AuNS3n6hdDhZ6cxn-mzxCnB9xzoW5cNeuVTfUHmBgUIA83zS1sffL6evUBpqBHUIt-T6uFwWZUWCNWs6gPB117HTtlHne_PdWSw=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczOGmmEVXStVwOx7ImnMjbqANVvYKFGcbqwnSY1kqkqOirdilr-BvYRCHhfr1_9Wq5RIaQB_7YTprHmgILz3PpyzwIRiKzhYFJoBhdEONC81tBhOEVk=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczN0h6FoPXxBDTfxQK8Auez4vc8eQCwvHeiAV8mnWSZJNjc_lN8dz_731aeg6tgKYBc5EU1OU72AsQCMgMmuTGXZ0k_9xIN51ng_WqEYB-20tF6Puxk=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczNF7WK64_hhu7NtqjUEFcvRzIvzcqD0ld5mwSwPKyosx3CXjuM6X6FF_DHflULoGJ1Ck7Pq4eu3QnKmM3yHJAMz7K8nRiijCE39Qa5s0aiOarwPFUc=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczPkoLDhdVoZkwfliGKUTny7o4OQsl0mmC-FER5e0jG8IOzYoNr5qy3yEwQMy9o10Xv9Hole_ril4dvYGuwBvCciHQvQk6fIgzuMLVuuqQF8XT067pk=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczMd9YhY2tbhoCvqfhe_OFfoUmg070jqaf3g3eQ4zCITnjg1pt_5YW9aG07E3NOzpxceE-fq_FRniA5BMv51tBmpBikYt73ZTUJLi1rLIVFqaBnj9jE=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczP0FwHpY92yWaGYJ6uXnnc9IZeDKcIcp4yETNuKsqzGhlmBnU-PnRSjlfhk0ionFLldl3mVTgjOnq_CTOYs_b0hUF_YggN5wVY5wSWgRfCF3V_Ipic=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczM5AlAg93FxVI4tK2b69oqZVqVRNzQKZ69MrmUrK2ClUdEDkKtOHKRmHjf_zH3xjwdO3VOOqo9kY058vpp5ELnPjDlpQ7KPphvfFcIj3jit4NaSXpE=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczNE_Yu_47444U7859lahmubki0X73WYJ4D6O8sll5hEsarcQb3oemBP1vUBJxtoG62edos4RCciSowWQffB-k_v5xhTGdtYkOyNkeM_kBE8Pt-o00Q=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczMH2MCfQECWtRHa0P4Db6on5PK-0xYAhXlAZ7TQhx-J7ltWXNv-mql1i7qkfA0yj_TzS_izu7vvVqZ8QT2CBNU1WSrFYHoRBW-tXQzDDBroAvj64qE=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczNa3tIdCiflEtzJaUzBZOy77XAcrxveist4ARB-EK4dKnqftaNsvdndoy51yuLYeTKGNLPoZ6a6H5t2FwlzX7vsE93zL05N3XJqo4rHXWKzF3Lltgs=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczNFm461HN5YSxFE8-qJYLivpoVNULvIRQBzPPuma47fZumIYktN_Z-DMjk5aD8tURg4JdCT8gSe4chcUWJya0ryBqMuU4qr806oWqmIMM89DVcB3C8=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczMDyRkO7tH7ZVXUK0DcHYDY1HsNImSleMVTDQ2iDmIcQqXoeEmf26sMwqDFbAVC_49slvSXIdFWyydni7O4f3NHz3tayrNJhgVvmL1HgPdGfaDL_tg=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczMmah5CDcLB2X3YGCorwlNXSTYKwRH2Z7Etpg3uu1kHq2udJ4OxlUcVJ6QbT0iBfF2ihrhWikGEWLJsUwGmht3yMxvyHZsFlKzi88qDGZ68L4Hm-vk=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczNkEO5hxVbmG4PaxWjtrK5JGBenLg565B0i_bY5VEZYFO6ThMUsoOnG3ErkUQ2pmc49tNRWXACsqGDEao08W4ZhHWty5uYdvWCpUJqYKaYZ_FIeRxg=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczMo7LGWlgFfBIgJ7NaLN_CjnZyGrtKoix0h6JNSZ37-xVskDr6pcMs1m-LTemMTPvyHGgvEIzB_Yj23U9HVGVb9wBUqP5JMCJdXMMUxO8Xu_IdOYK4=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczMzdFrGUaqo2HXIK1TKEFHV4X_iSGrrZvKZGpA-02n5Q4Q0Dzk6vRpOAvR1e8T89XKNveB_vDMqWqnCS8G4TYM1XsS3AnHJ3s4UOsrHMZitlcq5o8A=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczMhCNcznx5Z7Zix3wJVfzRD8sMu26x3qEUHsAYLiphohti6S9KkB4pk8onyYj_eO_DYvsi_PSIl60JBUc1kHhQpWiC-Ks55UG4SdqjMyGlAGRYs5_U=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/pw/AP1GczNglOz799PYAStgq02zWk-vcu91vQoVM5LCtvFPTQE1p9faxsRKgXjfFda6FD6cf4BRqzwcSChKuq8tD0VPX63TWjBd0Fvx901o04tFmVIkM1rYtmA=w1920-h1080"></object>
</div> 
