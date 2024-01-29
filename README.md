# Binary classification: offers on the marketplace
## Overview
### About Samokat.Tech
- We create IT for real-time retail.
- Our goal is to ensure that any product gets into the hands of customers as quickly as possible in the physical world.
- We are growing quickly - in 2020, our IT products helped deliver 1.6 million orders per month in 4 cities of Russia. Now in the first half of 2023 this is 92 million orders and a 90% increase in turnover compared to last year*.
- This rapid growth has been made possible by technology and robotics. We digitize and automate all stages of creating value for the delivery client: from procurement and logistics to the operation of dark stores and management of promotional campaigns.

## Description
The Samokat.tech machine learning team creates models for demand forecasting, assortment planning, logistics robotization, automatic generation of user content and for many other tasks.

## Formulation of the problem
- In this competition, we invite you to solve one of the practical problems of the matching and machine learning team.
The matching and machine learning team works with offers from marketplace sellers, assortments, and competitors’ products.

- We work with images, texts, tabular data and use deep learning and computer vision models.

- Here, we offer a product matching task:
  - You have to implement the final part of the matching pipeline. In it, you must decide for each pair (product offered by the seller - product on the site) whether it is a match or not (binary classification).
To do this, each pair has a set of features and sets of vectors (picture and text) that describe the products from this pair.

- F-score is used as a solution quality metric.

## Deadlines
- 01/25/2024 7:00 PM (Moscow time) - 02/08/2024 11:59 PM (Moscow time) - solution to the problem.
- 02/11/2024 11:59 PM (Moscow time) - sending completed notebooks for evaluation.
- 02/15/2024 - Online broadcast with summing up. 
- 02/18/2024 and beyond - individual meetings of the matching and machine learning team with the five best participants in the competition.

## Dataset Description

To solve the problem, we provide anonymized data on sellers’ product offers (offers) and products from the Megamarket marketplace (goods).
The data for each offer already contains the closest products from the assortment and indicates the main characteristics for this pair. It is only necessary to classify which of the pairs is a match and which is not.

### Files
- train.csv - training dataset
- test.csv - testing dataset
### Columns
`offer_depersonalised` and `goods_depersonalised` - offer and product identifiers, respectively
`sum_length` - total length of a pair of names and attributes in characters
`attrs+title_score` - match probability from the rescoring model
`offer_price` and `item_price` - the price of the offer and the product, respectively
`goods_category_id` - product category
`id` - identifier of the pair offer_depersonalised + $ + goods_depersonalised
`target` (only in train.csv) - class label (0 - not a match, 1 - a match)

### Embeddings
`goods_image_vectors` and `offer_image_vectors` - contain files with image vectors (embed_deperson.npy) and their identifiers (items_deperson.npy) for assortment products and offers, respectively. Objects in files are correlated 1 to 1
`goods_title_vectors` and `offer_title_vectors` - contain files with vectors of titles+attributes (embed_deperson.npy) and their identifiers (items_deperson.npy) for assortment goods and offers, respectively. Objects in files are correlated 1 to 1
