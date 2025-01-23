---
tags:
  - STAT542
---
---
In week 15, I usually present a brief introduction to topics of personal interest, with no quizzes or assignments tied to the content.

**Notes**
\[[lec_W14.1_IntroDeepLearning](https://liangfgithub.github.io/Notes/lec_W14.1_IntroDeepLearning.pdf)\]
\[[lec_W14.2_VAE](https://liangfgithub.github.io/Notes/lec_W14.2_VAE.pdf)\]

**Additional Reading for Diffusion Models**
- HuggingFace Diffusion Model Course [[Github](https://github.com/huggingface/diffusion-models-class)] [[Youtube](https://www.youtube.com/watch?v=09o5cv6u76c)]
- Calvin Luo. Understanding Diffusion Models: A Unified Perspective. [[Webpage](https://calvinyluo.com/2022/08/26/diffusion-tutorial.html)] [[PDF](https://arxiv.org/pdf/2208.11970.pdf)]
- Yang Song. Generative Modeling by Estimating Gradients of the Data Distribution [[Webpage](https://yang-song.net/blog/2021/score/)]
- Lilian Weng. What are Diffusion Models? [[Link](https://lilianweng.github.io/posts/2021-07-11-diffusion-models/)]

**Videos**
This year's videos: TBA

Old videos: 
\[[NN_Part_1](https://mediaspace.illinois.edu/media/t/1_fi1kg73s)\] \[[NN_Part_2](https://mediaspace.illinois.edu/media/t/1_92mvl0xp)\]
\[[F18_NN_Rcode_1](https://mediaspace.illinois.edu/media/t/1_vjvq77sp)\] \[[F18_NN_Rcode_2](https://mediaspace.illinois.edu/media/t/1_2b4bbd4t)\]
\[[F20_NN_Rcode_CNN](https://mediaspace.illinois.edu/media/t/1_mbif0pa9)\]
\[[F20_NN_Rcode_VAE](https://mediaspace.illinois.edu/media/t/1_huzkiomd)\]

**Code**
Python: [[FashionMnist](https://liangfgithub.github.io/Python_W14_NN_FashionMnist.html)] [[MovieReview](https://liangfgithub.github.io/Python_W14_NN_MovieReview.html)] [[RNN_LSTM](https://liangfgithub.github.io/Python_W14_NN_RNN_LSTM.html)] [[VAE](https://liangfgithub.github.io/Python_W14_NN_VAE.html)]

R: [[FashionMnist](https://liangfgithub.github.io/Rcode_W14_NN_FashionMnist.html)]
[[CNN](https://liangfgithub.github.io/Rcode_W14_NN_CNN.html)] [[MovieReview](https://liangfgithub.github.io/Rcode_W14_NN_MovieReview.html)]
[[RNN_LSTM](https://liangfgithub.github.io/Rcode_W14_NN_RNN_LSTM.html)] [[VAE](https://liangfgithub.github.io/Rcode_W14_NN_VAE.html)]

**Resources**
- Stanford CS231 \[[website](https://cs231n.github.io/)\] (you can find recorded videos on youtube)
- A birds-eye view of optimization algorithms \[[Link](http://fa.bianp.net/teaching/2018/COMP-652/)\]
- Stanford CS236 [[Youtube](https://www.youtube.com/watch?v=XZ0PMRWXBEU&list=PLoROMvodv4rPOWA-omMM6STXaWW4FvJT8)]
- Probabilistic PCA. [[Bishop_Book_Chap12](https://liangfgithub.github.io/Bishop-Chap12.pdf)]


## W15: VAE
---
**Youtube** [[Link](https://www.youtube.com/watch?v=XOLaTANrJEY)]

**Slides** [[Link](https://liangfgithub.github.io/Notes/lec_W14.2_VAE.pdf)] (You can ignore the 1st page at this moment)

-----
#### Introduction

Deep neural networks are widely known for their role in supervised learning. However, they are equally powerful in unsupervised learning, enabling tasks like dimensionality reduction and generative modeling. Today, we’ll explore how deep neural networks can be leveraged for dimensionality reduction using the **Variational Autoencoder (VAE)**.

---
#### Autoencoders: A Brief Overview

An autoencoder is essentially a tool for dimensionality reduction or data compression. Here’s the basic flow:

1. **Input**: Start with a $$p$$-dimensional input vector $$\mathbf{x}$$.
2. **Encoding**: Compress $$\mathbf{x}$$ into a $$k$$-dimensional vector $$\mathbf{z}$$, where $$k < p$$. This step is called encoding.
3. **Decoding**: Reconstruct the original $$\mathbf{x}$$ from $$\mathbf{z}$$. This step is called decoding.

Autoencoders aim to minimize reconstruction error, typically using a loss function tailored to the data type: mean squared error (MSE) for numerical $$\mathbf{x}$$ and binary cross-entropy for binary  $$\mathbf{x}$$.

If we restrict both the encoder and decoder to linear functions and use MSE loss, the process is analogous to **Principal Component Analysis (PCA)**.

With nonlinear transformations, autoencoders can capture more complex data structures.

---
#### From PCA to Probabilistic PCA
To transition to VAEs, let’s briefly discuss Probabilistic PCA:

1. Assume a generative model for the data:
   - a $$k$$-dimensional latent vector $$\mathbf{z}$$ is drawn from a standard Gaussian distribution $$\mathcal(0, \mathbf{I}_k)$$, where $$\mathbf{I}_k$$ denotes the $$k$$-by-$$k$$ identity matrix.
   - The observed data $$\mathbf{x}$$ is generated as:
$$ \mathbf{x}_{d \times 1} = W_{d \times k} \mathbf{z}_{k \times 1}+ \mathcal{N}(0, \sigma^2 \mathbf{I}_d) $$
   
     where $$W$$ maps the latent space to the observed space. Here we assume that we have centered the data so no mean parameter is needed. 

2. Parameters $$(W, \sigma^2)$$ can be estimated using Maximum Likelihood Estimation (MLE) or the EM algorithm.

**Why EM**
Although MLE provides direct solutions, EM can be computationally efficient by reducing the dimensionality of matrices involved in computations. Check the discussion in Chap 12.2.2 of Bishop [[PDF](https://liangfgithub.github.io/Bishop-Chap12.pdf)]. 

---

#### Variational Autoencoders (VAEs)

Recall the EM algorithm is essentially an iterative maximization algorithm with the following objective function, also known as **ELBO** (Evidence Lower Bound): 

$$
J(\theta, Q) = \mathbb{E}_Q \log \frac{\prod_i p(\mathbf{x}_i | \mathbf{z}_i, \theta) \prod_i \pi(\mathbf{z}_i)}{\prod_i q_i(\mathbf{z}_i)}
$$

Given $$\theta$$ value, the optimal $$q_i$$ is the posterior $$p(\mathbf{z}_i | \mathbf{x}_i, \theta)$$, which corresponds to the E-step in the EM algorithm. 

VAEs extend Probabilistic PCA by introducing:

1. **Variational Inference**: As mentioned earlier, the optimal choice for $$q_i(\mathbf{z}_i)$$  is the posterior $$p(\mathbf{z}_i | \mathbf{x}_i, \theta)$$ given data $$\mathbf{x}_i$$ and the current parameter value $$\theta$$. However, for computational tractability, we approximate $$q_i(\mathbf{z}_i)$$ using a parametric family $$q(\mathbf{z}_i | \phi_i)$$. Here we use Gaussian, so $$\phi_i$$ denotes the mean and (log of) variance.
2. **Amortized Inference**: Instead of computing $$\phi_i$$ individually for each sample, we'll model $$\phi_i$$ as a function of the data $$\mathbf{x}_i$$, i.e., $$q(\mathbf{z}_i | \phi (\mathbf{x}_i))$$
3. **Deep Neural Networks (DNNs)**: Learn both $$\theta$$ and $$\phi$$ mappings using deep neural networks. 

---

#### Key Components of a VAE

1. **Encoder**: map $$\mathbf{x}$$ to $$\phi(\mathbf{x})$$, the parameters of the distribution over $$\mathbf{z}$$ (blue component)
2. **Decoder**: Reconstruct $$\mathbf{x}$$ from latent $$\mathbf{z}$$ (purple component)
3. **Loss function**: see below. 

![Screen%20Shot%202024-12-08%20at%2011.33.46%20PM.png](https://files.campuswire.com/b46e5679-e794-4c26-bbfe-e20c683cd5d8/061789ab-e691-4876-9f32-de47997cdfe4/Screen%20Shot%202024-12-08%20at%2011.33.46%20PM.png)


The loss function can be written as follows: 

$$
J(\theta, Q) = \mathbb{E}_Q \log \prod_i p(\mathbf{x}_i | \mathbf{z}_i, \theta)  + \sum_i \mathbf{E}_{q_i} \log \frac{ \pi(\mathbf{z}_i)}{q_i(\mathbf{z}_i | \phi(\mathbf{x}_i))}
$$

1. **Second Term (KL Divergence)**: This term involves the Gaussian expectation of a ratio of two Gaussian distributions, which can be solved analytically. Gradients can be computed directly without difficulty.

2. **First Term (Reconstruction Loss)**: This term measures the difference between x (input) and x' (reconstruction). For numerical data, this is often the mean squared error (MSE). For binary data, such as MNIST images where pixel values are either 0 or 1, the output x' lies between 0 and 1, and binary cross-entropy can be used.


----

#### Reparameterization Trick

For the first term, the expectation is taken over the latent variable z sampled from the approximate posterior q.  However, $$q(z | \phi(x))$$  depends on learnable parameters (i.e., weights of encoder network). This dependency complicates direct gradient computation because the parameters are embedded within the distribution.

This is where the reparameterization trick comes into play. In essence, we rewrite the expectation over $$q(\mathbf{z}_i | \phi(\mathbf{x}_i))$$ as an expectation over standard normal distributions, incorporating the learnable parameters associated with $$\phi$$ into the function being optimized. During stochastic gradient descent, we can randomly sample from a standard normal distribution, carry out the gradient calculation inside the expectation, enabling efficient backpropagation and training of VAEs.

## W15: Generating Samples
---
First Slide in [[Link](https://liangfgithub.github.io/Notes/lec_W14.2_VAE.pdf)]

---
#### Introduction
In this class, we've primarily focused on **supervised learning**, dedicating only about two weeks to unsupervised learning, such as clustering and latent class models. 

However, with the rise of generative AI and its applications—creating data, text, or images based on input prompts—we’re returning to unsupervised methods. These generative models aim to simulate or produce data based on learned distributions.

To understand this better, let’s revisit how we typically generate random variables.

---

#### Generating Discrete Random Variables

First, how to generate samples from uniform [0, 1]?

Computer first generates uniform random variables over a range of integers, 1, 2, ...., N, and then scale them (e.g., divide them by (N+1)) to approximate a uniform [0,1] distribution.

In practice, software uses **pseudo-random number generators** —deterministic algorithms that produce sequences resembling random data. By setting a **seed**, these sequences become reproducible, which is why you’ve seen us specify seeds in assignments.

With uniform samples, we can generate discrete random variables. For example, to generate a variable 
X with probabilities:

- $$P(X=1)=0.5,$$
- $$P(X=2)=0.2,$$
- $$P(X=3)=0.3,$$

we partition [0,1] into intervals:
- [0,0.5)→X=1,
- [0.5,0.7)→X=2,
- [0.7,1]→X=3.

A uniform sample can then determine the corresponding interval and value of X. 

---

#### Generating Continuous Distributions (CDF Method)

For continuous random variables, we can use the CDF method:

- Let X have a distribution with CDF  F(x).
- Generate a uniform random variable U∼Uniform(0,1).
- Find $$X = F^{-1}(U)$$

This method transforms uniform samples into samples from the desired distribution by inverting the CDF. 

For example, to generate exponential random variables, use the CDF $$F(x) = 1 - e^{-\lambda x}$$ and invert it.

---
#### Generating Normal Random Variables

To generate samples from a normal distribution, it suffices to focus on generating samples from N(0, 1). A common method is the  **Box-Muller** algorithm. Interestingly, this algorithm relates to a fundamental question: how can we show the pdf of N(0,1) integrates to one? 

For a single normal PDF, this verification isn't straightforward. However, the problem becomes easier if you consider two independent N(0,1) distributions and demonstrate that the product of their PDFs integrates to one:

$$
\Big ( \int_{-\infty}^{\infty} \frac{1}{\sqrt{2 \pi}} e^{-x^2/2} \Big ) \cdot \Big ( \int_{-\infty}^{\infty} \frac{1}{\sqrt{2 \pi}} e^{-z^2/2} \Big ) = 1
$$

The left-hand side can be written as a double integral 
$$
\int_{-\infty}^{\infty} \int_{-\infty}^{\infty} \frac{1}{2 \pi} e^{-(x^2+z^2)/2} d x d z.
$$

Then you can switch to polar coordinates. 

---

#### Latent Variable Models

In Week 7, we introduced latent variable models, such as Gaussian Mixture Models (GMMs). These models decompose complex distributions into simpler components:

For example, a GMM assumes that: $$f(x) = \sum_k P(Z=k) f(x | \theta_k)$$. Then we can first sample a latent variable $$Z$$, and condition on $$Z=k$$ to sample $$x$$ based on a Gaussian distribution with parameter $$\theta_k$$.

This approach simplifies generating samples from intricate distributions by breaking them into manageable steps.

---

#### Generate Samples using VAEs

The VAE model can serve not only as a dimensionality reduction method through its encoding component but also as a generative model. Once the model is trained, the decoder can be utilized independently to generate new samples. Specifically, you can sample Z from a standard normal distribution and pass it through the decoder to produce a new sample  X. 


----

#### Advanced Generative Models
However, while VAEs are effective at generating samples in a single step, the outputs often lack the realism seen in other generative methods. This is where **Generative Adversarial Networks (GANs)** come into play. Although we didn't cover GANs, students can explore some online resources.

Alternatively, **diffusion models** offer another exciting approach. Think of them as the “cool cousin” of VAEs, operating in a more sequential manner. Unlike VAEs, diffusion models doesn't bother with learning the encoder, leaving it fixed, and instead focuses solely on the decoder. The encoder (aka, forward process) gradually injects noise into an image, making it appear more like random noise. The decoder  (aka, the backward process) gradually tweaks a random image to make it look more real over multiple steps. 

## W15: Diffusion Models
---

---
#### Recap: Variational Autoencoders (VAEs)

Let’s revisit the VAE model we discussed earlier in #1110 

![Screen%20Shot%202024-12-08%20at%2011.33.46%20PM.png](https://files.campuswire.com/b46e5679-e794-4c26-bbfe-e20c683cd5d8/061789ab-e691-4876-9f32-de47997cdfe4/Screen%20Shot%202024-12-08%20at%2011.33.46%20PM.png)


The key objective of VAEs is $$J(\theta, \phi)$$, the  Evidence Lower Bound (ELBO). Within the ELBO: 

- The numerator, p(x∣z), acts as the decoder, which generates the output x given a latent embedding x. 
- The denominator, q(z|x), serves as the encoder, generating the embedding from the input x. 

As mentioned earlier, if our sole interest lies in learning a decoder as a data-generating mechanism, there’s no need to train an encoder. 

This principle underpins the concept of diffusion models. Unlike VAEs, diffusion models do not learn the encoder. Instead, they keep the encoder, q(z|x), fixed and concentrate solely on the decoder.

---
#### Diffusion Models: An Overview

The diffusion model process can be illustrated as below (image from [[Link](https://calvinyluo.com/2022/08/26/diffusion-tutorial.html)]):

![Screenshot%202024-12-10%20at%202.11.14%E2%80%AFPM.png](https://files.campuswire.com/b46e5679-e794-4c26-bbfe-e20c683cd5d8/a3aa8d1f-c823-4501-808a-8221938b9cc7/Screenshot%202024-12-10%20at%202.11.14%E2%80%AFPM.png)

- The **encoder** (aka, the **forward process**), shown as the **bottom flow** (from time t=0 to t=T), gradually injects noise into an image while simultaneously scaling down its signal, progressively transforming it to resemble random noise.

- The **decoder** (aka, the **backward process**), shown as the **upper flow** (from time t=T to t=0), iteratively removes the noise, gradually refining the random image until it looks realistic.

This iterative approach makes diffusion models akin to multi-layered or hierarchical VAEs, enabling them to generate highly realistic outputs.

---
#### The ELBO

A detailed derivation of the ELBO for diffusion models can be found in this tutorial [[Link](https://calvinyluo.com/2022/08/26/diffusion-tutorial.html)]. A crucial term to focus on is the third term in Equation 38, where:

![Screen%20Shot%202024-12-10%20at%2011.33.44%20AM.png](https://files.campuswire.com/b46e5679-e794-4c26-bbfe-e20c683cd5d8/4a382386-49c3-4cd6-b52c-6c24e37baec4/Screen%20Shot%202024-12-10%20at%2011.33.44%20AM.png)

The backward process (P) has this backward decomposition:
$$
p(x_{0:T}) = p(x_T) p(x_{T-1} | x_T) \cdots p(x_1 | x_2) p(x_0 | x_1)
$$

The forward process (Q) has a natural forward expression 
$$
q(x_{1:T} | x_0) = q(x_1 | x_0) q(x_2 | x_1) \cdots q(x_T | x_{T-1}).   (*)
$$

But to match the backward process (P), we rewrite the forward process Q as follows:
$$
q(x_{1:T} | x_0) = q(x_T | x_0) q(x_{T-1} | x_T, x_0) \cdots q(x_1 | x_2, x_0).   (**)
$$

Since each distribution in (*) is Gaussian, we can show that each distribution in (**) also Gaussian and deriving the parameters is straightforward.

----
#### What Are We Learning?

This leads to a key question: **If we already know the forward process (Q), what exactly are we learning?**

The answer lies in the backward process (P):

- The **numerator** $$q(x_{t-1} | x_t, x_0)$$ is well-defined as a Gaussian distribution based on the original image $$x_0$$.
- The **denominator**, $$p_{\theta}(x_{t-1} | x_t) $$, is what we aim to learn. It represents the denoising process, conditioned only on the noisy image $$x_t$$ without access to the true image $$x_0$$.

Once  the backward process (P) is learned, we can sample a noise image and effectively reverse the process to generate realistic images.

---
#### Three Equivalent Interpretations

If we assume $$p_{\theta}(x_{t-1} | x_t) $$ is Gaussian, similar to $$q(x_{t-1} | x_t, x_0)$$, then learning the reverse process can be formulated as a regression problem  with a weighted mean-squared error (MSE) loss function.

You might encounter different explanations for learning the reverse process:
- **denoising model**: Learning to remove noise from $$x_t$$
- **noise prediction model**: learning to estimate noise injected in the forward process at time t
- **score model**: estimate the **score function** for $$x_t$$.

These interpretations are mathematically equivalent. For more details,  see the section "Three Equivalent Interpretations" in Calviny Luo's tutorial [[Link](https://calvinyluo.com/2022/08/26/diffusion-tutorial.html)]. The original comments might be from the Variational Diffusion Model paper [[Link](chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://arxiv.org/pdf/2107.00630)], Appendix A, page 14.

----
#### Resources for Implementation

 And for implementation, I recommend checking out the HuggingFace Diffusion Model Course [[Github](https://github.com/huggingface/diffusion-models-class)] [[Youtube](https://www.youtube.com/watch?v=09o5cv6u76c)].

----
#### Why Learn the Score Function?

The primary advantage of learning the score function, instead of estimating the original probability density, is that it eliminates the need to compute the normalizing constant. For further understanding, check the section on score based model in Calvin Luo's tutorial [[Link](https://calvinyluo.com/2022/08/26/diffusion-tutorial.html)] and Song Yang's blog [[Link](https://yang-song.net/blog/2021/score/)].

The ultimate goal of generative models is to produce samples, not just estimate parameters. Once we have the score functions, how do we generate these samples? The answer lies in **Langevin** dynamics, a technique that iteratively refines samples using the score function.

If you’re interested in diving deeper, I encourage you to explore readings on Langevin sampling and other related work on score-based generative models.