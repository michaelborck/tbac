# Data Preparation

Stage 3

This phase, which is often referred to as “data munging”, prepares the final
data set(s) for modeling. It has five tasks:

* Select data: Determine which data sets will be used and document reasons for
  inclusion/exclusion.
* Clean data: Often this is the lengthiest task. Without it, you’ll likely fall
  victim to garbage-in, garbage-out. A common practice during this task is to
  correct, impute, or remove erroneous values.
* Construct data: Derive new attributes that will be helpful. For example,
  derive someone’s body mass index from height and weight fields.
* Integrate data: Create new data sets by combining data from multiple sources.
* Format data: Re-format data as necessary. For example, you might convert
  string values that store numbers to numeric values so that you can perform
  mathematical operations.

Machine Learning algorithms can typically only have numerical values as their
independent variables. Label encoding is quite pivotal as they encode
categorical labels with appropriate numerical values.  Here we are label
encoding all categorical variables that have unique values.

```python
df.dtypes
```




    gender               object
    SeniorCitizen         int64
    Partner              object
    Dependents           object
    tenure                int64
    PhoneService         object
    MultipleLines        object
    InternetService      object
    OnlineSecurity       object
    OnlineBackup         object
    DeviceProtection     object
    TechSupport          object
    StreamingTV          object
    StreamingMovies      object
    Contract             object
    PaperlessBilling     object
    PaymentMethod        object
    MonthlyCharges      float64
    TotalCharges         object
    Churn                object
    dtype: object


Our customer churn data set is clean, no missing values, no nulls, no duplicates
but still needs to be transformed for use by machine learning algorithms. The
following need to be done before one-hot-encoding:

* Delete the CustomerID column.
* The seniorCitizen column only contains two values, 0 or 1.  It is currently
  listed as a numeric type.
* The TotalCharges column is a generic type and need to be converted into a
  numeric
* Preserve the 'Churn' column as this is the column we are trying to predict.


```python
del df['customerID']
df['TotalCharges'] = pd.to_numeric(df['TotalCharges'],errors='coerce')
df['TotalCharges'] = df['TotalCharges'].astype("float")
df['SeniorCitizen']=pd.Categorical(df['SeniorCitizen'])

df.dtypes
```


    gender                object
    SeniorCitizen       category
    Partner               object
    Dependents            object
    tenure                 int64
    PhoneService          object
    MultipleLines         object
    InternetService       object
    OnlineSecurity        object
    OnlineBackup          object
    DeviceProtection      object
    TechSupport           object
    StreamingTV           object
    StreamingMovies       object
    Contract              object
    PaperlessBilling      object
    PaymentMethod         object
    MonthlyCharges       float64
    TotalCharges         float64
    Churn                 object
    dtype: object



Once all columns are the correct data type then proceed to one-hot-encode.

```python
churn = df['Churn']
del df['Churn']
df= pd.get_dummies(df)
df['Churn'] = churn
df.dtypes
```




    tenure                                       int64
    MonthlyCharges                             float64
    TotalCharges                               float64
    gender_Female                                uint8
    gender_Male                                  uint8
    SeniorCitizen_0                              uint8
    SeniorCitizen_1                              uint8
    Partner_No                                   uint8
    Partner_Yes                                  uint8
    Dependents_No                                uint8
    Dependents_Yes                               uint8
    PhoneService_No                              uint8
    PhoneService_Yes                             uint8
    MultipleLines_No                             uint8
    MultipleLines_No phone service               uint8
    MultipleLines_Yes                            uint8
    InternetService_DSL                          uint8
    InternetService_Fiber optic                  uint8
    InternetService_No                           uint8
    OnlineSecurity_No                            uint8
    OnlineSecurity_No internet service           uint8
    OnlineSecurity_Yes                           uint8
    OnlineBackup_No                              uint8
    OnlineBackup_No internet service             uint8
    OnlineBackup_Yes                             uint8
    DeviceProtection_No                          uint8
    DeviceProtection_No internet service         uint8
    DeviceProtection_Yes                         uint8
    TechSupport_No                               uint8
    TechSupport_No internet service              uint8
    TechSupport_Yes                              uint8
    StreamingTV_No                               uint8
    StreamingTV_No internet service              uint8
    StreamingTV_Yes                              uint8
    StreamingMovies_No                           uint8
    StreamingMovies_No internet service          uint8
    StreamingMovies_Yes                          uint8
    Contract_Month-to-month                      uint8
    Contract_One year                            uint8
    Contract_Two year                            uint8
    PaperlessBilling_No                          uint8
    PaperlessBilling_Yes                         uint8
    PaymentMethod_Bank transfer (automatic)      uint8
    PaymentMethod_Credit card (automatic)        uint8
    PaymentMethod_Electronic check               uint8
    PaymentMethod_Mailed check                   uint8
    Churn                                       object
    dtype: object


