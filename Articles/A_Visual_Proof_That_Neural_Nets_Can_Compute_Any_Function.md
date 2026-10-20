# A Visual Proof That Neural Nets Can Compute Any Function

> **Source:** Michael Nielsen, *Neural Networks and Deep Learning*, [Chapter 4](http://neuralnetworksanddeeplearning.com/chap4.html)
> **Tags:** `deep-learning` `theory` `universal-approximation`

## TL;DR
A neural network with **just one hidden layer** can approximate **any continuous function** to any desired accuracy, provided the hidden layer has enough neurons. Nielsen shows *why* with pictures instead of heavy math.

## Key Ideas

### 1. What the theorem actually says
- **Approximate, not exact:** for any target accuracy ε > 0, there is a network whose output stays within ε of the function everywhere on the input range.
- **Continuous functions:** a discontinuous function (a jump) can't be matched exactly, but a continuous approximation is usually good enough in practice.
- It says such a network **exists** — not that gradient descent will find it, or how many neurons it needs.

### 2. A sigmoid neuron can become a step function
The output of one hidden neuron is σ(wx + b). Making the weight `w` very large turns the smooth sigmoid into an (almost) **step function**.
The step happens at position **s = −b / w**, so each neuron can be described by a single number: *where it steps*.

### 3. Two steps make a "bump"
Take two hidden neurons that step at s₁ < s₂, and give them output weights **+h** and **−h**. Their sum is a rectangle ("bump") of height `h` between s₁ and s₂, and zero elsewhere.

### 4. Many bumps approximate any curve
Split the input range into many small intervals and put one bump of the right height on each one. The result is a staircase that tracks the target function — like a histogram. More neurons ⇒ narrower bumps ⇒ a closer fit.

### 5. More inputs: towers
With two inputs, a pair of neurons stepping in `x` gives a ridge, and combining ridges in `x` and `y` (plus a threshold bias) gives a **tower** over a small square. Many towers approximate any function of two variables, and the same idea extends to any number of inputs.

### 6. Beyond sigmoid
The argument works for any activation that can be squashed into a step. **ReLU** works too (two shifted ReLUs make a ramp; ramps combine into bumps). Plain linear activations do **not** work — a stack of linear layers is still linear.

## Why Use Deep Networks Then?
Universality says one hidden layer is *enough in principle*, but it may need an enormous number of neurons. Deep networks build **hierarchies of concepts** (edges → shapes → objects), which in practice lets them represent complex functions far more efficiently and makes them easier to learn.

## My Takeaways
- The theorem removes the question "can a network represent this?" — the real questions become *how big* the network must be and *whether training will find it*.
- The step-and-bump picture is a great mental model for what individual hidden units contribute.

## Further Reading
- [Full chapter (interactive)](http://neuralnetworksanddeeplearning.com/chap4.html)
- Cybenko, G. (1989). *Approximation by superpositions of a sigmoidal function.*
- Hornik, K. (1991). *Approximation capabilities of multilayer feedforward networks.*
