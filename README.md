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
I have identified three common coffee plant diseases and created a model that will be able to successfully identify the symptoms of these diseases in the leaves of the plant. 

### Data Understanding
The data for this project comes from a Kaggle dataset of 1216 training and 388 testing images of coffee leaves that are classified as either healthy or presenting one of three diseases: miner, rust, or phoma.
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
### Conclusions
#### Next Steps
