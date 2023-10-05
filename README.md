# Classification of Coffee Leaf Pests and Diseases

![Shade Grown Coffee photo](https://github.com/e-jager/coffee_leaf/blob/e53e4849733cc89e8e02da559da0fa56361e357c/images/coffee-shade.jpg)
### Overview
Coffee farming is a global agricultural business that takes many forms from large to small farms and standardized to shade grown and organic. Coffee farming is a complex and intricate business, with millions of small-scale farmers relying on its cultivation for their income. However, this industry faces significant challenges, with coffee leaf diseases posing a constant threat to coffee crops. 
<br>
<br>
This project aims to create an image classification model that is able to identify symptoms of three different diseases and pests in coffee leaves and to distinguish them from images of healthy leaves. The benefit of this system is that it is simple, and would only require a smartphone camera to photograph leaves to identify the problem. On a larger scale, farms with more technology would also be able to quickly input larger quantities of photos into the model, creating something that would serve as a monitoring system for successful agricultural production. 

### Business Problem
Local communities in Ecuador are pooling resources and working with a local NGO, Somos Salud Integral, to start a series of organic, shade grown coffee farms in the Manabi region of coastal Ecuador. This system is being proposed to the stakeholders as a means to reduce their barrier to entry into this business because they will be ensured to have a system to monitor for disease and pests in their crops, minimizing risk of the business failing due to die off of plants. 
<br>
<br>
Coffee miner, which damages coffee leaves, and coffee rust, a highly contagious fungus that causes extensive leaf loss, lead to reduced coffee yields and inferior bean quality. Phoma, another fungal disease, contributes to further crop losses. These issues result in increased production costs, decreased profitability for coffee farmers, and potential price hikes for consumers. The economic consequences extend beyond the farm gate, affecting coffee trading, export, and the coffee supply chain. As a result, finding effective solutions to identify and combat these pests and diseases is crucial to ensure the sustainability and resilience of the coffee industry, safeguarding both the livelihoods of coffee growers and the availability of high-quality coffee for consumers worldwide.
<br>
<br>
An image classification model designed to identify coffee leaf pests and diseases such as coffee miner, coffee rust, and phoma offers a promising and impactful solution to the challenges faced by the coffee industry. By utilizing machine learning and computer vision, the model can rapidly detect the presence of these pests and diseases in coffee plants based on images of their leaves. Early detection allows for timely intervention, enabling farmers to take preventive measures, such as targeted pesticide application or the removal of affected plants, before the infestations spread. This proactive approach can significantly reduce crop damage and yield losses.
<br>
<br>
The model can pinpoint the specific type and severity of the infestation, allowing for precise and customized treatment strategies. This targeted approach minimizes the use of pesticides and resources while maximizing the effectiveness of interventions, reducing production costs, and minimizing environmental impacts.By identifying and addressing coffee leaf pests and diseases promptly, the model can help maintain healthier coffee plants. Healthy plants produce higher yields of better-quality beans, leading to increased income for coffee farmers and improved overall product quality in the market. Early detection translates to timely interventions, empowering farmers to take preventive measures such as precise pesticide application and targeted plant removal before the infestations escalate. Consequently, crop damage and yield losses are significantly reduced, resulting in healthier coffee plants that yield higher quantities of superior-quality beans. Moreover, the model's precision enables tailored treatment strategies, minimizing the environmental impact of pesticides and optimizing resource allocation. This innovation fosters cost savings, supports sustainable agricultural practices, and empowers coffee farmers with knowledge to protect their crops and livelihoods. Its potential for global deployment stands to benefit coffee producers across diverse regions, ensuring the industry's resilience and safeguarding the consistent supply of premium coffee for consumers worldwide. Ultimately, an image classification model for coffee leaf pests and diseases holds the promise of revolutionizing coffee farming, aligning economic prosperity with environmental sustainability.

### Data Understanding
The data for this project comes from a Kaggle dataset of 1216 training and 388 testing images of coffee leaves that are classified as either healthy or presenting one of three diseases: miner, rust, or phoma.
<br>
The dataset can be found at this link: https://www.kaggle.com/datasets/badasstechie/coffee-leaf-diseases?resource=download
<br>
<br>
#### Healthy coffee leaf
![Healthy coffee leaf](https://github.com/e-jager/coffee_leaf/blob/e53e4849733cc89e8e02da559da0fa56361e357c/data/images_sorted/test/test_healthy/1118.jpg)
<br>
<br>
The photos below show each disease of the coffee leaves, and it is evident in each that they are present themselves in distinct ways - the miner affected leaves have brown splotches, the rust affected have yellow, round spots, and the phoma affected may have brown spots, but primarily have tips that are shriveled.
#### Coffee miner
Leucoptera coffeella, or the coffee leaf miner, is a moth found in South America, Central America, and the West Indies. It is a small moth, with an average adult wingspan of 6.5 millimeters (0.26 inches). The larvae of these moths feed on the leaves of the coffee plant, leaving them with brown necrotic spots. It is considered one of the worst pests of the coffee plant due to the large amount of damage it can inflict. 

![Leaf affected by coffee leaf miner](https://github.com/e-jager/coffee_leaf/blob/e53e4849733cc89e8e02da559da0fa56361e357c/data/images_sorted/test/test_miner/72.jpg)

#### Coffee rust
Hemileia vastatrix is a multicellular fungus that infects coffee plant leaves causing coffee leaf rust. It is an obligate host of the coffee leaf, meaning it relies on the plant and must come in contact with it to survive. It is one of the most economically important diseases that affects coffee plants worldwide. It can kill plants by covering leaves in its spores, which limits their ability to photosynthesize. This causes leaves to die and fall off, leading eventually to the inability of the whole plant to survive. 

![Leaf affected by coffee leaf rust](https://github.com/e-jager/coffee_leaf/blob/e53e4849733cc89e8e02da559da0fa56361e357c/data/images_sorted/test/test_rust/1122.jpg)

#### Coffee phoma
Ascochyta tarda or Phoma tarda is a fungal plant pathogen that causes dieback and leaf spots in coffee plants. Dieback is a process by which plants begin to die beginning with the tips of the leaves shriveling and drying up. Cold climate, heavy rain, strong wind, and hail all increase the prevalence and damage caused by phoma. However, due to climate change and warming of the climate, it is becoming less common. 

![Leaf affected by coffee leaf phoma](https://github.com/e-jager/coffee_leaf/blob/e53e4849733cc89e8e02da559da0fa56361e357c/data/images_sorted/test/test_phoma/512.jpg)

### Modeling
I worked through several different iterations of models before reaching the final. First I created a dummy model as a baseline to see what the accuracy would be. Next, I started working on Sequential models using tensorflow keras, changing parameters to improve the model. A Sequential model is a good choice for image classification tasks due to its simplicity and versatility. They offer a straightforward interface for adding layers, making it ideal for building custom architectures tailored to specific image classification challenges while benefiting from the automatic gradient computation and optimization capabilities provided by deep learning frameworks in tensorFlow and keras.
<br>
<br>
I used a grid search as well to improve the Sequential model, but ultimately I wasn't happy with the final accuracies I was able to achieve so I decided to switch to a Convolutional Neural Network (CNN). Using a CNN for image classification offers advantages by leveraging specialized convolutional layers to automatically learn and extract hierarchical features from images. This enables CNNs to capture intricate patterns and spatial relationships within images, making them highly effective for tasks like image classification. 
<br>
<br> Below are the validation curves that I got from my first CNN model, that was not pretrained. The curves are close together which could indicate that the model is not too overfit. After 50 epochs, the validation accuracy (0.6763) is higher than the training accuracy (0.5880). This means that the model is possibly underfit and needs to be more complex to suit the images the model is classifying. 
<br>
![CNN model curves](https://github.com/e-jager/coffee_leaf/blob/fb770bb1629dcf6e253d03101fdbf0dd4daa2ed4/images/CNN_modelcurves.png)
<br>
<br>
The final model I concluded with is a pretrained CNN model called VGG16 that has 16 layers. Pretrained models have pretrained weights for networks, so the hierarchies are already assigned to what a type of image would need, allowing them to be a lot more complex and run a lot faster than if I made the same model myself. The validation loss achieved is pretty low (0.0784), meaning that the model is able to predict the class of new data well, but the training data loss (0.2531) is a little higher. However, the fact that the validation loss is lower than the training is a positive indicator suggesting the model is generalizing well to new data. The training accuracy I got for this model is 0.9104 and the validation accuracy is 0.9876. Additionally, the curves are very close together to each other in each graph, indicating that the model is not overfit. 
![vgg16 model curves](https://github.com/e-jager/coffee_leaf/blob/83f21f0eda53dc22c8ec6b8da1bc1468dfad491a/images/VGG16_modelcurves.png)
### Results
This is a confusion matrix for the classes the VGG16 model predicted for the images in the test dataset. I think this particular set is too small, and if it were larger we would see better results, more consistent with the accuracy of the model. It predicted the healthy leaves most accurately, but it failed to predict correctly a lot of the images in the other disease/pest categories.
<br>
![confusion matrix](https://github.com/e-jager/coffee_leaf/blob/83f21f0eda53dc22c8ec6b8da1bc1468dfad491a/images/confusion.png)
### Conclusions
Ultimately this model, could be a tool for farmers of coffee crops to be used to identify these three pests/diseases in their plants. Being able to identify pest/disease risk, especially early before they are able to spread to an entire crop has huge benefits to the agricultural business. Economic stability for smaller coffee farms is essential, and being able to sustain a farm is also beneficial for sustainability of the environment. This model could also help farms scale to larger sizes, with it being able to monitor crops that are more than a farmer, especially in remote rural areas, would be able to monitor by eye. Shade grown coffee is a popular method for growing the crop, and it is often done in forest areas that are physically difficult to navigate as often as they would need to be in order to be monitored for pests/disease by indviduals working on the farm. Finally, being able to detect pests and diseases with a model could help to optimize resource allocation for farms, making them more sustainable and even beneficial for the environment. 
#### Next Steps
For next steps, I think there are a lot of directions I could go in depending on the feedback from my stakeholders, but first I would create an app to implement the model on real farms and make it really user friendly. Next I would scale the model to be used on larger scale farms, which could include creating a system to place monitoring cameras around a farm that would automatically monitor the crop health. And last I would collect more data and expand to other crop health indicators that can be seen from leaves such as drought stress and nutrient deficiencies. This could create a well rounded monitoring system for crop health in general.

### References
#### Coffee pests/diseases
https://en.wikipedia.org/wiki/Leucoptera_coffeella <br>
https://www.apsnet.org/edcenter/disandpath/fungalbasidio/pdlessons/Pages/CoffeeRust.aspx <br>
https://en.wikipedia.org/wiki/Ascochyta_tarda

#### VGG16 model
https://medium.com/@mygreatlearning/everything-you-need-to-know-about-vgg16-7315defb5918
<br>
https://datagen.tech/guides/computer-vision/vgg16/
<br>
https://keras.io/api/applications/vgg/
<br>
https://pytorch.org/vision/main/models/generated/torchvision.models.vgg16.html
<br>
https://builtin.com/machine-learning/vgg16
<br>

#### CNN Models
https://www.tensorflow.org/tutorials/images/cnn <br>
https://towardsdatascience.com/build-your-own-convolution-neural-network-in-5-mins-4217c2cf964f
