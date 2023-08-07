# PredictAirPolution
This predicts air pollution index of a major city. It is based on data provided by https://aqicn.org/. This is to demonstrate the steps involved in a ML prediction service
Hopsworks (https://c.app.hopsworks.ai/) is the feature store used

![image](https://github.com/jamello/PredictAirPolution/assets/3978328/c4e09374-7494-4ef5-801a-271ad06cb172)

Step 1: Feature generation script 🐍

1 → fetches raw weather and pollutant data from an external API like https://aqicn.org/city/houston

2 → computes features from this raw data (aka model inputs), and targets (aka model outputs)

3 → stores these features in the *Feature Store* in hopsworks

Step 2: Backfill historical (features, targets) ⏮️

To train a Machine Learning model later, you need enough historical data (features, targets) in your Feature Store.

Run the feature script for a range of past dates, to get enough training data.
![image](https://github.com/jamello/PredictAirPolution/assets/3978328/d52b0cc1-1205-4287-ac41-13dab3155caa)

