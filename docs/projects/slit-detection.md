---
layout: default
title: Foot Process Width Segmentation in Podocytes
parent: Projects
nav_order: 1
has_children: false
---

# Foot Process Width Segmentation in Podocytes

Performed @ the Najafian Lab, UW Medicine
{: .fs-6 .fw-300 }

---

| For this project, I am working with David Smerkous under PI Bezhad Najafian. |

*More description forthcoming*.

**A novel approach to segment specialized annotations in electron microscopy images of podocyte cells.**
Podocyte cells reside in the glomerulus of the kidney and aid in urine filtration. Images of podocytes can be obtained through electron microscopy; certain cell features visually indicated on these images can be used to quantify the extent to which the podocyte filtering function has been impaired. Certain morphological features, such as foot process width, have been shown to correlate with disease progression. The current gold standard for measuring morphological features involves human measurements with traditional imaging software, which takes 6-8 hours per biopsy. Deep convolutional neural networks can be used to significantly decrease the time and labor required to obtain this quantification by identifying cell features in electron microscopy images, as has been demonstrated in many other bioimaging problems. However, when annotations are locality-specific and small, standard convolutional neural network approaches yield mediocre results. We present a novel approach for the segmentation of locality-specific annotations in cellular images and demonstrate its superior performance in identifying cell features on podocyte images. Firstly, we show that the problem of modeling small annotations consistently in proximity to a cross-image cell feature, like a membrane, can be simplified into a two-step modeling process: one model segments the cross-image cell feature, and dependent model segments on smaller windows along the predicted feature segmentation. Secondly, we show that dynamically dilating the size of small annotations from an inflated representation down to its original size over the duration of training improves model generalization. These findings allow for more robust modeling of locality-specific small cell segmentation tasks beyond podocyte cell feature identification. |
