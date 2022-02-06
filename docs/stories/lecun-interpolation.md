---
layout: default
title: Yann LeCun, Twitter Wars, and Interpolation
parent: Projects
nav_order: 1
has_children: false
---

# Yann LeCun, Twitter Wars, and Interpolation

A story of deep learning theory debate and defeat
{: .fs-6 .fw-300 }

---

In June of 2020, I wrote a piece entitled ["You Don't Understand Neural Networks Until You Understand the Universal Approximation Theorem"](https://medium.com/analytics-vidhya/you-dont-understand-neural-networks-until-you-understand-the-universal-approximation-theorem-85b3e7677126?sk=62937adc3de501a7ec005262ac621cfd){:target="_blank"}. Its thesis was that by the Universal Approximation Theorem (UAT), we can understand the appearance of intelligent behavior in certain problems exhibited by neural networks (e.g. image recognition, image captioning, text recognition) as a product of sufficiently large neural network's ability to more or less arbitrarily fit any function. Although it's not the best choice of words, we can think of neural networks as extremely advanced curve-fitters operating in very high-dimensional spaces.

The key distinction made in the article was between the concepts of interpolation and extrapolation. While interpolation demonstrated at a very high-dimensional level seems impressive, the article argues, extrapolation is at the root of a human conception of intelligence.

> "From the Universal Approximation Theorem, we understand that neural networks may not be 'intelligent' in the sense that humans often think of intelligence, but are complex estimators hidden under a guise of multidimensionality, which makes its ability - which would seem ordinary in two or three dimensions - seem impressive." - from the article

I used the following definitions of interpolation and extrapolation:

> Interpolation refers to the ability of a model to perform generalization within the domain it was exposed to. For instance, a linear regression model fitted on points within the domain `[0, 10]` would be said to possess the skill of interpolation if it can yield reasonably accurate predictions for inputs sampled within the domain `[0, 10]`.
> Extrapolation on the other hand, refers to the ability of a model to generalize outside the domain it was exposed to. Our hypothetical linear regression model, to demonstrate extrapolation, would need to be able to yield reasonably accurate predictions for inputs sampled in, say, the domain `(10, 20]` or `[-10, 0)`.

[Steven Pinker](https://twitter.com/sapinker){:target="_blank"} - a cognitive scientist at Harvard - tweeted in support of the article, writing that the interpolation/extrapolation paradigm distinction is a key limiting factor to the current state of neural network development.

<blockquote class="twitter-tweet" data-theme="dark"><p lang="en" dir="ltr">Excellent explanation of why neural networks work (when they do) &amp; why they often don&#39;t. (Common knowledge w/in cog sci but seldom stated so clearly.) You Don’t Understand Neural Networks til You Understand the Universal Approximation Theorem by Andre Ye <a href="https://t.co/F7PTtpD8Rk">https://t.co/F7PTtpD8Rk</a></p>&mdash; Steven Pinker (@sapinker) <a href="https://twitter.com/sapinker/status/1409869656610033681?ref_src=twsrc%5Etfw">June 29, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Soon afterwards, [Yann LeCun](https://twitter.com/ylecun){:target="_blank"} - the god king of deep learning and Turing Award laureate - tweeted in disagreement, asserting that the sparsity of high-dimensional spaces makes the concept of interpolation itself irrelevant in that domain. As the dimensionality of a space increases, the distance between any pair of points grows so rapidly that the only applicable concept to neural networks' operation within such spaces is that of extrapolation.

<blockquote class="twitter-tweet" data-theme="dark"><p lang="en" dir="ltr">This is another piece that basically says &quot;deep learning is not as impressive as you think because it&#39;s mere interpolation resulting from glorified curve fitting&quot;.<br>But in high dimension, there is no such thing as interpolation. <br>In high dimension, everything is extrapolation. <a href="https://t.co/5DSB4RikqE">https://t.co/5DSB4RikqE</a></p>&mdash; Yann LeCun (@ylecun) <a href="https://twitter.com/ylecun/status/1409940043951742981?ref_src=twsrc%5Etfw">June 29, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Others, like [Joscha Bach](https://twitter.com/Plinz){:target="_blank"} — cognitive scientist — seconded LeCun’s argument via retweet.

In response, [Gary Marcus](https://twitter.com/GaryMarcus){:target="_blank"} — founder of Geometric Intelligence and Robust.AI as well as a professor of of psychology and neural science at NYU — asserted that the dimensionality of the spaces modern neural networks operate within does not point towards the ability of neural networks to perform some sort of extrapolation. Marcus points to the erratic behavior of systems like GPT-3 as evidence that networks struggle to solve problems requiring test items far from the space of the training dataset with interpolation.

<blockquote class="twitter-tweet" data-theme="dark"><p lang="en" dir="ltr">No, <a href="https://twitter.com/ylecun?ref_src=twsrc%5Etfw">@ylecun</a>, high dimensionality doesn’t erase the critical distinction between interpolation &amp; extrapolation. <br><br>Thread on this below, because only way forward for ML is to confront it directly. <br><br>To deny it would invite yet another decade of AI we can&#39;t trust. (1/9) <a href="https://t.co/KRtGoYW1rD">https://t.co/KRtGoYW1rD</a></p>&mdash; Gary Marcus (@GaryMarcus) <a href="https://twitter.com/GaryMarcus/status/1411401507610796032?ref_src=twsrc%5Etfw">July 3, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

[Grady Booch](https://twitter.com/Grady_Booch){:target="_blank"}, codeveloper of the Unified Modeling Language (UML), seconded Marcus:

<blockquote class="twitter-tweet" data-theme="dark"><p lang="en" dir="ltr">I stand with Gary on this. Yet again. And no, <a href="https://twitter.com/ylecun?ref_src=twsrc%5Etfw">@ylecun</a> it is not because I have some particular anti-neural bias.</p>&mdash; Grady Booch (@Grady_Booch) <a href="https://twitter.com/Grady_Booch/status/1411402260014190594?ref_src=twsrc%5Etfw">July 3, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

I initially dismissed this interesting burst of activity as merely the result of ambiguity in the field resulting in speculative disagreements. Twitter really isn't the best platform to exchange nuanced perspectives - a lot of the Twitter thread content seemed pretty speculative or pulled willy-nilly without much organization. However, someone forwarded a recently published paper by Randall Balestriero, Jerome Pesenti, and Yann LeCun entitled "Learning in High Dimension Always Amounts to Extrapolation" - which experimentally and mathematically demonstrated that the probability of a validation-set item falling within the convex hull of the training set was near 0 for standard high dimensions.

<iframe src="https://arxiv.org/pdf/2110.09485.pdf" width="100%" height="300" style="border:1px solid black;"></iframe>

LeCun and Balestriero further talked about their work in an episode of the popular Machine Learning Street Talk series. I actually get a (not too flattering) shoutout by one of the co-hosts, who brings up my article at `2:08:15`:

<iframe width="100%" height="300"
src="https://youtu.be/86ib0sfdFtw?t=7695">
</iframe>

tl;dr: The paper and discussion has changed my mind. The thesis of Balestriero et al's work is not to necessarily argue that neural networks extrapolate, but rather that the demarcation between interpolation and extrapolation is not particularly useful in high dimensions.
