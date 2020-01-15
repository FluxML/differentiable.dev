+++
fragment = "item"
weight = 100
align = "left" # Default is center, can be left, right or center
title = "Deep Learning"
+++
∂P.jl is a flexible backend for calculating gradients of deep learning models. A typical example is shown here, where a recurrent architecture using LSTMs is used to learn Shakespeare. The code sample below demonstrates many powerful elements of ∂P.jl , making use of several convenient Julia features in the process. First, the defined model has no special data types within it to enable AD; the models are defined for forward-pass calculation only, with backwards-pass definitions only for basic
building blocks such as BLAS operations and basic array manipulation. ∂P.jl is used to wrap the loss computation, explicitly denoting the bounds of the computation that should be differentiated to calculate the gradients imposed upon the model, but all other pieces of code (including the LSTM layer definition itself) are written without automatic differentiation in mind. This model executes on the CPU, GPU and Google TPU architecture, with little to no change.
