---
URL: https://www.youtube.com/watch?v=d3RrbeJKNoc&t=221s
Repo: https://github.com/MouseLand/cellpose
Paper: https://www.nature.com/articles/s41592-020-01018-x
Video code: https://github.com/bnsreenu/python_for_microscopists/blob/master/305_What_is_Cellpose_algorithm_for_segmentation.ipynb
---
## Cellpose: a generalist algorithm for cellular segmentation
 - Generalist -> can very precisely segment a wide range of image types
 ![[Pasted image 20240313162839.png]]
 1. Generate an auxiliary representation for the masks - an energy function for the mask as the equilibrium distribution of a **heat- diffusion simulation with a heat source placed at the center of the mask**
 2. The **<mark style="background: #FFB86CA6;">horizontal and vertical gradients of the energy function</mark>** form a reversible representation of the masks in a format that can be /red predicted directly by a neural network
 3. In **<mark style="background: #FFB86CA6;">addition the the two spatial gradient maps</mark>**, they predict a third map which classifies pixel as inside or outside of cells, which helps to precisely predict cell boundaries
 4. Finally they recover the predicted masks by running the gradient ascent procedure on the pixel with probabilities greater than 0.5
 5. The neural network that predicts the spatial flows was based on the general U-net architecture
**Other Tools** : stardist, mask r-cnn -> cellpose outperforms those