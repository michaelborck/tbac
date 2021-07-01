# Modeling

Stage 4

Churn prediction modeling techniques attempt to understand the precise customer
behaviors and attributes which signal the risk and timing of customer churn.
The accuracy of the technique used is obviously critical to the success of
any proactive retention efforts.  The most common churn prediction models
are based on statistical and data-mining methods, such as logistic
regression and other binary modeling techniques.

Out data has been prepared, we will withhold a random sample of 10% of the data.
We will use this to evaluate the final model.

We use the PyCaret library.  We must set the dataset via the setup() function.
This requires that we provide the Pandas DataFrame and specify the name of
the column that contains the target variable. The setup() function also allows
you to configure simple data pipeline, such as scaling, power transforms,
missing data handling, and PCA transforms.

Next, we can compare standard machine learning models by calling the
compare_models() function. By default, it will evaluate models using 10-fold
cross-validation, sort results by classification accuracy, and return the
single best model. These are good defaults, and we don’t need to change a thing.


## Compare Models

<style  type="text/css" >
    #T_1314f_ th {
          text-align: left;
    }#T_1314f_row0_col0,#T_1314f_row0_col3,#T_1314f_row0_col4,#T_1314f_row0_col5,#T_1314f_row0_col6,#T_1314f_row0_col7,#T_1314f_row1_col0,#T_1314f_row1_col1,#T_1314f_row1_col2,#T_1314f_row1_col3,#T_1314f_row1_col4,#T_1314f_row1_col5,#T_1314f_row2_col0,#T_1314f_row2_col1,#T_1314f_row2_col2,#T_1314f_row2_col3,#T_1314f_row2_col5,#T_1314f_row2_col6,#T_1314f_row2_col7,#T_1314f_row3_col0,#T_1314f_row3_col1,#T_1314f_row3_col2,#T_1314f_row3_col3,#T_1314f_row3_col4,#T_1314f_row3_col5,#T_1314f_row3_col6,#T_1314f_row3_col7,#T_1314f_row4_col0,#T_1314f_row4_col1,#T_1314f_row4_col2,#T_1314f_row4_col3,#T_1314f_row4_col4,#T_1314f_row4_col5,#T_1314f_row4_col6,#T_1314f_row4_col7,#T_1314f_row5_col0,#T_1314f_row5_col1,#T_1314f_row5_col2,#T_1314f_row5_col3,#T_1314f_row5_col4,#T_1314f_row5_col5,#T_1314f_row5_col6,#T_1314f_row5_col7,#T_1314f_row6_col0,#T_1314f_row6_col1,#T_1314f_row6_col2,#T_1314f_row6_col3,#T_1314f_row6_col4,#T_1314f_row6_col5,#T_1314f_row6_col6,#T_1314f_row6_col7,#T_1314f_row7_col0,#T_1314f_row7_col1,#T_1314f_row7_col2,#T_1314f_row7_col3,#T_1314f_row7_col4,#T_1314f_row7_col5,#T_1314f_row7_col6,#T_1314f_row7_col7,#T_1314f_row8_col0,#T_1314f_row8_col1,#T_1314f_row8_col2,#T_1314f_row8_col3,#T_1314f_row8_col4,#T_1314f_row8_col5,#T_1314f_row8_col6,#T_1314f_row8_col7,#T_1314f_row9_col0,#T_1314f_row9_col1,#T_1314f_row9_col2,#T_1314f_row9_col3,#T_1314f_row9_col4,#T_1314f_row9_col5,#T_1314f_row9_col6,#T_1314f_row9_col7,#T_1314f_row10_col0,#T_1314f_row10_col1,#T_1314f_row10_col2,#T_1314f_row10_col3,#T_1314f_row10_col4,#T_1314f_row10_col5,#T_1314f_row10_col6,#T_1314f_row10_col7,#T_1314f_row11_col0,#T_1314f_row11_col1,#T_1314f_row11_col2,#T_1314f_row11_col3,#T_1314f_row11_col4,#T_1314f_row11_col5,#T_1314f_row11_col6,#T_1314f_row11_col7,#T_1314f_row12_col0,#T_1314f_row12_col1,#T_1314f_row12_col2,#T_1314f_row12_col4,#T_1314f_row12_col6,#T_1314f_row12_col7,#T_1314f_row13_col0,#T_1314f_row13_col1,#T_1314f_row13_col2,#T_1314f_row13_col3,#T_1314f_row13_col4,#T_1314f_row13_col5,#T_1314f_row13_col6,#T_1314f_row13_col7{
            text-align:  left;
            text-align:  left;
        }#T_1314f_row0_col1,#T_1314f_row0_col2,#T_1314f_row1_col6,#T_1314f_row1_col7,#T_1314f_row2_col4,#T_1314f_row12_col3,#T_1314f_row12_col5{
            text-align:  left;
            text-align:  left;
            background-color:  yellow;
        }#T_1314f_row0_col8,#T_1314f_row1_col8,#T_1314f_row2_col8,#T_1314f_row3_col8,#T_1314f_row4_col8,#T_1314f_row5_col8,#T_1314f_row6_col8,#T_1314f_row7_col8,#T_1314f_row8_col8,#T_1314f_row9_col8,#T_1314f_row11_col8,#T_1314f_row12_col8,#T_1314f_row13_col8{
            text-align:  left;
            text-align:  left;
            background-color:  lightgrey;
        }#T_1314f_row10_col8{
            text-align:  left;
            text-align:  left;
            background-color:  yellow;
            background-color:  lightgrey;
        }</style><table id="T_1314f_" ><thead>    <tr>        <th class="blank level0" ></th>        <th class="col_heading level0 col0" >Model</th>        <th class="col_heading level0 col1" >Accuracy</th>        <th class="col_heading level0 col2" >AUC</th>        <th class="col_heading level0 col3" >Recall</th>        <th class="col_heading level0 col4" >Prec.</th>        <th class="col_heading level0 col5" >F1</th>        <th class="col_heading level0 col6" >Kappa</th>        <th class="col_heading level0 col7" >MCC</th>        <th class="col_heading level0 col8" >TT (Sec)</th>    </tr></thead><tbody>
                <tr>
                        <th id="T_1314f_level0_row0" class="row_heading level0 row0" >lr</th>
                        <td id="T_1314f_row0_col0" class="data row0 col0" >Logistic Regression</td>
                        <td id="T_1314f_row0_col1" class="data row0 col1" >0.7993</td>
                        <td id="T_1314f_row0_col2" class="data row0 col2" >0.8409</td>
                        <td id="T_1314f_row0_col3" class="data row0 col3" >0.5549</td>
                        <td id="T_1314f_row0_col4" class="data row0 col4" >0.6650</td>
                        <td id="T_1314f_row0_col5" class="data row0 col5" >0.6040</td>
                        <td id="T_1314f_row0_col6" class="data row0 col6" >0.4713</td>
                        <td id="T_1314f_row0_col7" class="data row0 col7" >0.4753</td>
                        <td id="T_1314f_row0_col8" class="data row0 col8" >0.9210</td>
            </tr>
            <tr>
                        <th id="T_1314f_level0_row1" class="row_heading level0 row1" >lda</th>
                        <td id="T_1314f_row1_col0" class="data row1 col0" >Linear Discriminant Analysis</td>
                        <td id="T_1314f_row1_col1" class="data row1 col1" >0.7988</td>
                        <td id="T_1314f_row1_col2" class="data row1 col2" >0.8359</td>
                        <td id="T_1314f_row1_col3" class="data row1 col3" >0.5661</td>
                        <td id="T_1314f_row1_col4" class="data row1 col4" >0.6592</td>
                        <td id="T_1314f_row1_col5" class="data row1 col5" >0.6082</td>
                        <td id="T_1314f_row1_col6" class="data row1 col6" >0.4741</td>
                        <td id="T_1314f_row1_col7" class="data row1 col7" >0.4771</td>
                        <td id="T_1314f_row1_col8" class="data row1 col8" >0.0360</td>
            </tr>
            <tr>
                        <th id="T_1314f_level0_row2" class="row_heading level0 row2" >ridge</th>
                        <td id="T_1314f_row2_col0" class="data row2 col0" >Ridge Classifier</td>
                        <td id="T_1314f_row2_col1" class="data row2 col1" >0.7955</td>
                        <td id="T_1314f_row2_col2" class="data row2 col2" >0.0000</td>
                        <td id="T_1314f_row2_col3" class="data row2 col3" >0.5163</td>
                        <td id="T_1314f_row2_col4" class="data row2 col4" >0.6692</td>
                        <td id="T_1314f_row2_col5" class="data row2 col5" >0.5821</td>
                        <td id="T_1314f_row2_col6" class="data row2 col6" >0.4499</td>
                        <td id="T_1314f_row2_col7" class="data row2 col7" >0.4570</td>
                        <td id="T_1314f_row2_col8" class="data row2 col8" >0.0200</td>
            </tr>
            <tr>
                        <th id="T_1314f_level0_row3" class="row_heading level0 row3" >gbc</th>
                        <td id="T_1314f_row3_col0" class="data row3 col0" >Gradient Boosting Classifier</td>
                        <td id="T_1314f_row3_col1" class="data row3 col1" >0.7905</td>
                        <td id="T_1314f_row3_col2" class="data row3 col2" >0.8356</td>
                        <td id="T_1314f_row3_col3" class="data row3 col3" >0.5198</td>
                        <td id="T_1314f_row3_col4" class="data row3 col4" >0.6526</td>
                        <td id="T_1314f_row3_col5" class="data row3 col5" >0.5780</td>
                        <td id="T_1314f_row3_col6" class="data row3 col6" >0.4412</td>
                        <td id="T_1314f_row3_col7" class="data row3 col7" >0.4466</td>
                        <td id="T_1314f_row3_col8" class="data row3 col8" >2.2610</td>
            </tr>
            <tr>
                        <th id="T_1314f_level0_row4" class="row_heading level0 row4" >lightgbm</th>
                        <td id="T_1314f_row4_col0" class="data row4 col0" >Light Gradient Boosting Machine</td>
                        <td id="T_1314f_row4_col1" class="data row4 col1" >0.7841</td>
                        <td id="T_1314f_row4_col2" class="data row4 col2" >0.8213</td>
                        <td id="T_1314f_row4_col3" class="data row4 col3" >0.5146</td>
                        <td id="T_1314f_row4_col4" class="data row4 col4" >0.6363</td>
                        <td id="T_1314f_row4_col5" class="data row4 col5" >0.5686</td>
                        <td id="T_1314f_row4_col6" class="data row4 col6" >0.4268</td>
                        <td id="T_1314f_row4_col7" class="data row4 col7" >0.4314</td>
                        <td id="T_1314f_row4_col8" class="data row4 col8" >17.6720</td>
            </tr>
            <tr>
                        <th id="T_1314f_level0_row5" class="row_heading level0 row5" >ada</th>
                        <td id="T_1314f_row5_col0" class="data row5 col0" >Ada Boost Classifier</td>
                        <td id="T_1314f_row5_col1" class="data row5 col1" >0.7815</td>
                        <td id="T_1314f_row5_col2" class="data row5 col2" >0.8131</td>
                        <td id="T_1314f_row5_col3" class="data row5 col3" >0.5180</td>
                        <td id="T_1314f_row5_col4" class="data row5 col4" >0.6276</td>
                        <td id="T_1314f_row5_col5" class="data row5 col5" >0.5670</td>
                        <td id="T_1314f_row5_col6" class="data row5 col6" >0.4228</td>
                        <td id="T_1314f_row5_col7" class="data row5 col7" >0.4266</td>
                        <td id="T_1314f_row5_col8" class="data row5 col8" >0.6080</td>
            </tr>
            <tr>
                        <th id="T_1314f_level0_row6" class="row_heading level0 row6" >rf</th>
                        <td id="T_1314f_row6_col0" class="data row6 col0" >Random Forest Classifier</td>
                        <td id="T_1314f_row6_col1" class="data row6 col1" >0.7796</td>
                        <td id="T_1314f_row6_col2" class="data row6 col2" >0.8123</td>
                        <td id="T_1314f_row6_col3" class="data row6 col3" >0.4623</td>
                        <td id="T_1314f_row6_col4" class="data row6 col4" >0.6403</td>
                        <td id="T_1314f_row6_col5" class="data row6 col5" >0.5364</td>
                        <td id="T_1314f_row6_col6" class="data row6 col6" >0.3970</td>
                        <td id="T_1314f_row6_col7" class="data row6 col7" >0.4063</td>
                        <td id="T_1314f_row6_col8" class="data row6 col8" >0.6200</td>
            </tr>
            <tr>
                        <th id="T_1314f_level0_row7" class="row_heading level0 row7" >svm</th>
                        <td id="T_1314f_row7_col0" class="data row7 col0" >SVM - Linear Kernel</td>
                        <td id="T_1314f_row7_col1" class="data row7 col1" >0.7782</td>
                        <td id="T_1314f_row7_col2" class="data row7 col2" >0.0000</td>
                        <td id="T_1314f_row7_col3" class="data row7 col3" >0.5679</td>
                        <td id="T_1314f_row7_col4" class="data row7 col4" >0.6076</td>
                        <td id="T_1314f_row7_col5" class="data row7 col5" >0.5812</td>
                        <td id="T_1314f_row7_col6" class="data row7 col6" >0.4322</td>
                        <td id="T_1314f_row7_col7" class="data row7 col7" >0.4361</td>
                        <td id="T_1314f_row7_col8" class="data row7 col8" >0.0340</td>
            </tr>
            <tr>
                        <th id="T_1314f_level0_row8" class="row_heading level0 row8" >xgboost</th>
                        <td id="T_1314f_row8_col0" class="data row8 col0" >Extreme Gradient Boosting</td>
                        <td id="T_1314f_row8_col1" class="data row8 col1" >0.7770</td>
                        <td id="T_1314f_row8_col2" class="data row8 col2" >0.8045</td>
                        <td id="T_1314f_row8_col3" class="data row8 col3" >0.4914</td>
                        <td id="T_1314f_row8_col4" class="data row8 col4" >0.6231</td>
                        <td id="T_1314f_row8_col5" class="data row8 col5" >0.5486</td>
                        <td id="T_1314f_row8_col6" class="data row8 col6" >0.4035</td>
                        <td id="T_1314f_row8_col7" class="data row8 col7" >0.4090</td>
                        <td id="T_1314f_row8_col8" class="data row8 col8" >8.3540</td>
            </tr>
            <tr>
                        <th id="T_1314f_level0_row9" class="row_heading level0 row9" >et</th>
                        <td id="T_1314f_row9_col0" class="data row9 col0" >Extra Trees Classifier</td>
                        <td id="T_1314f_row9_col1" class="data row9 col1" >0.7729</td>
                        <td id="T_1314f_row9_col2" class="data row9 col2" >0.7858</td>
                        <td id="T_1314f_row9_col3" class="data row9 col3" >0.4477</td>
                        <td id="T_1314f_row9_col4" class="data row9 col4" >0.6250</td>
                        <td id="T_1314f_row9_col5" class="data row9 col5" >0.5210</td>
                        <td id="T_1314f_row9_col6" class="data row9 col6" >0.3778</td>
                        <td id="T_1314f_row9_col7" class="data row9 col7" >0.3871</td>
                        <td id="T_1314f_row9_col8" class="data row9 col8" >0.3010</td>
            </tr>
            <tr>
                        <th id="T_1314f_level0_row10" class="row_heading level0 row10" >nb</th>
                        <td id="T_1314f_row10_col0" class="data row10 col0" >Naive Bayes</td>
                        <td id="T_1314f_row10_col1" class="data row10 col1" >0.7661</td>
                        <td id="T_1314f_row10_col2" class="data row10 col2" >0.7751</td>
                        <td id="T_1314f_row10_col3" class="data row10 col3" >0.6235</td>
                        <td id="T_1314f_row10_col4" class="data row10 col4" >0.5720</td>
                        <td id="T_1314f_row10_col5" class="data row10 col5" >0.5961</td>
                        <td id="T_1314f_row10_col6" class="data row10 col6" >0.4320</td>
                        <td id="T_1314f_row10_col7" class="data row10 col7" >0.4332</td>
                        <td id="T_1314f_row10_col8" class="data row10 col8" >0.0110</td>
            </tr>
            <tr>
                        <th id="T_1314f_level0_row11" class="row_heading level0 row11" >knn</th>
                        <td id="T_1314f_row11_col0" class="data row11 col0" >K Neighbors Classifier</td>
                        <td id="T_1314f_row11_col1" class="data row11 col1" >0.7625</td>
                        <td id="T_1314f_row11_col2" class="data row11 col2" >0.7733</td>
                        <td id="T_1314f_row11_col3" class="data row11 col3" >0.5198</td>
                        <td id="T_1314f_row11_col4" class="data row11 col4" >0.5789</td>
                        <td id="T_1314f_row11_col5" class="data row11 col5" >0.5472</td>
                        <td id="T_1314f_row11_col6" class="data row11 col6" >0.3870</td>
                        <td id="T_1314f_row11_col7" class="data row11 col7" >0.3884</td>
                        <td id="T_1314f_row11_col8" class="data row11 col8" >0.1030</td>
            </tr>
            <tr>
                        <th id="T_1314f_level0_row12" class="row_heading level0 row12" >qda</th>
                        <td id="T_1314f_row12_col0" class="data row12 col0" >Quadratic Discriminant Analysis</td>
                        <td id="T_1314f_row12_col1" class="data row12 col1" >0.7492</td>
                        <td id="T_1314f_row12_col2" class="data row12 col2" >0.8147</td>
                        <td id="T_1314f_row12_col3" class="data row12 col3" >0.7213</td>
                        <td id="T_1314f_row12_col4" class="data row12 col4" >0.5354</td>
                        <td id="T_1314f_row12_col5" class="data row12 col5" >0.6142</td>
                        <td id="T_1314f_row12_col6" class="data row12 col6" >0.4346</td>
                        <td id="T_1314f_row12_col7" class="data row12 col7" >0.4455</td>
                        <td id="T_1314f_row12_col8" class="data row12 col8" >0.0180</td>
            </tr>
            <tr>
                        <th id="T_1314f_level0_row13" class="row_heading level0 row13" >dt</th>
                        <td id="T_1314f_row13_col0" class="data row13 col0" >Decision Tree Classifier</td>
                        <td id="T_1314f_row13_col1" class="data row13 col1" >0.7345</td>
                        <td id="T_1314f_row13_col2" class="data row13 col2" >0.6807</td>
                        <td id="T_1314f_row13_col3" class="data row13 col3" >0.5326</td>
                        <td id="T_1314f_row13_col4" class="data row13 col4" >0.5200</td>
                        <td id="T_1314f_row13_col5" class="data row13 col5" >0.5259</td>
                        <td id="T_1314f_row13_col6" class="data row13 col6" >0.3417</td>
                        <td id="T_1314f_row13_col7" class="data row13 col7" >0.3419</td>
                        <td id="T_1314f_row13_col8" class="data row13 col8" >0.1380</td>
            </tr>
    </tbody></table>

## Print 'Best' model

```python
print(best)
```

    LogisticRegression(C=1.0, class_weight=None, dual=False, fit_intercept=True,
                       intercept_scaling=1, l1_ratio=None, max_iter=1000,
                       multi_class='auto', n_jobs=None, penalty='l2',
                       random_state=42, solver='lbfgs', tol=0.0001, verbose=0,
                       warm_start=False)


## Create Model



<style  type="text/css" >
#T_2c6c0_row10_col0,#T_2c6c0_row10_col1,#T_2c6c0_row10_col2,#T_2c6c0_row10_col3,#T_2c6c0_row10_col4,#T_2c6c0_row10_col5,#T_2c6c0_row10_col6{
            background:  yellow;
        }</style><table id="T_2c6c0_" ><thead>    <tr>        <th class="blank level0" ></th>        <th class="col_heading level0 col0" >Accuracy</th>        <th class="col_heading level0 col1" >AUC</th>        <th class="col_heading level0 col2" >Recall</th>        <th class="col_heading level0 col3" >Prec.</th>        <th class="col_heading level0 col4" >F1</th>        <th class="col_heading level0 col5" >Kappa</th>        <th class="col_heading level0 col6" >MCC</th>    </tr></thead><tbody>
                <tr>
                        <th id="T_2c6c0_level0_row0" class="row_heading level0 row0" >0</th>
                        <td id="T_2c6c0_row0_col0" class="data row0 col0" >0.7607</td>
                        <td id="T_2c6c0_row0_col1" class="data row0 col1" >0.8181</td>
                        <td id="T_2c6c0_row0_col2" class="data row0 col2" >0.4359</td>
                        <td id="T_2c6c0_row0_col3" class="data row0 col3" >0.5930</td>
                        <td id="T_2c6c0_row0_col4" class="data row0 col4" >0.5025</td>
                        <td id="T_2c6c0_row0_col5" class="data row0 col5" >0.3497</td>
                        <td id="T_2c6c0_row0_col6" class="data row0 col6" >0.3569</td>
            </tr>
            <tr>
                        <th id="T_2c6c0_level0_row1" class="row_heading level0 row1" >1</th>
                        <td id="T_2c6c0_row1_col0" class="data row1 col0" >0.8057</td>
                        <td id="T_2c6c0_row1_col1" class="data row1 col1" >0.8357</td>
                        <td id="T_2c6c0_row1_col2" class="data row1 col2" >0.5470</td>
                        <td id="T_2c6c0_row1_col3" class="data row1 col3" >0.6882</td>
                        <td id="T_2c6c0_row1_col4" class="data row1 col4" >0.6095</td>
                        <td id="T_2c6c0_row1_col5" class="data row1 col5" >0.4824</td>
                        <td id="T_2c6c0_row1_col6" class="data row1 col6" >0.4881</td>
            </tr>
            <tr>
                        <th id="T_2c6c0_level0_row2" class="row_heading level0 row2" >2</th>
                        <td id="T_2c6c0_row2_col0" class="data row2 col0" >0.8128</td>
                        <td id="T_2c6c0_row2_col1" class="data row2 col1" >0.8565</td>
                        <td id="T_2c6c0_row2_col2" class="data row2 col2" >0.6239</td>
                        <td id="T_2c6c0_row2_col3" class="data row2 col3" >0.6759</td>
                        <td id="T_2c6c0_row2_col4" class="data row2 col4" >0.6489</td>
                        <td id="T_2c6c0_row2_col5" class="data row2 col5" >0.5215</td>
                        <td id="T_2c6c0_row2_col6" class="data row2 col6" >0.5223</td>
            </tr>
            <tr>
                        <th id="T_2c6c0_level0_row3" class="row_heading level0 row3" >3</th>
                        <td id="T_2c6c0_row3_col0" class="data row3 col0" >0.8175</td>
                        <td id="T_2c6c0_row3_col1" class="data row3 col1" >0.8723</td>
                        <td id="T_2c6c0_row3_col2" class="data row3 col2" >0.5556</td>
                        <td id="T_2c6c0_row3_col3" class="data row3 col3" >0.7222</td>
                        <td id="T_2c6c0_row3_col4" class="data row3 col4" >0.6280</td>
                        <td id="T_2c6c0_row3_col5" class="data row3 col5" >0.5099</td>
                        <td id="T_2c6c0_row3_col6" class="data row3 col6" >0.5176</td>
            </tr>
            <tr>
                        <th id="T_2c6c0_level0_row4" class="row_heading level0 row4" >4</th>
                        <td id="T_2c6c0_row4_col0" class="data row4 col0" >0.8009</td>
                        <td id="T_2c6c0_row4_col1" class="data row4 col1" >0.8393</td>
                        <td id="T_2c6c0_row4_col2" class="data row4 col2" >0.5897</td>
                        <td id="T_2c6c0_row4_col3" class="data row4 col3" >0.6571</td>
                        <td id="T_2c6c0_row4_col4" class="data row4 col4" >0.6216</td>
                        <td id="T_2c6c0_row4_col5" class="data row4 col5" >0.4871</td>
                        <td id="T_2c6c0_row4_col6" class="data row4 col6" >0.4884</td>
            </tr>
            <tr>
                        <th id="T_2c6c0_level0_row5" class="row_heading level0 row5" >5</th>
                        <td id="T_2c6c0_row5_col0" class="data row5 col0" >0.7981</td>
                        <td id="T_2c6c0_row5_col1" class="data row5 col1" >0.8504</td>
                        <td id="T_2c6c0_row5_col2" class="data row5 col2" >0.6121</td>
                        <td id="T_2c6c0_row5_col3" class="data row5 col3" >0.6396</td>
                        <td id="T_2c6c0_row5_col4" class="data row5 col4" >0.6256</td>
                        <td id="T_2c6c0_row5_col5" class="data row5 col5" >0.4874</td>
                        <td id="T_2c6c0_row5_col6" class="data row5 col6" >0.4877</td>
            </tr>
            <tr>
                        <th id="T_2c6c0_level0_row6" class="row_heading level0 row6" >6</th>
                        <td id="T_2c6c0_row6_col0" class="data row6 col0" >0.8029</td>
                        <td id="T_2c6c0_row6_col1" class="data row6 col1" >0.8241</td>
                        <td id="T_2c6c0_row6_col2" class="data row6 col2" >0.5690</td>
                        <td id="T_2c6c0_row6_col3" class="data row6 col3" >0.6667</td>
                        <td id="T_2c6c0_row6_col4" class="data row6 col4" >0.6140</td>
                        <td id="T_2c6c0_row6_col5" class="data row6 col5" >0.4827</td>
                        <td id="T_2c6c0_row6_col6" class="data row6 col6" >0.4854</td>
            </tr>
            <tr>
                        <th id="T_2c6c0_level0_row7" class="row_heading level0 row7" >7</th>
                        <td id="T_2c6c0_row7_col0" class="data row7 col0" >0.7957</td>
                        <td id="T_2c6c0_row7_col1" class="data row7 col1" >0.8301</td>
                        <td id="T_2c6c0_row7_col2" class="data row7 col2" >0.5345</td>
                        <td id="T_2c6c0_row7_col3" class="data row7 col3" >0.6596</td>
                        <td id="T_2c6c0_row7_col4" class="data row7 col4" >0.5905</td>
                        <td id="T_2c6c0_row7_col5" class="data row7 col5" >0.4564</td>
                        <td id="T_2c6c0_row7_col6" class="data row7 col6" >0.4609</td>
            </tr>
            <tr>
                        <th id="T_2c6c0_level0_row8" class="row_heading level0 row8" >8</th>
                        <td id="T_2c6c0_row8_col0" class="data row8 col0" >0.8266</td>
                        <td id="T_2c6c0_row8_col1" class="data row8 col1" >0.8501</td>
                        <td id="T_2c6c0_row8_col2" class="data row8 col2" >0.5690</td>
                        <td id="T_2c6c0_row8_col3" class="data row8 col3" >0.7416</td>
                        <td id="T_2c6c0_row8_col4" class="data row8 col4" >0.6439</td>
                        <td id="T_2c6c0_row8_col5" class="data row8 col5" >0.5319</td>
                        <td id="T_2c6c0_row8_col6" class="data row8 col6" >0.5401</td>
            </tr>
            <tr>
                        <th id="T_2c6c0_level0_row9" class="row_heading level0 row9" >9</th>
                        <td id="T_2c6c0_row9_col0" class="data row9 col0" >0.7720</td>
                        <td id="T_2c6c0_row9_col1" class="data row9 col1" >0.8328</td>
                        <td id="T_2c6c0_row9_col2" class="data row9 col2" >0.5128</td>
                        <td id="T_2c6c0_row9_col3" class="data row9 col3" >0.6061</td>
                        <td id="T_2c6c0_row9_col4" class="data row9 col4" >0.5556</td>
                        <td id="T_2c6c0_row9_col5" class="data row9 col5" >0.4036</td>
                        <td id="T_2c6c0_row9_col6" class="data row9 col6" >0.4062</td>
            </tr>
            <tr>
                        <th id="T_2c6c0_level0_row10" class="row_heading level0 row10" >Mean</th>
                        <td id="T_2c6c0_row10_col0" class="data row10 col0" >0.7993</td>
                        <td id="T_2c6c0_row10_col1" class="data row10 col1" >0.8409</td>
                        <td id="T_2c6c0_row10_col2" class="data row10 col2" >0.5549</td>
                        <td id="T_2c6c0_row10_col3" class="data row10 col3" >0.6650</td>
                        <td id="T_2c6c0_row10_col4" class="data row10 col4" >0.6040</td>
                        <td id="T_2c6c0_row10_col5" class="data row10 col5" >0.4713</td>
                        <td id="T_2c6c0_row10_col6" class="data row10 col6" >0.4753</td>
            </tr>
            <tr>
                        <th id="T_2c6c0_level0_row11" class="row_heading level0 row11" >SD</th>
                        <td id="T_2c6c0_row11_col0" class="data row11 col0" >0.0189</td>
                        <td id="T_2c6c0_row11_col1" class="data row11 col1" >0.0156</td>
                        <td id="T_2c6c0_row11_col2" class="data row11 col2" >0.0510</td>
                        <td id="T_2c6c0_row11_col3" class="data row11 col3" >0.0438</td>
                        <td id="T_2c6c0_row11_col4" class="data row11 col4" >0.0423</td>
                        <td id="T_2c6c0_row11_col5" class="data row11 col5" >0.0529</td>
                        <td id="T_2c6c0_row11_col6" class="data row11 col6" >0.0527</td>
            </tr>
    </tbody></table>



```python
lr_final = finalize_model(lr_model)
```


```python
save_model(lr_final,'lr_20210701')
```

    Finished loading model, total used 100 iterations
    Transformation Pipeline and Model Succesfully Saved
