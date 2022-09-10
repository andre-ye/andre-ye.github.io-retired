---
layout: default
title: Informative Segmentation Modeling and Crowdsourcing
parent: Projects
nav_order: 2
has_children: false
---

# Informative Segmentation Modeling and Crowdsourcing

Performed @ the Social Futures Lab, Allen School
{: .fs-6 .fw-300 }

---

| For this project, I am working with Ph.D. student Jim (Quanze) Chen and PI Amy Zhang. |

Semantic segmentation tasks are an important part of computer vision, with key applications in robotics, scene interpretation, surveillance, and biology. These tasks often require human annotators to create segmentation maps identifying regions, boundaries, or bounding boxes corresponding to the original image. However, like many annotation problems, there are often nontrivial uncertainties associated with annotation that cannot be captured through vanilla annotation mediums, practices, policies, and interfaces.

We can separate uncertainty in semantic segmentation tasks into two categories: uncertainty of existence and uncertainty of precision.
- Uncertainty of existence: the annotator is unsure if a region, boundary, or bounding box should exist or not.
- Uncertainty of precision: the annotator knows that a region, boundary, or bounding box exists, but is unsure precisely where.

To address these sources of uncertainty, we can look towards the *Goldilocks method*, proposed by Quanze (Jim) Chen. The Goldilocks method offers a framework to deal with uncertainty and ambiguity in crowdsourced scalar annotations. The Goldilocks method has several key features:
- Global grounding and local comparison. When the annotator is making an annotation, they are both given information about the broad landscape (for efficient and accurate general localization) and about the locality surrounding a point (for higher precision).
- Encouraging annotation self-consistency by incorporating anchors, forming ‘soft rubrics’.
- Addressing uncertainty & establishing consistent label meaning by allowing annotators to select multiple fitting labels (for instance, via a two-step range).

In this project, I attempt to 'translate' these principles to a segmentation domain, in which the target annotation is a spatial segmentation map.

- [Goldilocks for Images](https://andre-ye.github.io/files/sfl/Goldilocks for Images.pdf){:target="_blank"}. Given as an introduction during a lab meeting to the idea of uncertainty representation and theorizing visual uncertainty.
- [Medical Uncertainty Annotation](https://andre-ye.github.io/files/sfl/Medical Uncertainty Annotation.pdf){:target="_blank"}. Given as an update during a lab meeting to the chosen domain and demoing the application.



