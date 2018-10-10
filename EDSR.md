# Enhanced Deep Residual Networks for Single Image Super-Resolution
- Abstract:     
>1. Use Residual Networks but optimize it by **analyzing and removing** unnecessary modules    
>2. Do some modification on training **multi-scale training**
>3. PSNR and SSIM
- Related work:     
>1. Interpolation base on sample theory:    
 low resolution image is down sample of the high resolution image
>2. Adopt nature image statistic to problem (?)
>3. Neighbor embedding (machine learning method)
>4. Sparse coding （machine learning method）
>5. Deep Neural Networks:       
>>- **SRCNN 香港中文大学，汤晓鸥:**    
>>  **3 convolutional layers:**      
feature extraction --> non-linear mapping --> reconstruct
>>- **Residual Network for SR:**    
To get deeper network and superior performance
>>- **Use Recursive Convolutional Network:**         
《Deeply-Recursive Convolutional Network for Image Super-Resolution》
__alleviate the burden of carrying identity information in the super-resolution network???__.
>>- **Encode and Decode structure with skip connections:**    
they said it provide fast and improved convergence
>6. Training strategy:      
1) Many method do the upsample operation via bicubic Interpolation before the image feed to the Network      
2) In VDSR, they train a single Network using multi-scale images 2X 4X 8X so the network can deal with multi-scale problem.    
3) Geometric Self-ensemble, do some transform operation to the lr images as a set and then feed them to the network（个人理解是生成多个针对于不同角度变换lr的学习模型，然后将这些模型给一些权重，集成成一个更具有鲁棒性的学习器）![](assets/markdown-img-paste-20181009163342426.png)
![](assets/markdown-img-paste-20181009163311585.png)
>7. Loss function: MSE or L2 loss, SSIM
- Propose method:       
remove BN: they get rid of range flexibility from
networks by normalizing the features **???**
