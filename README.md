# Classroom-Introduction-to-Python-based-Artificial-Intelligence
Coursework material for [introduction-to-python-with-artificial-intelligence](https://kapoorlabs.org/product/introduction-to-python-with-artificial-intelligence/)

\documentclass[a4paper,10pt]{article}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{authblk}
\usepackage{textcomp}
\usepackage{longtable}
\usepackage{eurosym}
\usepackage{graphicx}
\usepackage{hyperref}
\title{Program syllabus for : \href{https://kapoorlabs.org/product/introduction-to-python-with-artificial-intelligence/}{Classroom}} 
\author[]{Varun Kapoor}
\affil[]{Kapoorlabs, Paris, France}
\date{February 2022}

\begin{document}

\maketitle

\section{Introduction to AI based image analysis}

\subsection{Package installation \label{install}}
\subsection{Creating training data for instance segmentation \label{td_instance}}
\subsection{Creating training data for image classification\label{td_class}}
\subsection{Bias Variance tradeoff \label{bias_variance}}
\subsection{Keras features for model training \label{keras_train_features}}
\subsection{Using keras to create encoder-decoder networks \label{keras_net}}
\subsection{Model hyperparameters \label{model_hyp}}
\subsection{Activation functions \label{model_act}}
Activation functions of the last layer are a crucial choice and depends on the task, if it is a segmentation task the final activation is linear as it estimates the mean value of the Gaussian distribution (assumption being that the data generating distribution is Gaussian). If the task is image classification the last activation function is either softmax or sigmoid. The activation functions are strongly coupled to the choice of the training loss. For segmentation task the training loss is mean absolute or mean squared error while for classification tasks is categorical or binary cross entropy.
\subsection{Before Training: Over/Underfitting \label{over_under}}
Before starting the model training, it is essential to split the data into training and validation datasets. This is to perform cross validation to judge if the model is over/under fitting on the training dataset. Such information can be seen in the training and validation loss curves. \newline
\textbf{Your model is overfitting on the data} if you see the validation loss curve rising instead of following the training loss curve. This gap between the two is called the generalization gap and is a result of high variance of the estimator \ref{bias_variance}. High variance comes due to large coefficients in the weight vector. Regularization is a technique used to penalize such large coefficients in the weight vector. Increasing the regularization coefficient adds to the penalty being higher, \textbf{increasing regularization coefficient helps avoid over fitting}. Your model can be overfitting on the data if the \textbf{training data is not enough}, \textbf{either increase the training data or use data augmentation} to avoid overfitting. It is also a good idea to check if your \textbf{model is too complex}, reducing the number of hidden units (reducing depth, number of convolutional filters \label{model_hyp}) also helps in avoiding overfitting. You can also add a \textbf{keras callback \label{keras_train_features} for early stopping to avoid overfitting}.  
The opposite sitution to this is underfitting.\newline
\textbf{Your model is underfitting on the data} if you see high training and validation loss that does not improve. This situation arises due to high bias of the estimator \ref{bias_variance}. In this case \textbf{increasing the model complexity} by adding more hidden neurons, increasing the network depth and or the number of convolutional filters would help. If you are using regularization then \textbf{decreasing the regularization coefficient} and increasing the training time simultaneously would avoid this problem.



\end{document}
