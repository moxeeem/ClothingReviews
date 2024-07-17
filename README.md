# 🛒 Women's E-Commerce Clothing Reviews
![img](\img\img.jpg)

## Project Description

In this project, we use transformers to predict product ratings and to determine the tone of the review based on preprocessed customer text reviews.


## Table of Contents

- [🛒 Women's E-Commerce Clothing Reviews](#-womens-e-commerce-clothing-reviews)
  - [Project Description](#project-description)
  - [Table of Contents](#table-of-contents)
  - [Files](#files)
  - [Dataset](#dataset)
  - [Preprocessing](#preprocessing)
  - [Binary Classification](#binary-classification)
  - [Multiclass Classification](#multiclass-classification)
  - [Include Credits](#include-credits)
      - [Author](#author)
      - [Course](#course)
  - [License](#license)

## Files
- [ClothingReviewsClassification.ipynb](https://github.com/moxeeem/ClothingReviews/blob/main/ClothingReviewsClassification.ipynb) : Jupyter Notebook with text preprocessing and model training
- [/binary](https://github.com/moxeeem/ClothingReviews/tree/main/binary) : Binary classification model's files
- [/multiclass](https://github.com/moxeeem/ClothingReviews/tree/main/multiclass) : Multiclass classification model's files

## Dataset
We use [Women’s Clothing E-Commerce dataset](https://www.kaggle.com/datasets/nicapotato/womens-ecommerce-clothing-reviews) revolving around the reviews written by customers

This dataset includes 23486 rows and 10 feature variables. Each row corresponds to a customer review, and includes the variables:

|Feature|Type|Description|
|---|---|---|
|`Clothing ID`|Integer|Variable that refers to the specific piece being reviewed.|
|`Age`|Integer|Variable of the reviewers age.|
|`Title`|String|Variable for the title of the review.|
|`Review Text`|String|Variable for the review body.|
|**`Rating`**|Integer|Variable for the product score granted by the customer from 1 Worst, to 5 Best.|
|**`Recommended IND`**|Integer|Variable stating where the customer recommends the product where 1 is recommended, 0 is not recommended.|
|`Positive Feedback Count`|Integer|Variable documenting the number of other customers who found this review positive.|
|`Division Name`|String|Categorical name of the product high level division.|
|`Department Name`|String|Categorical name of the product department name.|
|`Class Name`|String|Categorical name of the product class name.


## Preprocessing

In the process of text preprocessing, we employ methods such as tokenization, POS-tagging, and lemmatization. All these operations are carried out using the nltk library. Additionally, we remove stop words and convert the text to lowercase. 

## Binary Classification

We use  `bert-base-uncased` to binary classification for predicting whether the review is positive or negative.

**f1 score**: 0.8507015684469733 
**number of epochs**: 10

The classifier does its job well. For successful classification, it is necessary to write a review using a sufficient number of explicit evaluative words.


## Multiclass Classification

We use `distilroberta-base` to multiclass classification for predicting the rating of the product.

**f1 score**: 0.6033866825602262
**number of epochs**: 20

Overall accuracy for each class:
- Class 0: 0.24
- Class 1: 0.31
- Class 2: 0.34
- Class 3: 0.35
- Class 4: 0.81

The classifier confuses classes that are close in value, for example: class 2 with 1 and 3.
The classifier distinguishes classes well at a distance, for example: class 4 is little confused with class 0.
Most likely, this result was due to an unbalanced dataset.

## Include Credits

#### Author
Maxim Ivanov - [GitHub](https://github.com/moxeeem), [Telegram](https://t.me/fwznn_ql1d_8)

#### Course

This project was completed as part of the ["Практический Deep Learning"](https://stepik.org/course/179805) course offered by [AI Education](https://stepik.org/users/628121134).


## License
This project is licensed under the MIT license. For more information, see the [LICENSE](/LICENSE) file.
