---
layout: default
title: Unstructured Ideas
nav_order: 100
nav_exclude: true
search_exclude: true
---

# Random Ideas
{: .no_toc}

Unorganized seedlings of ideas, perhaps promising or stupid or both.
{: .fs-6 .fw-300 }

---

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---

## Self-Aware Dual Output Networks

The traditional scheme for apply a deep neural network to a supervised problem is to train a model entity (i.e. a collection of parameters organized by computational abstractions like 'nodes' or 'layers') to predict an output given an input.

![image](https://user-images.githubusercontent.com/73039742/153722949-0f155d20-c02f-4155-894c-4aec2a9e757f.png)

It is interesting to ponder the possibility of self-aware networks - not in the sense of being conscious or sentient, but rather in the more technical sense of being able to model oneself or to match one's internal state. One potential idea is to add an additional output (i.e. a dual output model) that attempts to predict the parameters of one of the model's layers in addition to a *task output* that performs the actual given task.

![image](https://user-images.githubusercontent.com/73039742/153723038-845e790f-c62d-4158-9f2c-3c0a29ba7a92.png)

In this particular case, the loss function would be a weighted combination of the task output performance and the self-aware output performance, like such (binary cross-entropy and cosine similarity are just given as examples of possible specialized loss functions):

$$\text{loss} = \alpha \cdot \text{BCE}\left(y_{\text{task pred}}, y_{\text{task true}}\right) + (1 - \alpha) \cdot\text{CosSim}\left(y_{\text{param pred}}, y_{\text{true params}}\right)$$

The specific value of $$\alpha$$ can be adjusted over time such that it is high initially and progressively decreases towards $$0.5$$ to give both eventual equal weighting.

If this were to be successful, it would raise interesting questions about the formulation of meta-parameters that parametrize the modeling of themselves, rather than an external phenomena. There are many variations on this type of 'meta-modeling' or 'self-awareness' experiment.

---

## Modeling Schools of Thought in a Dynamic, End-to-End Manner
In nontrivial, nonobjective, and difficult crowdsourced annotation tasks, annotators often give conflicting annotations $$y$$ on very similar or identical inputs $$x$$. This is often due to different criteria interpretation, background, belief system, and reasoning. This makes the task of building a model $$f$$ to learn the mapping $$f(x) \to y$$ from the dataset challenging.

Much literature exists on learning from differing/disagreeing annotations. The simplest approach is to average or otherwise aggregate the annotations before model training, then to train the model to predict the aggregated annotation (e.g. the mean annotator score). Another approach is to treat the distribution of annotations as a probability distribution to be modeled (rather than a single ‘objective’ output). More recent methods involve modeling each annotator’s output and learning the optimal aggregation of each annotator’s output (see figures from work by Guan and Rodrigues below). To paraphrase Guan 2018, “aggregating modeled annotators beats modeling the aggregated annotator”.

![image](https://user-images.githubusercontent.com/73039742/151713748-8e1b8037-1665-41fd-8a18-c19b2bb5346b.png)
*Guan 2018*

![image](https://user-images.githubusercontent.com/73039742/151713759-24225365-8f71-4d23-ad2d-25ded6076f61.png)
*Rodrigues 2018*

Most models and approaches designed for learning from disagreement include a component, explicit or implicit, that allows for the judging of annotator/worker reliability or trustworthiness. The labels of annotators/workers that score poorly on these dimensions are discounted internally by the model, whereas the labels of those that score well are inflated in determining the overall output of the model. The concepts of reliability and trustworthiness are inextricably linked to the existence of an ideal ground/gold truth. For instance, Guan et al. apply annotator-specific modeling to doctor diagnoses, in which there is a hypothetical true diagnosis.

In the context of the existence of an ideal ground/gold truth, decision-making is a zero-sum game (or, more appropriately in the context of probability, one-sum). In order to obtain a final ground truth estimation $$y$$, an increase in the importance or weightage of $$y_i$$ necessitates a decrease in the importance of weightage of $$y_j$$, where $$i$$ is an annotator output and $$j$$ is a collection/set of impacted annotator outputs. That is, different candidates compete with one another over influence on the final estimate of the ideal ground truth.

In some domains, however, the concepts of an ideal gold standard, reliability, trustworthiness, and zero/one-sum annotator logic cease to be helpful or significant. This is particularly the case for annotations reflecting opinions or beliefs in which there is not a clear truth. For instance, consider the problem of identifying toxic or offensive content. Different people have different standards, sensitivities, beliefs, and contexts for which comments, images, or other media are toxic or offensive and which are not. Some works (e.g. Sap 2019) identify differences in toxicity/offensiveness identification that can be dangerous if deployed universally. As such, it proposes techniques (i.e. author context, etc.) to homogenize/increase annotation consistency in order to reconcile what is argued to be harmful annotation disagreement. This still does not address the existence of disagreement on what is considered offensive. For instance, although the n-word has been reclaimed by many in the black community, there are many complex reasons why people of all races feel that its usage is offensive, not offensive, or somewhere in the middle. A model that models a phenomena as personal as this should model ‘multiple truths’ rather than attempting to force the modeling of one homogenizing universal truth. (If clients desire a certain truth/belief system/reasoning system to use in their applications, they ideally are able to extract the part of the model that corresponds to that desired truth.)

A ‘Multi-Response Model’ is a general modeling concept in which multiple different outputs are accepted, and the outputs are not in competition with each other (i.e. does not adhere to zero/one-sum decision-making logic). Consider the following hypothetical model design, which allows for multiple ‘answers’ or output heads derived from different extractions/interpretations but shared compilations and aggregations of extracted features.

![image](https://user-images.githubusercontent.com/73039742/151713803-a83ce2e8-4eec-46ff-8a09-bef2e69e3448.png)

The model is optimized on a loss function that only considers one or a subset of ‘relevant’ answers. For instance, the loss function may only take into account the output that is closest to the provided dataset label and adjust the weights of the associated branch. With this model design, the model can learn from an input sample $$x$$ with two differing annotations $$y_0$$ and $$y_1$$ without engaging in zero/one-sum penalization. The result is a model that can obtain multiple outputs that exist ‘organically’, having been derived from different interpretations/extractive processes but the same feature aggregation methods. Each output can be thought of as representing a ‘school of thought’ - a sophisticated aggregation of opinions that are capable of being represented well via one output. Each ‘school of thought’ is derived through a simple learning paradigm rather than a complex and manual clustering operation (like in Tian 2012). If desired, a client can extract segments of the model representing certain schools of thought that behave in certain ways desirable for their application.

This model is similar to Guan’s work, but we attempt to model the output of ‘schools of thought’ rather than individual annotators.

Moreover, the concept is generalizable to any domain; the extractive, processing, and output components simply need to be composed of layers that are capable of processing the modal form of the dataset. For instance:
- Modeling image-to-scalar/class problems using convolutional extractive branches, fully-connected processing branches, and a linear/softmax output for each output component.
- Modeling image-to-text problems using convolutional extractive branches, recurrent/attention-based processing branches, and a text-based output for each output component.
- Modeling Goldilocks data by predicting the high and low bounds for each output component.

The idea of model outputs existing noncompetitively with respect to each other may become more important as AI’s enforcement of subjective standards becomes more prevalent.

(One concern is how to determine the optimal number of schools of thought. It may be possible to impose a penalty/regularization to balance the number of outputs used by the network vs. performance such that the model expands an additional response field only if the benefit in modeling outweighs the penalty.)

---

## Discretized Distribution Modeling for Regression Confidence
Consider a scalar annotation problem in which annotators provide a scalar annotation across a range $$[a, b]$$:

![image](https://user-images.githubusercontent.com/73039742/151713843-fef5bdd2-68d8-4553-b7a1-2543b62998f9.png)

In [Chen et al.](https://arxiv.org/abs/2108.01799), the Goldilocks method allows annotators to provide a lower and upper bound:

![image](https://user-images.githubusercontent.com/73039742/151713863-d6e492cc-d76a-40e2-98af-343072c2f5d7.png)

We can represent this as a uniformd distribution from $$[a, b]$$.

![image](https://user-images.githubusercontent.com/73039742/151713896-35834561-f4e4-459e-87ed-b576c1a54d9f.png)

This distribution can be discretized into $$n$$ buckets.

![image](https://user-images.githubusercontent.com/73039742/151713932-4b017b72-6661-484d-b1f4-c67b1c9db389.png)

A neural network can be trained with $$n$$ output nodes; the output can be interpreted as a probability distribution.

![image](https://user-images.githubusercontent.com/73039742/151713944-38b1af66-2003-400f-8127-8bb115faffe2.png)

We have transformed a regression problem into a probability distribution modeling problem into a multiclass problem. The Neural Net can be fitted with a specialized head to process the input (e.g. convolutional for images, recurrent/transformer for sequence) and a FC output for distribution prediction. The network can be optimized either through a conventional classification loss function (i.e. multiclass categorical crossentropy), or through a distribution loss function like KL divergence.

This method can provide a better feedback for regression problems.



