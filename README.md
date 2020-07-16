# getting-started-with-nlp
This is the material for the intro to nlp workshop by Alexandra Cosseron and Eva Jaumann.

In order to be ready for this workshop, you need to:
- [Setup your computer](#Setup-your-computer)
- [Download Amazon reviews dataset](#Download-the-necessary-data)


## Setup your computer

#### Step 1: Requirements
- pyenv >= 1.2.13
- python >= 3.7.0

#### Step 2: Clone the workshop repository

```
git clone https://github.com/pyladieshamburg/getting-started-with-nlp.git
cd getting-started-with-nlp
```
#### Step 3: Setup your virtual environment

With *pyenv* and *poetry*:
```
pyenv local 3.7.4
pip install poetry
make setup
```

#### Step 4: Open Jupyter Lab

Run the following command in your shell: 
```
poetry run jupyter lab
```

## Download the necessary data

We will use two datasets during the workshop:
1. `SMS Spam Collection` dataset, which has been downloaded for you and which you will find in the folder `data` of this repo.
More information about this dataset can be found in the following section;
2. `Amazon Reviews: Unlocked Mobile Phones`, which you will need to download by yourself.

`Amazon Reviews: Unlocked Mobile Phones` is a public dataset made available through the Kaggle platform.
You can download it [here](https://www.kaggle.com/PromptCloudHQ/amazon-reviews-unlocked-mobile-phones/data#). You will need to create
a free Kaggle account in order to do so.
Once the downloading is completed, you can place the file in the folder `data` (the code we will use assumes that the data files
are located there, you will need to adjust the code accordingly if you don't). No need to unzip the file at this stage, it is handled in the code.


## Information about the data we will use

#### Part 1: SMS Spam Collection

As described in its [dedicated website](http://www.dt.fee.unicamp.br/~tiago/smsspamcollection/):

> The SMS Spam Collection v.1 is a public set of SMS labeled messages that have been collected for mobile phone spam research. 
> It has one collection composed by 5,574 English, real and non-enconded messages, tagged according being legitimate (ham) or spam.

Further details about this dataset can be found at http://www.dt.fee.unicamp.br/~tiago/smsspamcollection/ .

The paper of reference for this dataset is: 

Almeida, T.A., Gómez Hidalgo, J.M., Yamakami, A. **Contributions to the Study of SMS Spam Filtering: New Collection and Results.** 
Proceedings of the 2011 ACM Symposium on Document Engineering (DOCENG'11), Mountain View, CA, USA, 2011.
[preprint](http://www.dt.fee.unicamp.br/~tiago/smsspamcollection/doceng11.pdf)

#### Part 2: Amazon Reviews: Unlocked Mobile Phones

[Kaggle dedicated webpage](https://www.kaggle.com/PromptCloudHQ/amazon-reviews-unlocked-mobile-phones/data#) provides the following description:

> PromptCloud [a web scraping company, ndrl] extracted 400 thousand reviews of unlocked mobile phones sold on Amazon.com
> to find out insights with respect to reviews, ratings, price and their relationships.
> 
> Given below are the fields:
> - Product Title
> - Brand
> - Price
> - Rating 
> - Review text
> - Number of people who found the review helpful
>
> Data was acquired in December, 2016 by the crawlers build to deliver [their] data extraction services.


## Troubleshooting

While importing `nltk` module, if you encounter a `ModuleImportError` , the following procedure may help:
- Close Jupyter lab
- Run the following command:
``` 
poetry run python -m ipykernel install --user --name=nltk_ws
```
- Reopen Jupyter Lab
- Select the kernel `nltk_ws`