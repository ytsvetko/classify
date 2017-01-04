**A wrapper to python scikit-learn classifiers**

**(e.g., SVM, Logistic Regression, Random Forest, Gradient Boosted Regression Trees)**

**that works with sparse input features in json format**

Input files format:


train_features file in json format: 

    sample1 \t {"feat0": 0.1, "feat1": -0.1}
    sample2 \t {"feat0": 5, "feat1": 0.5, "feat2": -0.2}

train_labels file: 

    sample1 \t LABEL
    sample2 \t LABEL
 

Usage:

1) 10-fold cross validation

    ./classify.py --classifier RandomForest \
              --train_features data/train.feat \
              --train_labels data/train.labels \
              --num_cross_validation_folds 10

2) Training a model and saving it

    ./classify.py --classifier SVM \
                  --train_features data/train.feat \
                  --train_labels data/train.labels \
                  --dump_classifier_filename out/svm.model

3) Prediction using a trained model

    ./classify.py --load_classifier_filename out/svm.model \
              --test_features data/test.feat \
              --test_predicted_labels_out out/test.labels.out \
              --write_posterior_probabilities 

4) Evaluate predictions: Accuracy & confusion matrix

    ./classify.py --load_classifier_filename out/svm.model \
              --test_features data/test.feat \
              --golden_labels data/test.labels 
              
