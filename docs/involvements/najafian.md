---
layout: default
title: Najafian Lab
parent: Involvements
nav_order: 11
has_children: false
---

# Najafian Lab

Pathobiology of Kidney Diseases, UW Medicine
{: .fs-6 .fw-300 }

PI: Bezhad Najafian 
{: .label .label-blue}

Project Supervisor: David Smerkous 
{: .label .label-green}

Active: March 2020 - June 2022
{: .label .label-purple}

---

[Najafian Lab research](https://dlmp.uw.edu/research-labs/najafian){:target="_blank"} strives to better understand pathobiology of kidney diseases. Podocytes are terminally differentiated cells with limited regenerative capacity. These cells play crucial role in preservation of structure and function of glomeruli (blood filters in the kidney). Injury and loss of these cells is directly or indirectly involved in development or progression of majority of chronic kidney diseases. We study podocyte injury in various kidney diseases, but largely in diabetic nephropathy and Fabry nephropathy.

At the Najafian Lab, I work on designing deep learning computer vision models on the Foot Process Width project. Read more about the project [here](./projects/slit-detection). We've proposed and validated new approaches for segmetnation problems, including:
- *Membrane windowing*. If certain local cell features (e.g. foot process slits) are reliably clustered near a cross-cell featur (e.g. a membrane), then we can reduce the problem space by obtaining small windows (i.e. subregions) along the segmentation of cross-cell feature, segmenting the individual subregions for the local cell features, then aggregating the subregion segmentations back into a complete segmentation. Not only does this remove irrelevant context, it also amplifies the relative size and importance of the segmentation outputs, which would have been insignificant in a complete target segmentation map.
- *Dynamic dilation*. Rather than directly training an image-to-image network on small segmentation annotations, we can inflate the size of the annotations using dilation and slowly deflate it back to the original representation size. This allows the network to grasp the major regions in which a small annotation should be segmented, then develop precision later.
- *Dynamic augmentation*. The severity of augmentation can be dynamically increased over time in response to model performance.

David and I presented this work at the 25th Undergraduate Research Symposium. You can find slides [here](https://andre-ye.github.io/files/najafian/URP%20Presentation.pdf){:target="_blank"}.

