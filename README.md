# Hybrid Quantum Classical Neural Networks

Hi There! 👋<br/>
This is a repo where you have access to all the Jupiter Notebooks, along with some resources that made it all possible!<br/>

## Table of Contents
* [What's Hybrid Quantum Classical Neural Networks?](##What's-Hybrid-Quantum-Classical-Neural-Networks?)
* [Diabetic Retinopathy](##Diabetic-Retinopathy)
* [Acknowledgements](##Acknowledgements)
* [Connect with me](##Connect-with-me)

## What's Hybrid Quantum Classical Neural Networks?

### TL;DR 
There are 2 parts to a Hybrid Quantum Classical Neural Network: The classical NN and the quantum circuit. The classical NN is your standard NN with it's inputs, weights and biases. The quantum part is acutally a Parameterized Quantum Circuit, with it's qubits, rotations and CNOT gates.

### A Longer Explanation:

<p align="center">
<img src="HQCNN.png" width="350"/><br/>
Credit: Qiskit
</p>

Here's a diagram of what exactly a Hybrid Quantum Classical Neural Network looks like! We have a normal neural network at the top which just takes in all the data and computes and compresses it down to a lower size. Then we take the outputs of that classical networks and use it as the rotations of our qubits. Finally we take the outputs of those qubits and put them inside of another classical neural network, which then outputs the result

That's a nice scaled down version of the Hybrid Quantm Classical Neural Network. I did it a bit different. For the first part, I didn't just use classical neural networks. I used a CNN (So Conv2d, Maxpooling, Relu) along with some linearl layers attatched to the end (with dropout and Relus). Now comes the PQC! In the diagram there are 2 qubits, each with only 1 rotation, but we can do a lot more with the PQC! Take for example this:

<p align="center">
<img src="PQC.png" width="350"/><br/>
Credit: https://arxiv.org/pdf/1912.06184.pdf
</p>

I used this circuit inside of my Hybrid Quantum Classical Neural Network, and it works quiet well! There are 3 qubits, each with 3 rotations. There's 1 rotation that's done on every single qubit (hence 7 parameters). I took these outputs and put them into another classical neural network to obtain the results!

The hardest part of coding this all was the backpropbagation. You can't preform backpropagation inside of a PQC, so I did the next best thing - Parameter shift rule. Instead of the derivitive of the parameter, you just find the difference between a little nudge to the left and the little nudge to the right. We're nudging one of the parameters. Using this we can feed it into the loss backwards so we can update all the parameters!

## Diabetic Retinopathy
Diabetic Retinopathy is a disease that's caused by diabeties. It occurs then the blood vessles at the back of your eye become damaged. There are 4 stages (5 if you include no Diabetic retinopathy) of the disease, ranging from symptoms of mild vison problems and progressing towards blindness. This is a tremendous point of suffering for the human population - this project aims to stop that. 

Those those living in rural and poor areas, screening for this disease is game changing. But problems arise when you don't have easy access to a doctor. With this model, we can diagnose diseases via a normal phone! 

Now, practically speaking, we don't need the quantum part of our model. But it's just fun to include and play around with!

## Acknowledgements

* [Understanding LSTM Networks by Christopher Olah - A wonderful guide to LSTMs](https://colah.github.io/posts/2015-08-Understanding-LSTMs/)
* [Reserach Paper that details the history, evolution and math of LSTMs](https://arxiv.org/pdf/1909.09586.pdf)
* [Illustrated Guide to LSTM’s and GRU’s: A step by step explanation](https://towardsdatascience.com/illustrated-guide-to-lstms-and-gru-s-a-step-by-step-explanation-44e9eb85bf21)
* [The Dataset I used](https://www.kaggle.com/shahir/protein-data-set/notebooks)
* [Resource that helped me code](https://towardsdatascience.com/lstm-text-classification-using-pytorch-2c6c657f8fc0)
* [Resource that helped me code](https://www.analyticsvidhya.com/blog/2020/01/first-text-classification-in-pytorch/)
* [Resource that helped me code](https://huggingface.co/Rostlab/prot_bert)
* [Resource that explains the importance](https://arxiv.org/ftp/arxiv/papers/1701/1701.08318.pdf)
* [Resource that explains the importance](https://www.nature.com/articles/nrm2281)
* [Resource that explains the importance](https://www.newscientist.com/article/2194516-we-dont-know-what-a-fifth-of-our-genes-do-and-wont-find-out-soon/)
* [Resource that explains the importance](https://news.mit.edu/2019/machine-learning-amino-acids-protein-function-0322)
* [Resource that explains the importance](https://www.frontiersin.org/articles/10.3389/fbioe.2020.00391/full)

## Connect with me

If you want to follow along on my journey, you can join my [monthly newsletter](https://www.subscribepage.com/g1p8w4), check out my [website](https://dicksonwu654.github.io/), and connect on [Linkedin](https://www.linkedin.com/in/real-dickson-wu/) or [Twitter](https://twitter.com/DicksonWu3) 😃
