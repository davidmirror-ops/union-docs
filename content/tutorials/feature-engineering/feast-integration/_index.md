---
title: Feast integration
weight: 1
variants: +flyte -serverless -byoc -selfmanaged
sidebar_expanded: false
---

# Feast Integration

[Feast](https://feast.dev/) is an operational data system for managing and serving machine learning features to models in production.

Flyte provides a way to train models and perform feature engineering as a single pipeline.
But it provides no way to serve these features to production when the model matures and is ready to be served in production.

This is where Feast can be helpful.

On leveraging the collective capabilities, Flyte enables engineering the features, and Feast provides the feature registry and online feature serving system.
Moreover, Flyte can help ensure incremental development of features and enables to turn on the sync to online stores only when one is confident about the features.

In this tutorial, we'll walk through how Feast can be used to store and retrieve features to train and test the model through a pipeline curated using Flyte.

## Dataset

We'll use the horse colic dataset to determine if the lesion of the horse is surgical or not. This is a modified version of the original dataset.

The dataset will have the following columns:

* surgery
* age
* hospital number
* rectal temperature
* pulse
* respiratory rate
* temperature of extremities
* peripheral pulse
* mucous membranes
* capillary refill time
* pain
* peristalsis
* abdominal distension
* nasogastric tube
* nasogastric reflux
* nasogastric reflux PH
* rectal examination
* abdomen
* packed cell volume
* total protein
* abdominocentesis appearance
* abdomcentesis total protein
* outcome
* surgical lesion
* timestamp

The horse colic dataset will be a compressed zip file consisting of the SQLite DB.
For this example, we wanted a dataset available online, but this could be easily plugged into another dataset/data management system
like Snowflake, Athena, Hive, BigQuery, or Spark, all of which are supported by Flyte.

## Takeaways

1. Source data is from SQL-like data sources
2. Procreated feature transforms
3. Serve features to production using Feast
