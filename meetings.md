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


Notes:

- Training, check darknet, use higher levels of yolo, https://github.com/WongKinYiu/yolov7
    - pretrained models, 
    - small models, firstly
    - yolo code, first download model, accuracy is the same. Further train it, first with pictures, and then after with our data augmentation.
    - measure? model same, inference speed would be the same. Different methods would take more or less time. 
    - train on hole data set(coco), same procedure is correct. 
        - randomness
        - downlaod already trained model
        - retrain the model and confirm accuracy. 
        - train with the same procedure

        - start experiment, remove data augmentation from the original
        - then we should use different methods, one by one or more together, and train. (aplecation study)
        - see results

        - next step, reduce coco(subset)
        - see what we can do with data augmentation, and see which methods works best. 

- metoder, kig på hvilke der er brugt meget nu her. 


        
- Data augmentation, during trainnig. Use it for test, he dont think so
- GPU, brightspace see tutorial

# 4. meeting: 09/04/2024
Questions: 
- We have found out to remove data augmentation. Can we use their implementations to handle the experiments (with support from other articles why we use these particular ones)
    - Or do our project needs us to implement anything ourselves?

- We are thinking to divide it into two different experiments. 
    1. Test whole dataset validate with their results and test individual traditional data augemntations (all 3 categories)
    2. Make subset and make test of org. data for comparison and use CycleGen datasets of syntehtic dataset. Maybe also compare with some traditional data augemntations.

- After moving our data to data0 folder, we cannot run the test. AssertionError: Image Not Found coco/images/val2017/000000298251.jpg.
    - the only thing we have changed is the paths in the coco.yaml file. How else ?? 


Notes: 
Q1
- Just add code from somewhere or make it yourself
- i understood that we can do what we wanted 

Q2
- focus on traditionel
- Anders thinks its sounds reasonable 
- (I also found doc to do so in the articel for related work)

Q3

ln -s /data0/x ~/yolov7/dataset 
Creating a symbolic link

Lad det ligge i home (ikke mere end 50G) 

# 6. Meeting: 23/04/2024
- should we set the hyp. prob. to 1.0 or 0.5 (same as them) here fliplr. 
- should all hyp be tested individually if we have an interresting combination? 
    - Because we want to test rotate, but nothing is represented 100 % as in the articel we where considering combining degree and perspective
- Does batchsize matters? we have the retrained model with batch 3, and it gives us a much lower accuracy
- We can see that in the train file it runs parallel, but we cannot see that on the graphs on the website
- 

Batch size, we should increase number of epochs by 2(multiply)

try: 
- tiny with bact 32
- original batch 16 and 2 times epochs
- original batch 8 and 4 times epochs


Our training is not comparable, data augmentation need more training. Wo aug does not need as much

Check multiple GPU, device 1 and device 0, 

hyp prob, test different fractions, 

test combinations of fractions, some work better than others with different fractions (måske ikke tidsmæssigt muligt)

Modellen er ikke den vi tester men det er dataaugmentation!! vi skal bare huske at skrive dette!!!!

Vores eksperimenter skal bare give mening, vi skal huske at udpensle

Cycle gan - vi behøves ikke at eksperimentere eller teste, men vi kan bare beskrive den i related work og teori
for at sige at det er det nye man kan bruge 
Vi kan godt skrive en "future work" i diskussion, husk på ikke at skrive noget vi kan gøre noget anderledes
Sammenligning med to aproches (Gan og klassiske metoder)



# 7. Meeting 30/04/2024

- Original YOLO : 


- tiny YOLO : 


- We should use the distributed GPU as a baseline with 16 batzh and 1200 epochs
- As many technique as we can!
    - compare
- 2 weeks left, last meeting last meeting next time

Forklar ift teori, hvorfor vi ikke får de samme resultater
- hvad kendetegner træning, helt gennerelt...!!!  
    - learningrate ift batchsize
        - nogle modeller er meget følsom overfor det
        - normalilsering af billeder 
    - skaler batchsize så skal man skaler learningrate
        - anders tror ikke at det skyldes det

- sæt en deadline for hvornår vi begynder med plan b.



