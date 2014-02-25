**python scikit-learn wrapper with json-type input features**






Input file format:

--train_features file in json formar: 

    sample1 {"feat1": 0.1, "feat1": -0.1}
    sample2 {"feat0": 5, "feat1": -0.2}

--train_labels : 

    sample1 LABEL
    sample2 LABEL

Usage:

1) 10-fold cross validation

    ./classify.py --train_features data/train.feat \
              --train_labels data/train.labels \
              --num_cross_validation_folds 10

2) Training a model and saving it

    ./classify.py --train_features data/train.feat \
              --train_labels data/train.labels  \
               --dump_classifier_filename out/fand_forest.model

3) Prediction using a trained model

    ./classify.py --load_classifier_filename out/fand_forest.model \
              --test_features data/test.feat \
              --test_predicted_labels_out out/test.labels.out \
              --write_posterior_probabilities 

4) Evaluate predictions: Accuracy & confusion matrix

    ./classify.py --load_classifier_filename out/fand_forest.model \
              --test_features data/test.feat \
              --golden_labels data/test.labels 
              
