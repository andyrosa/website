+++
title = "Visualizing the Confusion Matrix"
description = "Summary of terminologies in Confusion Matrix"
date = "2017-10-15T13:33:07-04:00"
thumbnail = "https://i.imgur.com/uipmEwt.png"
categories = [
  "machine learning",
  "blog"
]
tags = [
  "machine learning",
  "calculus",
]

[distill]
  [[distill.authors]]
  author = "Sanyam Kapoor"
  authorURL = "http://www.sanyamkapoor.com/"

    [[distill.authors.affiliations]]
    name = "Courant Institute, NYU"
    url = "https://cs.nyu.edu"
+++

*Confusion Matrix* is a matrix built for binary classification problems.
It is an important starting tool in understanding how well a binary
classifier is performing and provides a whole bunch of metrics to be
analysed and compared.

Here, I present an intuitive visualization given that most of the times
the definition gets confusing.

{{< figure class="figure" src="//i.imgur.com/uipmEwt.png" title="The Confusion Matrix" >}}

### How to read the visualization?

Before we go ahead and read the visualization, let us remember the definitions.

* *True Negatives* - All samples that were identified as negative labels and
were truly negative

* *False Negatives* - All samples that were identified as negative labels and
were in fact positive

* *True Positives* - All samples that were identified as positive labels and
were truly positive

* *False Positives* - All samples that were identified as positive labels and
were in fact negative

Now, each array in the visualization above specifies the name of the metric that
we are going to measure, and the start point of each ray represents the
numerator of that metric and the span of the ray represents the summation
of the adjacent terms. Note that each metric is essentially a fraction.

Let us read the most popular ones from the visualization.

\\[ \text{Recall} = \frac{TP}{TP+FN} \\]
\\[ \text{Precision} = \frac{TP}{TP+FP} \\]


### When are they useful?

These metrics come in handy when trying to determine the best threshold
to separate the positive classes from the negative classes in a binary
classification problem.

For instance, a popular trade-off is the *precision-recall trade-off* which
is realized in the graph below. Precision tends to be more wriggly by nature.

{{< figure class="figure" src="//i.imgur.com/bUqbFXU.png">}}

More simply we might just choose a *Precision v/s Recall Curve*. This curve
shows that we still have scope for improvement towards the right as it
suddenly shows a dip in precision with increase in recall.

{{< figure class="figure" src="//i.imgur.com/7TIpZUb.png">}}

Or another popular curve called the ROC-Curve which maps between the
*True Positive Rate* and *False Positive Rate*. It can also be seen
as the *Sensitivity v/s 1-Specificity*. The closer this curve is
to the left-top corner, the better the classifier. Or alternatively,
the closer the curve is to the center line, the more likely it is to be
just as good as a random classifier.

{{< figure class="figure" src="//i.imgur.com/vtdW5sh.png">}}

The scope of what is useful when is more sample dependent but these
curves should be a good starting point in the analysis of the first
binary classifier that one builds.
