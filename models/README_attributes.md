In this file there is a detailed description of the class attributes included in the accompanying model py files.

    --> (resnet.py) type_: one of '34', '50'

    --> no_of_classes: integer

    --> trainable_feature_layers / trainable_layers:
                                  This attribute is either 'None' (default) OR a list of indices where each index 
                                  corresponds to the layer index among the model's features. The list allows the user 
                                  to choose any layers of preference for training regardless of their position in the architecture.
                                  As per .py files, we note that the classifier / fully connected part of the network is always trainable
                                  
                                  Per pretrained architecture the trainable layers are indexed as follows :
                                  
                                  ----------DenseNets-----------     |    ------GoogLeNet--------    |    ------ResNets--------  
                                      LAYER               INDEX      |      LAYER         INDEX      |      LAYER        INDEX
                                  features.conv0       :    0        |      conv1       :   0        |      conv1     :    0
                                  features.norm0       :    1        |      maxpool1    :   1        |      bn1       :    1
                                  features.relu0       :    2        |      conv2       :   2        |      relu      :    2
                                  features.pool0       :    3        |      conv3       :   3        |      maxpool   :    3
                                  features.denseblock1 :    4        |      maxpool2    :   4        |      layer1    :    4    
                                  features.transition1 :    5        |      inception3a :   5        |      layer2    :    5
                                  features.denseblock2 :    6        |      inception3b :   6        |      layer3    :    6
                                  features.transition2 :    7        |      maxpool3    :   7        |      layer4    :    7
                                  features.denseblock3 :    8        |      inception4a :   8        |
                                  features.transition3 :    9        |      inception4b :   9        |
                                  features.denseblock4 :    10       |      inception4c :   10       |
                                                                     |      inception4d :   11       |
                                                                     |      inception4e :   12       |
                                                                     |      maxpool4    :   13       |
                                                                     |      inception5a :   14       |
                                                                     |      inception5b :   15       |
                                  -------------------------------------------------------------------------------------------------
                                  In the above structures, note that ReLU and MaxPool layers do not have trainable params
 

