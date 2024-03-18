# 1. meeting: 05/03/2024
- Present our idea: 
    * We want to work with medical data 
    * Often seen that 70/30 for accordingly sick/healty --> augmentation to produce healty images
    * For the model construction we think something like cycle GAN for aug, then use YOLO... 
- Questions: 
    1. How much "new work" do we need, and how much can we get inspiration from others? 

- Notes:
- select 2 or more papers (related work - not in high detail, how data aug is used)
- resulst : show how they works... 
- take reulst and compare - which are faster wich most impact 
- different approaches (and prioritixe)
- aug in input and in train 
- experiments: varience..... 
- find mathemical explanations 
- this aug works for small models but not for big ones... 
- yolo!  (check papers)
- if std approach choose different types 
- could compare with e.g cycleGAN 
- COCO dataset (80 object categories)


# 2. meeting: 19/03/2024

Questions: 
- The method of testing many methods on the same model and see the variance and mean in between ?? 

- Dataset: Should we use the entire coco dataset or would it make sense for us to only use a subset, to see the change with data augmentation? (Which way to view the problem?)
- YOLO: If we want to do data augmentation on the training data, and we now have used the yolo model, you have given, is this then possible? Can we change the weights?? 
- We are mainly using the code you have provided, is this okay? We think our task is the comparison part... 
- Are there any guidlines for the length of the report? 
