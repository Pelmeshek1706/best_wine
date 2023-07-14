# Best Wine using NLP
#### made by [@pelmeshek1706](https://telegram.me/pelmeshek1706)

Let's imagine a situation. we went to the biggest wine store in town and wanted to choose a wine, for which we went to the winemaker for information about wines. In this project I used a [dataset about wines](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-GPXX0SV2EN/winemag-data-130k-v2.csv) to get interesting information, I also applied some NLP tools to create a recommendation system for choosing wines.

### In this project I will use Distil-BERT
    DistilBERT is a variant of the BERT (Bidirectional Encoder Representations from Transformers) model, which is a state-of-the-art pre-trained language model developed by Google. DistilBERT was introduced by researchers at Hugging Face, a company specializing in natural language processing (NLP) and transformer-based models.

The main idea behind DistilBERT is to create a smaller and faster version of BERT while preserving its performance. It achieves this by applying a process called knowledge distillation, where a larger model (such as BERT) is used to teach a smaller model (DistilBERT) to mimic its behavior. This allows DistilBERT to retain much of the knowledge and performance of BERT while being more computationally efficient.
![alt text](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-GPXX068IEN/images/SBERT.png)
Also It has 40% fewer parameters than BERT base, runs 60% faster, while preserving over 95% of BERT's performances as measured on the GLUE language understanding benchmark.

------------------------------------


### My query that I use for test recomendation:
    'sweet and soft'

#### Received data


|№|	country|winery|	title|	variety|descriptio|	price|points|distance|
|-|--------|------|------|---------|----------|------|------|--------|
|0|Portugal|	José Maria da Fonseca|José Maria da Fonseca 2013 Periquita Rosé (Pen...|Rosé|An instantly enjoyable, balanced rosé. It's fr...|	11.0| 87 |	0.270147 |
|1 |France |Sauvion|	Sauvion 2013 Rosé d'Anjou|Rosé|	Definitely sweet, this soft, red fruit flavore... |	11.0 |	84	|0.278145 |
|2 |Argentina |	Graffigna |	Graffigna 2007 Centenario Estate Bottled Pinot...|	Pinot Grigio |	Funky, off-base floral aromas and a sweet, cot...|	13.0 |	81 |0.283556 |

#### Output description together with their 'distance' parameters:
1) An instantly enjoyable, balanced rosé. It's fresh, clean and full of red berry fruits, with a crisp finish. Drink now.
distance: 0.2701471

2) Definitely sweet, this soft, red fruit flavored rosé has enough crispness to stop it being cloying. It is fruity and ready to drink.
distance: 0.27814543

3) Funky, off-base floral aromas and a sweet, cotton candy flavor profile. Feels flat and sugary to the end, with a nip of bitter almond.
distance: 0.28355634
----------------------------------------------------------------
For distance I used Cosine similarity

