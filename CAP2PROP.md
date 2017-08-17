# Capstone Project #2 Proposal

**Project Overview**: Proposal is to build a predictive model for a "hypothetical" movie that can be user defined across a defined set of critical features such as leading actors/actresses, genre, and plot descriptions. This is an interesting problem for a number of reasons:

- There are a large number of potential variables that can explain the success (or lack thereof) of a movie, providing the model building a significant challenge in identifying and staging the most relevant variables
- The problem is highly relatable to a large number of people and can be turned into an engaging application as long as the features that can be used to define the "hypothetical" movie are simple in nature but comprehensive in coverage. In addition, the application can be used in a "live" environment (e.g. to predict the box office revenues of yet to be released movies, and then tracking actual vs. predicted revenues in real time)
- In addition to predicting the performance of "hypothetical" movies, the application can be used to identify, statistically, the biggest "surprise" hits or flops. The presentation of these "outliers" can further improve the "engagement" aspect of the application
- The data required to feed the model may not be easily derived from a single source, creating an interesting data acquisition challenge

**Hypothetical client**: Hypothetical clients may include movie studios, or more likely, consumer facing on-line properties focused on movies and television:

- Movie studios: Such a model could be potentially used by a movie studio to provide a high-level initial screen of movie proposals. However, given that movie studios are not likely to consider a large number of potential movies concurrently at any one point in time, the usage of a model is likely to be very limited.

- On-line properties focused on movies and television: An application of this model is more likely to be successfully embedded in consumer facing sites like Rotten Tomatoes and/or IMDB. For example, there could be a weekly competition to write the most "box office" compelling description for a movie given a defined set of actors and genre, or in addition to user or professional reviews, an assessment of whether a movie is a "surprise" hit or flop could be provided in an engaging manner.

**Data**: Data is likely to be sourced from a number of site, however the following are the most promising:

- Web scraping of Box Office Mojo, IMDB and Wikipedia
- Google Knowledge Graph API
- The [CMU Movie Summary Corpus](http://www.cs.cmu.edu/~ark/personas/)

**Project approach**: Target and feature selection:

Target: Cumulative box office revenue for English-speaking movies (inflation adjusted)

Features:

- Date of movie release
- Names of leading actors / actresses
- Names of director(s)
- Genre
- Movie description or plot, converted to numerical features (e.g. though Word2Vec). This is potentially the most novel feature of this model, and it allows the user of the app to express a significant amount of creativity. Dependent on this feature set having significant predictive power after adjusting for all other "simpler" metrics.
- Measures for "sentiment" of leading actors / actresses / director(s). Ideally, a social media-derived affinity score would be developed, but this would significantly limit the period over which the model could be calibrated to the last 10ish years. Alternatively, a "sentiment" metric could be proxied by the historical box office success of the individuals involved or a transformation of their bios to numerical features,. To be explored further.

Primary model to be used is XGBoost. Tensorflow may also be tested time permitting.

**Deliverables**: Deliverables to include:

- Python scripts for scraping / cleaning data, building relevant feature sets, optimizing feature selection and hyperparameters and providing a method for a consumer to enter features for a "hypothetical" movie

- Model wrapped in Flask, live in Amazon AWS and accessible at a minimum through HTTP API endpoints. Additional development of a customer interface (e.g. through React) to be explored time permitting
