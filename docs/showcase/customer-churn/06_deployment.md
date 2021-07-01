# Deployment

Stage 6

A model is not particularly useful unless the customer can access its results.
The complexity of this phase varies widely. This final phase has four tasks:

* Plan deployment: Develop and document a plan for deploying the model.
* Plan monitoring and maintenance: Develop a thorough monitoring and
  maintenance plan to avoid issues during the operational phase (or
  post-project phase) of a model.
* Produce final report: The project team documents a summary of the project
  which might include a final presentation of data mining results.
* Review project: Conduct a project retrospective about what went well, what
  could have been better, and how to improve in the future.


The deployment of machine learning models is the process of making models
available in production where web applications, enterprise software, and APIs
can consume the trained model by providing new data points and generating
predictions. Normally machine learning models are built so that they can be
used to predict an outcome (binary value i.e. 1 or 0 for Classification,
continuous values for Regression, labels for Clustering, etc. There are two
broad ways of generating predictions (i) predict by batch; and (ii) predict
in real-time. This tutorial will show how you can deploy your machine learning
models as API to predict in real-time.

It doesn't actually stop there,  if the model is going to production, be
sure you maintain the model in production. Constant monitoring and occasional
model tuning is often required.
