---
layout: post
title: "Non-linear activation"
urlimg: https://media.giphy.com/media/10nUdjHP9usQJG/giphy.gif
tags:

    - python

    - notebook
--- 
Introducing non-linearities into neural networks.



## A story of approximation

The reason behind the use of non-linearities is the [Universal approximation theorem](http://mcneela.github.io/machine_learning/2017/03/21/Universal-Approximation-Theorem.html)



Linear algebra would only allow approximation of linear function

Introducing non-linearities puts us in the right setup so that: with non-linearities, given an approximation error, there is a neural network of a given architecture composed of both linear and non-linear operations that will meet this error threshold.



Global optimum = set of parameters value

To achieve global optimum, **gradient-based approaches require those operations to be differentiable.**

4 aspects to keep in mind for non-linearities:

- need to be differentiable to allow gradient-based optimization
- avoid vanishing gradients (saturation for instance) to prevent slower convergence
- avoid dead neurons (wasted parameter)
- preserve normalization for easier optimization. However, parameter normalization can tackle this issue



avoid saturation = avoid vanishing gradient

zero-centered: gradient not restricted to certain sign

flat zero domain = dead neurons

computation



problems: vanishing gradients, exploding gradients







**In [1]:**

{% highlight python %}
%reload_ext autoreload
%autoreload 2
%matplotlib inline
{% endhighlight %}

**In [2]:**

{% highlight python %}
import torch
import torch.nn as nn
import torch.nn.functional as F

import matplotlib.pyplot as plt

plt.rcParams['figure.figsize'] = [10, 5]
{% endhighlight %}

**In [3]:**

{% highlight python %}
def swish(x, beta=1):
    return x * torch.sigmoid(beta * x)

def mish(x):
    return x * torch.tanh(F.softplus(x))
{% endhighlight %}

## Normalized input 
Can write everywhere

**In [4]:**

{% highlight python %}
def investigate_act(fn, val_range, step=0.1, nb_samples=10000, title=None):
    fig, (ax1, ax2, ax3) = plt.subplots(1, 3)
    x_range = torch.arange(*val_range, step, requires_grad=True)
    x = torch.randn(nb_samples)
    ax1.hist(x, 100)
    ax1.title.set_text(f'Input distribution\n(samples: {nb_samples})')
    ax1.set_xlabel(f'mean: {x.mean():.5}\nstd: {x.std():.5}')

    _y = fn(x_range)
    ax2.plot(x_range.detach().numpy(), _y.detach().numpy())
    # Get derivative
    _y.sum().backward()
    ax2.plot(x_range.detach().numpy(), x_range.grad.detach().numpy())
    ax2.title.set_text('Activation')
    ax2.legend(['Value', 'Derivative'])
    
    y = fn(x)
    ax3.hist(y, 100)
    ax3.title.set_text(f'Output distribution\n(samples: {nb_samples})')
    ax3.set_xlabel(f'mean: {y.mean():.5}\nstd: {y.std():.5}')
    
    if isinstance(title, str):
        fig.suptitle(title, fontsize='xx-large', weight='bold')
{% endhighlight %}

**In [5]:**

{% highlight python %}
plt.rcParams['figure.figsize'] = [15, 5]
{% endhighlight %}

**In [6]:**

{% highlight python %}
act_fns = [('Sigmoid', torch.sigmoid), ('Tanh', torch.tanh), ('Hard tanh', F.hardtanh),
           ('ReLU', F.relu), ('Leaky ReLU', F.leaky_relu), ('eLU', F.elu), ('SeLU', F.selu),
           ('CeLU', F.celu), ('Softplus', F.softplus), ('Swish', swish), ('Mish', mish)]

for n, fn in act_fns:
    investigate_act(fn, (-5, 5), title=n)
    plt.show()
{% endhighlight %}


![png](/assets/images/2020-01-04-activations/activations_7_0.png) 



![png](/assets/images/2020-01-04-activations/activations_7_1.png) 



![png](/assets/images/2020-01-04-activations/activations_7_2.png) 



![png](/assets/images/2020-01-04-activations/activations_7_3.png) 



![png](/assets/images/2020-01-04-activations/activations_7_4.png) 



![png](/assets/images/2020-01-04-activations/activations_7_5.png) 



![png](/assets/images/2020-01-04-activations/activations_7_6.png) 



![png](/assets/images/2020-01-04-activations/activations_7_7.png) 



![png](/assets/images/2020-01-04-activations/activations_7_8.png) 



![png](/assets/images/2020-01-04-activations/activations_7_9.png) 



![png](/assets/images/2020-01-04-activations/activations_7_10.png) 