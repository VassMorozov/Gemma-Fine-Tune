# Gemma Fine-Tuning
In February 2024, Google released [Gemma](https://blog.google/technology/developers/gemma-open-models/), its own light-weight large language model (LLM) for use in open source projects. The purpose of this project was to explore fine-tuning this model for writing Airbnb reviews using Google Colab.

Although the model can already write an Airbnb review if requested, these are often generic and are not specific to any area or destination. A dataset of reviews for Las Vegas Airbnb listings was recently published on [Kaggle](https://www.kaggle.com/datasets/kanchana1990/airbnb-las-vegas-listings). This contained information such as:

* A review
* A star rating
* What type of property the listing was for
* Number of guests who stayed in the Airbnb

This information was combined to create a prompt for Gemma, where the expected response is the review itself. 

Given the limitations of the free Google Colab hardware, a 4-bit version of the model was used, along with QLoRA, an efficient finetuning technique. This substantially reduced the hardware requirements to complete this project. It is noted that this may ultimately impact end results, however these appeared satisfactory for what I was trying to achieve.

# Example outputs
**Input:** Write me a 1 star Airbnb review for a Private room in home that holds 2 guests.

**Prior to fine-tuning:**

Output: My stay in your private room in your home was wonderful! The space was spacious and comfortable, perfect for two people. The bed was comfortable, the bathroom was clean, and the location was quiet and safe.

**After fine-tuning:**

Output: Not the best location for a solo traveler. Too close to the strip with constant traffic noise that is extremely disruptive especially at night. Would not recommend!
#
**Input:** Write me a 4 star Airbnb review for a Entire home that holds 4 guests.

**Prior to fine-tuning:**

Output: This entire home was a delight to stay in! From the cozy living room to the well-equipped kitchen, everything was just as described. The bedrooms were spacious and comfortable, with ample room for four guests. The outdoor space was fantastic - perfect for grilling, reading, or simply relaxing in the sunshine.

**After fine-tuning:**

Output: Transportation is very convenient to anywhere you might want to go in the Vegas Strip area.  Would definitely recommend for any fun groups of 4!  


