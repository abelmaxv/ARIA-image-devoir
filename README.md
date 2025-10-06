# ARIA-image-devoir
Devoir donné en cours d'image du cursus ARIA.

Consignes : 

Implement a simple classification CNN (or use the one from the first course) and train it on the training set to reasonable accuracy (e.g. >98% on MNIST). Then freeze model weights and set the model to evaluation mode when generating adversarial examples. 
-1 Implement the FGSM (Fast Gradient Sign Attack) on the MNIST characters 
          𝑥𝑎𝑑𝑣 = 𝑥 + 𝜖 ⋅ sign(∇𝑥𝐽).  
-2 How does increasing  𝜖  affect the success rate and visual distortion? Are some classes more vulnerable (compute stats)?  Do some images require larger  𝜖  to flip?
-3 Does adding noise to the inputs (e.g. Gaussian) induce a similar misclassification rate?  
-4 What does this say about NN robustness for real-world vision systems?
-5 Lastly, implement a defense via adversarial training. Check that it works. 

Summarize your results and conclusions in a short (2 pages) report.
Hints 
- Make sure to zero gradients of the model parameters when computing gradients wrt the input, and call x.requires_grad_(True) for the input tensor.
- Normalize image ranges consistently (e.g., inputs in [0,1]). If you use normalized inputs for training (mean/std), apply the same normalization for FGSM.
- Clip adversarial image to valid range after perturbation (e.g., torch.clamp(x_adv, 0, 1)).

