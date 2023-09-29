# SepFormer Architecture


# Introduction
* The SepFormer architecture is a RNN-free Transformer based architecture.
* It works significantly faster and is memory efficient in comparsion to RNN-based sepration models due to parallel nature of Transformer based architecture.

# Architecture
* The SepFormer architecure consists of encoder, decoder and a masking network as show in the following figure:

![Alt text](image.png)

* The `encoder` is fully convolutional
* The `masking network` consist of two transformers embedded inside a dual-path processing block. It predicts the masks for a certain dataset.
* The `decoder` then reconstructs the separated signals by using the mask predicted by the masking network.

# Encoder
* It takes time-domain audio singal (audio of different speakers) $x \in R^T $. It then learns a STFT representation $h \in R^{FxT'} $ using a single convolutional layer.

* It can be summarized as:<br>
            $h=ReLU(Conv1d(x))$

**Note: The stride factor of the convolution layer greatly affects the performance, memory and speed of the model.**

![Alt text](image-1.png)
<span>fig: The overall architecture proposed for the masking network. (Middle) The SepFormer Block. (Bottom) The transformer
architecture f(.) that is used both in the IntraTransformer block and in the InterTransformer block.</span>

# Masking Network
* The masking net takes as an input the STFT representation i.e $h \in R^{FxT'}$.
* It estimates the masks $ m = {m_1, m_2, ...., m_{Ns}} $ for each of the Ns speakers.
* The encoded is input is passes through `Layer Normalization` and processed by `Linear Layer` (dimension = F).
* Then, overlapping chunks of size $C$ is created by chopping up $h$ on the time-axis with an overlap factor of 50%.
* Finally, the output can denoted as $h \in R^{FxCxN_C}$, where $N_C$ is the number of chunks created.
* The representation $h'$ is then passed through a `SepFormer` block denoted by $h''$
* The output of the `SepFormer` block is passed through `PReLU` followed by a `Linear Layer` denoted by $h'''$
* Finally, `overlap-add scheme` is applied to obtain $h''''$ and is passed through `two-feed forward networks` and `ReLU` activation to obtain the mask $m_k$ for each speakers.

# SepFormer Block
* SepFormer block is designed in such way that it can model both `short-term` and `long-term` dependencies through `two transformers`.
* The transformer which models the `short-term dependencies` is called as `IntraTransformer (IntraT)` & which handles `long-term dependencies` is called as `InterTransformer (InterT)`.
* The output from this block can be denoted as:<br> $h'' = f_{inter}(P(f_{intra(h')}))$.
* This block is repeated $N$ times.

## Inter and Intra Transformers
* Let $z$ be the input the transformer.
* First, `positional encoding`, $e$, is added to the input as:
$z' = z + e$
* We then apply it to each transformer layer. Inside each transformer layer `layer normalization` followed by `MultiHead attention` is applied.
* The transformer then finally employees a `feed-forward network`.
* The overall transformer block can be described as :
$f(z) = g^K(z + e) + z$
where <br>
$g^{K}(.)$ = $K$ layers of transformer layer $g(.)$ ;<br>
$K = N$ intra layers for the IntraT, and $K = N$ inter layers

# Decoder
* Decoder uses a `transposed convolutional layer.` having same stride and kernel size as that of encoder.
* The element-wise multiplication of  between masks $m_K$ and encoder output $h$ is passed to that transposed covolution layer.

# Architecture and Training Details
* The encoder and decoder both have:
    * convolutional filters = 256 filters
    * kernel size  = 16 samples
    * stride factor  = 8 samples
* Chunk Size (C) = 250 
* Parallel Attention Heads = 8
* Positional Feed Forward Networks = 1024 dimensions
* Total number of parameters = 26 million
* Data Augmentation by `Dynamic Mixing (DM)` to create new mixtures.
* `Speed perturbation` on the sources before creating mixtures.
* Optimizer = `Adam Optimizer`
* Learning Rate = $15e^{-5}$
* `Gradient Clipping` is also applied to limit the `L2` norms of the gradient.
* Batch Size = 1 and 
* Used `scale-invariant signal-to-noise Ratio (SI-SNR)`
via utterance-level permutation invariant loss
* Maximum no of epochs = 200  (1.5 hrs per epoch one NVIDIA V100 GPU with 32 GB of memory).
* `Automatic mixed-precision` to speed up the traininig


 